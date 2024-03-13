---
lab:
  title: "Labo\_1\_: Modélisation de données"
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Labo 1 : Modélisation de données

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai qui ne peut pas être utilisé ni être accessible une fois la classe terminée, ni faire l’objet d’une prolongation. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est un établissement d’enseignement avec plusieurs campus et plusieurs cursus. De nombreux enseignants et administrateurs de Bellow College doivent assister à des événements et acheter des articles. Le suivi de ces dépenses a toujours été un défi en soi. 

L’administration des campus aimerait moderniser son système de notes de frais en fournissant aux employés un moyen numérique de soumettre leurs dépenses. 

Tout au long de ce cours, vous allez créer des applications et effectuer une automatisation pour permettre aux employés de Bellows College de gérer les dépenses.

Dans ce labo, vous allez créer un modèle de données pour prendre en charge les exigences suivantes :

- R1 - Suivre les informations pour les visites planifiées sur le campus.

- R2 - Enregistrer des informations de base pour identifier et suivre les visiteurs.

- R3 - Planifier, enregistrer et gérer les visites.

Enfin, vous importerez des échantillons de données dans Microsoft Dataverse.

## Étapes de labo de haut niveau

Pour préparer vos environnements d’apprentissage, vous devez :

- Vous référer au [document de modèle de données](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus Management.png) pour la description des métadonnées (tables et relations) Vous pouvez appuyer sur la touche Ctrl et la maintenir enfoncée tout en faisant un clic gauche sur le lien ou faire un clic droit sur le lien pour ouvrir le document de modèle de données dans une nouvelle fenêtre.

- Créer une table Dépenses

- Ajoutez des exemples de données. 

### Prérequis

- Conclusion du **Module 1 Lab 0 – Valider l'environnement de laboratoire **

Éléments à considérer avant de commencer

- Conventions d’affectation de noms : tapez les noms sans aucune erreur.

## Exercice 1 : Créer une table

**Objectif** : Dans cet exercice, vous allez créer une table personnalisée pour Dépenses.

### Tâche n°1 : Créer une table et des colonnes Dépenses

La table **Dépenses** contient des informations sur les dépenses individuelles qu’un employé peut soumettre, notamment le motif, le type, la date et le montant.

1. Si vous n’êtes pas déjà connecté, connectez-vous à https://make.powerapps.com

1. Dans le menu **Environnement** en haut à droite, vérifiez que votre environnement **Dev One** est sélectionné.

1. Dans le volet de navigation de gauche, sélectionnez **Tables**.

1. Sélectionnez **+ Nouvelle table**, puis choisissez **Définir les propriétés avancées**.

1. Pour **Nom d’affichage**, entrez Dépenses

1. Sélectionnez **Enregistrer**.

1. Dans la section **Schéma**, sélectionnez **Colonnes**.

### Créer une colonne Date de la dépense

1. Sélectionnez **+ Nouvelle colonne**.

1. Entrez la date de la dépense pour **Nom d’affichage**.

1. Sélectionnez **Date uniquement** pour **Type de données**.

1. Remplacez **Obligatoire** par **Contrainte obligatoire**.

1. Développez **Options avancées**.

1. Dans **Ajustement du fuseau horaire**, sélectionnez **Date uniquement**.

    >**Remarque :** Nous utilisons le comportement **Date uniquement** pour enregistrer les informations de date, car la date de la visite ne doit pas changer lorsqu’elle est vue à partir d’un autre fuseau horaire.

1. Sélectionnez **Enregistrer**.

### Créer une colonne Type de dépense

1. Sélectionnez **+ Nouvelle colonne**.

1. Entrez Type de dépense pour **Nom d’affichage**.

1. Sélectionnez **Choix** pour **Type de données**.

1. Dans **Obligatoire**, sélectionnez **Facultatif**.

1. Définissez **Synchroniser avec le choix global** sur **Oui (recommandé)**

1. Dans le champ **Synchroniser ce choix avec**, sélectionnez **Type de dépense**.

1. Définissez le champ **Choix par défaut** sur **Aucun**.

1. Sélectionnez **Enregistrer**.

### Créer une colonne Objet de la dépense

1. Sélectionnez **+ Nouvelle colonne**.

1. Entrez Objet de la dépense pour **Nom d’affichage**.

1. Sélectionnez **Choix** pour **Type de données**.

1. Dans **Obligatoire**, sélectionnez **Facultatif**.

1. Définissez **Synchroniser avec le choix global** sur **Oui (recommandé)**

1. Dans le champ **Synchroniser ce choix avec**, sélectionnez **Objet de la dépense**.

1. Définissez le champ **Par défaut** sur **Aucun**.

1. Sélectionnez **Enregistrer**.

### Créer une colonne Description de l’article

1. Sélectionnez **+ Nouvelle colonne**.

1. Entrez Description de l’article pour **Nom d’affichage**.

1. Sélectionnez **Plusieurs lignes de texte &gt; Texte brut** pour **Type de données**.

1. Sélectionnez **Enregistrer**.

### Créer une colonne Montant de la dépense

1. Sélectionnez **+ Nouvelle colonne**.

1. Entrez Montant de la dépense pour **Nom d’affichage**.

1. Sélectionnez **Monnaie locale** pour **Type de données**.

1. Sélectionnez **Enregistrer**.

 
## Exercice 2 : Saisir des données

**Objectif** : Dans cet exercice, vous entrez manuellement des exemples de données dans votre nouvelle table. 

### Tâche n°1 : Modifier les colonnes affichées

1. Connectez-vous à https://make.powerapps.com si ce n’est déjà fait

1. Sélectionnez l’environnement **Dev One** en haut à droite, si ce n’est pas déjà fait.

1. Dans le volet de navigation de gauche, sélectionnez **Tables**.

1. Ouvrez la table **Dépenses** que vous avez créée dans l’exercice précédent.

1. À côté de la colonne **Nom**, sélectionnez **+26 autres**.

1. Dans le menu qui apparaît, sélectionnez les colonnes suivantes.

    1. Date de la dépense

    2. Objet de la dépense 

    3. Type de dépense

    4. Montant de la dépense

    5. Description de l’élément

1. Cliquez sur le bouton **Enregistrer**.

## Tâche n° 2 : Ajoutez un exemple d’enregistrement.

1. Sélectionnez la **Flèche** à côté de **Modifier**. Dans le menu qui s’affiche, sélectionnez **Modifier dans un nouvel onglet**.

1. Dans la colonne **Nom**, entrez **John Doe**.

1. Dans la colonne **Date de la dépense**, entrez **xxx**.

1. Dans **Objet de la dépense**, sélectionnez **Conférence**.

1. Dans la colonne **Type de dépense**, sélectionnez **Voyage**.

1. Dans la colonne **Montant de la dépense**, entrez **750.00**.

1. Dans **Description de l’article** entrez une courte description.

1. Appuyez sur le bouton Tab pour passer à la ligne suivante et **enregistrer** l’enregistrement.

Félicitations, vous avez créé une table et ajouté des données.


