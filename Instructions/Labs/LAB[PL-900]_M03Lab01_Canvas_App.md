---
lab:
  title: "Labo\_2\_: Comment créer une application canevas"
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Labo 2 : Comment créer une application canevas

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai qui ne peut pas être utilisé ni être accessible une fois la classe terminée, ni faire l’objet d’une prolongation. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est un établissement d’enseignement avec plusieurs campus et plusieurs cursus. De nombreux enseignants et administrateurs de Bellow College doivent assister à des événements et acheter des articles. Le suivi de ces dépenses a toujours été un défi en soi. 

L’administration des campus aimerait moderniser son système de notes de frais en fournissant aux employés un moyen numérique de soumettre leurs dépenses. 

Tout au long de ce cours, vous allez créer des applications et effectuer une automatisation pour permettre aux employés de Bellows College de gérer les dépenses. 


## Étapes de labo de haut niveau

Nous allons suivre le plan ci-dessous pour concevoir l’application canevas :

- Créer une application canevas de notes de frais 

- Configurer l’affichage des notes de frais sur l’écran de navigation

- Apporter des modifications de base à l’application

- Tester les fonctionnalités de l’application

## Prérequis

- Participation au **Module 1 Labo 0 – Valider l’environnement de labo**

## Exercice 1 : Créer une application canevas Notes de frais

### Objectif : Dans cet exercice, vous allez créer une application canevas en vous connectant à une table Expense Reports (Rapports de dépenses).

### Tâche n°1 : Créer l’application Notes de frais

1. Accédez à `https://make.powerapps.com`.

1. Vous devrez peut-être vous réauthentifier. Sélectionnez **Se connecter** et suivez les instructions si nécessaire.

1. Sélectionnez l’environnement **Dev One** en haut à droite, si ce n’est pas déjà fait.

1. Sélectionnez **+ Créer** dans le volet de navigation gauche de l’écran. Sous la section **Démarrer à partir de**, sélectionnez **Dataverse**.

1. Sélectionnez votre connexion Dataverse.

    >**Remarque** : Si une connexion Dataverse n’existe pas :

    >   - Sélectionnez **+ Nouvelle connexion**.

    >   - Localisez **Microsoft Dataverse**.

    >   - Sélectionnez **Créer**

    >   - **Connectez-vous** et sélectionnez **Autoriser l’accès**.

1. Recherchez et sélectionnez la table **Notes de frais**.

1. Cliquez sur le bouton **Connecter** en bas à droite.

1. Une fois votre application créée, dans l’écran Bienvenue dans Power Apps Studio, sélectionnez **Ne plus afficher ce message**, puis sélectionnez **Ignorer**.

1. Dans le concepteur d’applications, sélectionnez le bouton **Afficher un aperçu de l’application** (icône Lecture) dans la barre de commandes. (Vous pouvez aussi prévisualiser l’application en appuyant sur F5.) Parcourez l’application pour constater qu’elle est prête à l’emploi.

1. Fermez l’aperçu de l’application en sélectionnant le **X** en haut à droite de l’écran.

Félicitations, vous avez créé une application Power Apps à partir d’une table Dataverse. L’étape suivante du processus consiste à adapter l’application pour qu’elle reflète votre établissement. La série suivante d’étapes vous guidera tout au long des tâches nécessaires pour personnaliser davantage l’application.

### Tâche 2 : Modifier l’application nouvellement créée et lui appliquer un thème

Dans cette tâche, vous allez personnaliser le texte d’en-tête de chacun des trois écrans de votre application (Parcourir, Détails et Modifier) et modifier le thème de l’application.

1. Vous êtes sur l’écran Parcourir. Sélectionnez l’étiquette **Notes de frais** à l’écran.

1. À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle ** Texte** par Mes notes de frais

1. Dans l’onglet **Propriétés**, modifiez la **Taille de la police** en **24**.

1. Sélectionnez l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Parcourir.

1. En utilisant l’**arborescence** dans le volet de navigation gauche, sélectionnez **DetailScreen1**.

1. Sélectionnez l’étiquette **Notes de frais** à l’écran.

1. À droite de l’écran, sous l’onglet **Propriétés**, remplacez la propriété du contrôle **Texte** par Détails de la note

1. Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Détails.

1. En utilisant l’**arborescence** dans le volet de navigation gauche, sélectionnez **EditScreen1** (il peut être nécessaire de faire défiler vers le bas pour voir cette option dans l’arborescence).

1. Sélectionnez l’étiquette **Notes de frais** à l’écran.

1. À droite de l’écran, sous l’onglet **Propriétés**, remplacez le texte dans la propriété du contrôle **Texte** par Modifier les détails

1. Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Modifier.

1. En utilisant l’**arborescence** dans le volet de navigation gauche, sélectionnez **BrowseScreen1**.

1. Dans la barre d’outils de commande, sélectionnez le bouton **Thème** puis, dans la liste qui s’affiche, sélectionnez la couleur de thème **Rouge**.

### Tâche n°3 : Tester votre application Notes de frais

Dans cette tâche, vous allez tester votre nouvelle application.

1. Une fois votre application ouverte dans le Concepteur d’application, sélectionnez **Paramètres** (vous devrez peut-être sélectionner … pour faire apparaître l’icône Paramètres). Dans la section **Général**, remplacez le nom de votre application par Application Notes de frais, sélectionnez **X** pour fermer l’écran des paramètres, puis sélectionnez **Enregistrer**.

1. Dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

1. Dans le concepteur d’applications, sélectionnez le bouton **Afficher un aperçu de l’application** (icône Lecture) dans la barre de commandes. (Vous pouvez aussi prévisualiser l’application en appuyant sur F5.)

1. Une fois l’application ouverte, dans le champ **Éléments de recherche**, entrez le texte Déplacement (notez la façon dont les éléments de la galerie sont filtrés en fonction de ce que vous tapez dans le champ de recherche).

1. Une fois que l’enregistrement **Déplacement pour la conférence Power Platform** apparaît, sélectionnez une ligne afin d’ouvrir l’écran Détails de cette Dépense.
 
    >**Remarque** : Si plusieurs enregistrements Déplacement pour la conférence Power Platform s’affichent, sélectionnez l’un d’entre eux.

1. Pour modifier l’enregistrement, sélectionnez l’**icône crayon** dans le coin supérieur droit de l’application.

1. Vous pouvez modifier le **Nom de la note** ici et sélectionner l’icône **Coche** en haut à droite pour enregistrer la modification.

1. En haut à droite de l’écran, sélectionnez l’icône **X** pour fermer le mode Aperçu et revenir à l’éditeur de l’application canevas.

Félicitations ! Vous avez créé et configuré votre première application canevas.

 
