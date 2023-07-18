---
lab:
  title: "Labo\_1\_: Modélisation de données"
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Labo 1 : Modélisation de données

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visites sur le campus sont actuellement enregistrées dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous allez créer un modèle de données pour prendre en charge les exigences suivantes :

- R1 - Suivre les informations pour les visites planifiées sur le campus.

- R2 - Enregistrer des informations de base pour identifier et suivre les visiteurs.

- R3 - Planifier, enregistrer et gérer les visites.

Enfin, vous importerez des échantillons de données dans Microsoft Dataverse.

Étapes de labo de haut niveau

Pour préparer vos environnements d’apprentissage, vous devez :

- Vous référer au [document de modèle de données](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) pour la description des métadonnées (tables et relations) Vous pouvez appuyer sur la touche Ctrl et la maintenir enfoncée tout en faisant un clic gauche sur le lien ou faire un clic droit sur le lien pour ouvrir le document de modèle de données dans une nouvelle fenêtre.
- Créer une table Visite
- Importer les données de Visite avec une feuille de calcul Excel


## Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

Éléments à considérer avant de commencer

- Conventions de nommage : tapez les noms sans aucune erreur.

Exercice 1 : Créer une table

**Objectif** : Dans cet exercice, vous allez créer une table personnalisée pour Visites.

Tâche n° 1 : Créer une table Visit et des colonnes

La table **Visite** contient des informations sur les visites du campus, y compris le visiteur, les heures prévues et les heures réelles de chaque visite.

Nous aimerions attribuer à chaque visite un numéro unique qui peut être facilement saisi et interprété par un visiteur lorsque cela lui est demandé pendant le processus d’enregistrement de la visite.

1.  Si vous n’êtes pas déjà connecté, connectez-vous à <https://make.powerapps.com> 

1.  Dans le menu **Environnement** en haut à droite, vérifiez que votre environnement **Exercice pratique** est sélectionné. 

1.  Dans le volet de navigation de gauche, sélectionnez **Tables**.

1.  Sélectionnez **+ Nouvelle table** et choisissez **+ Nouvelle table**. 

1.  Pour **Nom d’affichage**, entrez `Visit`

1.  Sélectionnez **Enregistrer**. 

1.  Dans la section **Schéma**, sélectionnez **Colonnes**. 

# Créer une colonne Début prévu

1.  Sélectionnez **+ Nouvelle colonne**. 

1.  Entrez `Scheduled Start` comme **Nom d’affichage**. 

1.  Sélectionnez **Date et heure** comme **Type de données**. 

1.  Remplacez **Obligatoire** par **Contrainte obligatoire**. 

1.  Développez **Options avancées**. 

1.  Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**. 

    > **Remarque :** Nous utilisons un comportement **indépendant du fuseau horaire** pour enregistrer les informations de date et d’heure, car l’heure d’une visite est toujours locale par rapport à l’emplacement du bâtiment et ne doit pas changer quand elle est affichée depuis un autre fuseau horaire. 

1.  Sélectionnez **Enregistrer**. 

# Créer une colonne Fin prévue

1.  Sélectionnez **+ Nouvelle colonne**. 

1.  Entrez `Scheduled End` comme **Nom d’affichage**.

1.  Sélectionnez **Date et heure** comme **Type de données**.

1.  Dans **Obligatoire**, sélectionnez **Contrainte obligatoire**.

1.  Développez **Options avancées**.

1.  Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**.

1.  Sélectionnez **Enregistrer**. 

# Créer une colonne Début réel

1.  Sélectionnez **+ Nouvelle colonne**. 

1.  Entrez `Actual Start` comme **Nom d’affichage**.

1.  Sélectionnez **Date et heure** comme **Type de données**.

1.  Dans le champ **Obligatoire**, laissez ceci comme **Optionnel**.

1.  Développez **Options avancées**.

1.  Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**. 

1.  Sélectionnez **Enregistrer**. 

# Créer une colonne Fin réelle

1.  Sélectionnez **+ Nouvelle colonne**.

1.  Entrez **Fin réelle** comme **Nom d’affichage**.

1.  Sélectionnez **Date et heure** comme **Type de données**.

1.  Dans le champ **Obligatoire**, laissez ceci comme **Optionnel**.

1.  Développez **Options avancées**.

1.  Dans **Définition du fuseau horaire**, sélectionnez **Indépendant du fuseau horaire**.

1.  Sélectionnez **Enregistrer**.

# Créer une colonne Code

1.  Sélectionnez **+ Nouvelle colonne**.

