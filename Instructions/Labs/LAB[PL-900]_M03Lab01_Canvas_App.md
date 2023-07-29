---
lab:
  title: "Labo\_2\_: Comment créer une application canevas"
  module: 'Module 3: Get started with Power Apps'
---

# Labo 2 : Comment créer une application canevas

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visites sur le campus sont actuellement enregistrées dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

Actuellement, l’administration du campus utilise une feuille de calcul Excel pour suivre l’inscription des visiteurs. Elle souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.


## Étapes de labo de haut niveau

Nous allons suivre le plan ci-dessous pour concevoir l’application canevas :

- Créer une application canevas à partir de données dans la table Visite

- Configurer l’affichage des visites sur l’écran de navigation

- Apporter des modifications de base à l’application

- Tester les fonctionnalités de l’application

## Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**
- Participation au **Module 2 Labo 1 : modélisation des données**


## Exercice 1 : créer une application canevas Visites

**Objectif :** Dans cet exercice, vous allez créer une application canevas en connectant la table Visits que vous avez créée précédemment.


### Tâche no 1 : créer l’application Visites

1.  Accédez à <https://make.powerapps.com>. Vous devrez peut-être vous authentifier à nouveau. Sélectionnez **Se connecter** et suivez les instructions si nécessaire.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Si nécessaire, sélectionnez l’icône **Accueil** à gauche de l’écran. Sous la section **Démarrer à partir de**, sélectionnez **Dataverse**.

4.  Sélectionnez votre connexion Dataverse.

    > **Remarque :** *S’il n’existe pas de connexion Dataverse :*
    > - Sélectionnez **+ Nouvelle connexion**.
    > - Localisez **Microsoft Dataverse**.
    > - Sélectionnez **Créer**

5.  Recherchez et sélectionnez la table **Visites** que vous avez créée dans le labo précédent.

6.  Cliquez sur le bouton **Connecter** en bas à droite.

7.  Une fois votre application créée, dans l’écran Bienvenue dans Power Apps Studio, cochez la case **Ne plus afficher ce message**, puis sélectionnez **Ignorer**.

8.  Une fois l’application créée, elle doit ressembler à l’image ci-dessous.

    ![Application canevas créée à partir des données Visite.](media/2-canvas-app-from-data.png)

9. Dans le concepteur d’applications, sélectionnez le bouton **Afficher un aperçu de l’application** (icône Lecture) dans la barre de commandes. *(Vous pouvez également appuyer sur la touche F5 de votre clavier pour prévisualiser l’application.)* Parcourez l’application pour constater qu’elle est application est prête à l'emploi.

10. Fermez l’aperçu de l’application en sélectionnant le **X** en haut à droite de l’écran.

Félicitations, vous avez créé une application Power Apps à partir d’une table Dataverse. L’étape suivante du processus consiste à personnaliser l’application pour refléter la stratégie de marque de votre établissement. La série suivante d’étapes vous guidera tout au long des tâches nécessaires pour personnaliser davantage l’application.


### Tâche \#2 : Modifier l’application nouvellement créée et lui appliquer un thème

Dans cette tâche, vous allez personnaliser le texte d’en-tête de chacun des trois écrans de votre application (Parcourir, Détails et Modifier) et modifier le thème de l’application. 

1.  Vous êtes sur l’écran Parcourir. Sélectionnez l’étiquette **Visites** à l’écran.

1.  À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle **Texte** par `Bellows College Visits`

1.  Dans les propriétés, définissez la **Taille de police** sur **24**. 

1.  Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Parcourir. 

1.  À l’aide de l’arborescence dans le volet de navigation de gauche, sélectionnez **DetailScreen1**. 

1.  Sélectionnez l’étiquette **Visites** à l’écran.

1.  À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle **Texte** par `Visit Details`

1.  Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Détails.

1.  À l’aide de l’arborescence dans le volet de navigation de gauche, sélectionnez **EditScreen1** (vous devrez peut-être faire défiler l’écran pour afficher cette option dans l’arborescence).

1.  Sélectionnez l’étiquette **Visites** à l’écran.

1.  À droite de l’écran, sous l’onglet Propriétés, remplacez le texte dans la propriété du contrôle **Texte** par `Edit Details`

1.  Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Modifier.

1. À l’aide de l’arborescence dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

1. Dans la barre d’outils de commande, sélectionnez le bouton **Thème** et, dans la liste qui s’affiche, sélectionnez la couleur de thème **Rouge**.


### Tâche \#3 : Tester l’application Visites

Dans cette tâche, vous allez tester votre nouvelle application.

1.  Une fois que votre application s’ouvre dans le Concepteur d’applications, sélectionnez **Paramètres**. Dans la section **Général**, remplacez le nom de votre application par `Visits App`, sélectionnez **X** pour fermer l’écran des paramètres, puis sélectionnez **Enregistrer**.

2.  Cliquez sur la flèche **retour** pour revenir à votre application.

3.  Dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

4.  Dans le concepteur d’applications, sélectionnez le bouton **Afficher un aperçu de l’application** (icône Lecture) dans la barre de commandes. *(Vous pouvez également appuyer sur la touche F5 de votre clavier pour prévisualiser l’application.)*

4.  Une fois l’application ouverte, dans le champ **Éléments de recherche**, entrez le texte `Maria`
     *(Notez la façon dont les éléments de la galerie sont filtrés en fonction de ce que vous tapez dans le champ de recherche.)*

5.  Une fois l’enregistrement **Contoso Suites** pour **Maria Campbell** affiché, sélectionnez une ligne pour ouvrir l’écran Détails de cette visite. (**Remarque** : *Si plusieurs enregistrements Contoso Suites pour Maria Campbell sont affichés, sélectionnez-en un.* )

6.  Pour modifier l’enregistrement, sélectionnez l’**icône crayon** dans le coin supérieur droit de l’application.

7.  Vous pouvez modifier ici le **Nom de la visite** et sélectionner l’icône **Coche** en haut à droite pour enregistrer la modification.

8.  En haut à droite de l’écran, sélectionnez l’icône **X** pour fermer le mode Aperçu et revenir à l’éditeur de l’application canevas.

Félicitations ! Vous avez créé et configuré votre première application canevas.


