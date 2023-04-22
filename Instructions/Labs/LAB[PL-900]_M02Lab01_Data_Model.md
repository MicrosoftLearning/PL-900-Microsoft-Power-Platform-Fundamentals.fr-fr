---
lab:
  title: "Labo\_1\_: Modélisation de données"
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Labo 1 : Modélisation de données

## Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visites sur le campus sont actuellement enregistrées dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous accéderez à votre environnement et créerez une base de données Microsoft Dataverse. Vous allez également créer un modèle de données pour prendre en charge les exigences suivantes :

- R1 – Suivre les informations pour les visites planifiées sur le campus

- R2 - Enregistrer des informations de base pour identifier et suivre les visiteurs

- R3 - Planifier, enregistrer et gérer les visites

Enfin, vous importerez des échantillons de données dans Microsoft Dataverse.


## Étapes de labo de haut niveau

Pour préparer vos environnements d’apprentissage, vous devez :

- Vous référer au [document de modèle de données](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) pour la description des métadonnées (tables et relations) Vous pouvez maintenir appuyée la touche CTRL et cliquer ou faire un clic droit sur le lien pour ouvrir le document de modèle de données dans une nouvelle fenêtre.
- Créer une table Visite
- Importer les données de Visite avec une feuille de calcul Excel

## Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

## Éléments à considérer avant de commencer

- Conventions de nommage : tapez les noms sans aucune erreur.


## Exercice 1 : Créer une table

**Objectif** : Dans cet exercice, vous allez créer une table personnalisée pour Visites.


### Tâche n° 1 : créer des tables et des colonnes Visite

La table **Visite** contient des informations sur les visites du campus, y compris le visiteur, les heures prévues et les heures réelles de chaque visite.

Nous aimerions attribuer à chaque visite un numéro unique qui peut être facilement saisi et interprété par un visiteur lorsque cela lui est demandé pendant le processus d’enregistrement de la visite.

> Nous utilisons un **comportement indépendant du fuseau horaire** pour enregistrer les informations de date et d’heure, car l’heure d’une visite est toujours locale par rapport à l’emplacement du bâtiment et ne doit pas changer quand elle est affichée depuis un autre fuseau horaire.

1. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) (si ce n’est déjà fait).

1. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

1. Dans le volet de navigation de gauche, développez **Dataverse** et sélectionnez **Tables**.

1. Cliquez sur **+ Nouvelle table**.

1. Entrez **Visite** comme **Nom d’affichage**.

1. Cliquez sur **Enregistrer**.

1. Dans la section **Schéma**, sélectionnez **Colonnes**.

1. Créer une colonne Début prévu

    - Sélectionnez **+ Nouvelle colonne**.

    - Entrez **Début prévu** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans **Obligatoire**, sélectionnez **Contrainte obligatoire**.

    - Développez **Options avancées**.

    - Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

1. Créer une colonne Fin prévue

    - Cliquez sur **+ Nouvelle colonne**.

    - Entrez **Fin prévue** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans **Obligatoire**, sélectionnez **Contrainte obligatoire**.

    - Développez **Options avancées**.

    - Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

1. Créer une colonne Début réel

    - Cliquez sur **+ Nouvelle colonne**.

    - Entrez **Début réel** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans le champ **Obligatoire**, laissez comme **Facultatif**.

    - Développez **Options avancées**.

    - Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

1. Créer une colonne Fin réelle

    - Cliquez sur **+ Nouvelle colonne**.

    - Entrez **Fin réelle** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans le champ **Obligatoire**, laissez ceci comme **Optionnel**.

    - Développez **Options avancées**.

    - Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

1. Créer une colonne Code

    - Cliquez sur **+ Nouvelle colonne**.

    - Entrez **Code** comme **Nom d’affichage**.

    - Sélectionnez **Numérotation automatique** comme **Type de données**.

    - Sélectionnez **Nombre préfixé de date** pour **Type de numérotation automatique**.

    - Cliquez sur **Enregistrer**.