1.  Entrez `Code` comme **Nom d’affichage**.

1.  Sélectionnez **Numérotation automatique** comme **Type de données**.

1.  Sélectionnez **Nombre préfixé de date** pour **Type de numérotation automatique**.

1.  Sélectionnez **Enregistrer**. 

# Créer une colonne de recherche Visiteur

1.  Sélectionnez **+ Nouvelle colonne**.

1.  Entrez `Visitor` comme **Nom d’affichage**.

1.  Sélectionnez **Recherche** comme **Type de données**. 

1.  Sélectionnez **Contact** comme **Table associée**. 

1.  Développez **Options avancées**. 

1.  Entrez `visitor_id` dans **nom de la relation**. 

1.  Sélectionnez **Enregistrer**.


Exercice 2 : importer des données

**Objectif** : Au cours de cet exercice, vous apprendrez à importer des échantillons de données dans la base de données Dataverse.

### Tâche n° 1 : Charger le fichier Excel sur OneDrive

1.  Le fichier **Visits.xlsx** doit être stocké sur votre machine virtuelle dans **C:/LabFiles**. Si ce n’est pas le cas, téléchargez [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2.  Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) si ce n’est déjà fait. 

3.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

4.  Sélectionnez le bouton Gaufre dans le coin supérieur gauche pour changer d’application et sélectionnez **OneDrive**. (La configuration de votre OneDrive peut prendre un moment. Cliquez sur **Votre OneDrive est prêt** lorsque vous le voyez à l’écran.)

5.  Sélectionnez **Charger** dans le menu supérieur, puis **Fichiers**.

6.  Recherchez et sélectionnez le fichier **Visits.xlsx**, puis sélectionnez **Ouvrir**.

    > **Remarque :** Ce fichier se trouve dans le dossier **Tous les fichiers** de votre ordinateur.


### Tâche n° 2 : Créer un flux de données

1.  Si vous n’êtes pas déjà connecté, connectez-vous à <https://make.powerapps.com> 

2.  Dans le menu **Environnement** en haut à droite, vérifiez que votre environnement **Exercice pratique** est sélectionné. 

3.  Dans le volet de navigation de gauche, sélectionnez **Tables**. 

4.  Ouvrez la table **Visit** que vous avez créée dans l’exercice précédent. 

5.  Dans le menu situé en haut, sélectionnez **Importer** > Importer des données**.

6.  Dans la boîte de dialogue **Choisir une source de données**, sélectionnez **Classeur Excel**.

7.  Sélectionnez l’option **Lier au fichier**. Sélectionnez **Parcourir OneDrive**. Si vous y êtes invité, connectez-vous avec vos informations d’identification Microsoft 365. Configurez le navigateur pour qu’il autorise toujours les fenêtres contextuelles. 

8.  Sélectionnez le fichier  **Visits.xlsx** qui a été chargé sur OneDrive dans la tâche précédente. 

9.  Sélectionnez **Suivant**. 

10. Sous **Choisir les données**, cochez la case à côté du classeur Excel **Visits**. 

11. Sélectionnez **Suivant**. Ne quittez pas cette page.

12. Sélectionnez **Suivant**. 

13. Dans la section **Mapper les tables**, sous **Charger les paramètres**, sélectionnez **Charger dans une table existante**. 

14. Dans le menu déroulant **Table de destination**, sélectionnez la table **crXXX_Visit** (où XXX est un ensemble aléatoire de lettres et de chiffres).

15. Dans **Mappage de colonnes**, mappez les colonnes à leurs colonnes de destination correspondantes.

    | Colonnes de destination  | Valeurs Source   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | fin réelle      |
    | crxxx_ActualStart    | début réel    |
    | crxxx_Code           | code            |
    | crxxx_Name           | name            |
    | crxxx_ScheduledEnd   | fin prévue   |
    | crxxx_ScheduledStart | début prévu |

16. Sélectionnez **Suivant**. 

17. Sélectionnez **Actualiser manuellement**. 

18. Sélectionnez **Publier**. 

    > **Remarque :** L’importation de vos données dans votre table peut prendre plusieurs minutes. Ne vous inquiétez pas si vous recevez des erreurs, c’est normal et cela n’aura aucun impact sur le reste du cours.


Tâche n°3 : Vérifier une importation de données

1.  Une fois vos données importées, utilisez le volet de navigation à gauche de l’écran pour sélectionner **Tables** et ouvrir la table **Visit**.

2.  Vérifiez que vous voyez les données importées sous la section **Visiter les colonnes et les données**.

Félicitations, vous avez créé une table et importé des données.