1. Créer une colonne de recherche Visiteur

    - Cliquez sur **+ Nouvelle colonne**.

    - Entrez **Visiteur** comme **Nom d’affichage**.

    - Sélectionnez **Recherche** comme **Type de données**.

    - Sélectionnez **Contact** comme **Table associée**.

    - Développez **Options avancées**.

    - Entrez **visitor_id** dans **nom de la relation**.

    - Cliquez sur **Enregistrer**.

## Exercice 2 : importer des données

**Objectif** : Au cours de cet exercice, vous apprendrez à importer des échantillons de données dans la base de données Dataverse.

### Tâche \#1.1 : Charger le fichier Excel sur OneDrive

1. Le fichier **Visits.xlsx** doit être stocké sur votre machine virtuelle dans **C:/LabFiles**. Si ce n’est pas le cas, téléchargez [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) si ce n’est déjà fait.

3. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

4. Cliquez sur le bouton Gaufre dans le coin supérieur gauche pour changer d’application et sélectionnez **OneDrive**. (La configuration de votre OneDrive peut prendre un moment. Cliquez sur **Votre OneDrive est prêt** lorsque vous le voyez à l’écran.)

5. Cliquez sur **Charger** dans le menu supérieur, puis sélectionnez **Fichiers**.

6. Recherchez et sélectionnez le fichier **Visits.xlsx**, puis cliquez sur **Ouvrir**.

 **Remarque :** Ce fichier se trouve dans le dossier **Tous les fichiers** de votre ordinateur.
 
### Tâche \#1.2 : Créer un flux de données

1. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) si ce n’est déjà fait.

2. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3. Dans le volet de navigation de gauche, développez **Dataverse** et sélectionnez **Tables**.

4. Recherchez et ouvrez la table **Visite** que vous avez créée dans l’exercice précédent.

5. Dans le menu en haut, sélectionnez la flèche déroulante à côté de **Importer**, puis sélectionnez **Importer les données**.

6. Dans la boîte de dialogue **Choisir une source de données**, sélectionnez **Classeur Excel**.

7. Sélectionnez l’option **Lier au fichier**. Cliquez sur **Parcourir OneDrive**. Si vous y êtes invité, connectez-vous avec vos informations d’identification Microsoft 365.

8. Sélectionnez le fichier **Visits.xlsx** qui a été chargé dans OneDrive, puis cliquez sur **Sélectionner**.

9. Cliquez sur **Suivant**.

10. Sous **Choisir les données**, cochez la case à côté du classeur Excel **Visits**.

11. Cliquez sur **Suivant**. Ne quittez pas cette page.

12. Cliquez sur **Suivant**.

13. Dans la section **Mapper les tables**, sélectionnez **Charger dans une table existante** sous **Charger les paramètres**.

14. Dans le menu déroulant **Table de destination**, sélectionnez le nom de la table qui commence par **crXXX_visit** (où XXX est un ensemble aléatoire de lettres et de chiffres)

15. Dans **Mappage de colonnes**, mappez les colonnes à leurs colonnes de destination correspondantes.

| Colonnes de destination  | Valeurs Source   |
|:---------------------|:----------------|
| crxxx_ActualEnd      | fin réelle      |
| crxxx_ActualStart    | début réel    |
| crxxx_Code           | code            |
| crxxx_Name           | name            |
| crxxx_ScheduledEnd   | fin prévue   |
| crxxx_ScheduledStart | début prévu |

16. Cliquez sur **Suivant**.

17. Sélectionnez **Actualiser manuellement**.

18. Cliquez sur **Publier**.

**Remarque :** L’importation de vos données dans votre table peut prendre plusieurs minutes. Ne vous inquiétez pas si vous recevez des erreurs, c’est normal et cela n’aura aucun impact sur le reste du cours.

### Tâche \#3 : Vérifier l’importation des données

1. Une fois vos données importées, utilisez le volet de navigation à gauche de l’écran pour resélectionner la table **Visite**.

2. Vérifiez que vous voyez les données importées sous la section **Visiter les colonnes et les données**.

Félicitations, vous avez créé une table et importé des données.
