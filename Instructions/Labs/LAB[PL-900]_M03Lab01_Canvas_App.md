---
lab:
  title: "Labo\_2\_: Comment créer une application canevas"
  module: 'Module 3: Get started with Power Apps'
---

# <a name="lab-2-how-to-build-a-canvas-app"></a>Labo 2 : Comment créer une application canevas

## <a name="scenario"></a>Scénario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Currently, campus administration is leveraging an Excel spreadsheet to track visitor registration. They would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

## <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Nous allons suivre le plan ci-dessous pour concevoir l’application canevas :

- Créer une application canevas à partir de données dans la table Visite

- Configurer l’affichage des visites sur l’écran de navigation

- Apporter des modifications de base à l’application

- Tester les fonctionnalités de l’application

## <a name="prerequisites"></a>Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**
- Participation au **Module 2 Labo 1 : modélisation des données**

## <a name="exercise-1-create-visits-canvas-app"></a>Exercice 1 : créer une application canevas Visites

**Objectif :** dans cet exercice, vous allez créer une application canevas en connectant la table Visites que vous avez créée précédemment.

### <a name="task-1-create-the-visits-app"></a>Tâche no 1 : créer l’application Visites

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  If necessary, click the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> icon on the left side of the screen. Under the <bpt id="p1">**</bpt>Start from<ept id="p1">**</ept> section, select <bpt id="p2">**</bpt>Dataverse<ept id="p2">**</ept>.

4.  Sélectionnez votre connexion Dataverse.

    > **REMARQUE :** *Si une connexion Dataverse n’existe pas :*
    > - Sélectionnez **Nouvelle connexion**.
    > - Localisez **Microsoft Dataverse**.
    > - Cliquez sur **Créer**

5.  Recherchez et sélectionnez la table **Visites** que vous avez créée dans le labo précédent.

6.  Cliquez sur le bouton **Connecter** en bas à droite.

7.  Une fois votre application créée, dans l’écran Bienvenue de Power Apps Studio, cochez la case **Ne plus afficher ce message**, puis sélectionnez **Ignorer**.

8.  Une fois l’application créée, elle doit ressembler à l’image ci-dessous.

![Application canevas créée à partir des données Visite.](media/2-canvas-app-from-data.png)

9. Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus.

10. Fermez l’aperçu de l’application en sélectionnant le **X** en haut à droite de l’écran.

Les visites sur le campus sont actuellement enregistrées dans des journaux papier.

### <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tâche \#2 : Modifier l’application nouvellement créée et lui appliquer un thème

Dans cette tâche, vous allez personnaliser le texte d’en-tête de chacun des trois écrans de votre application (Parcourir, Détails et Modifier) et modifier le thème de l’application.

1.  Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

1.  À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle  **Texte** par « **Visites de Bellows College** ».

1. Dans les propriétés, définissez la **Taille de police** sur **24**.

1.  Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Parcourir.

1.  À l’aide de l’arborescence dans le volet de navigation de gauche, sélectionnez **DetailScreen1**.

1.  Sélectionnez l’étiquette **Visites** à l’écran.

1.  À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle  **Texte** par « **Détails de la visite** ».

1.  Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Détails.

1.  À l’aide de l’arborescence dans le volet de navigation de gauche, sélectionnez **EditScreen1** (vous devrez peut-être faire défiler l’écran pour afficher cette option dans l’arborescence).

1.  Sélectionnez l’étiquette **Visites** à l’écran.

1.  À droite de l’écran, sous l’onglet Propriétés, remplacez le texte Table1 dans la propriété du contrôle  **Texte** par « **Modifier les détails** ».

1.  Cliquez sur l’arrière-plan vide de l’écran pour afficher le texte mis à jour sur votre écran Modifier.

1. À l’aide de l’arborescence dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

1. Dans la barre d’outils de commande, sélectionnez le bouton **Thème** et, dans la liste qui s’affiche, sélectionnez la couleur de thème **Rouge**.

### <a name="task-3-test-your-visits-app"></a>Tâche \#3 : Tester l’application Visites

Dans cette tâche, vous allez tester votre nouvelle application.

1.  Ouvrez votre application dans le Concepteur d’application, sélectionnez **Fichier**, remplacez le nom de votre application par **Application Visites**, puis sélectionnez **Enregistrer**.

2.  Cliquez sur la flèche **retour** pour revenir à votre application.

3.  Dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

4.  In the app designer, select the <bpt id="p1">**</bpt>preview the app<ept id="p1">**</ept> button (Play icon) on the command bar. <bpt id="p1">*</bpt>(You can also preview the app by pressing F5 on your keyboard.)<ept id="p1">*</ept>

4.  Une fois l’application ouverte, dans le champ **Éléments de recherche**, entrez le texte **Maria**
     *(Notez la façon dont les éléments de la galerie sont filtrés en fonction de ce que vous tapez dans le champ de recherche.)*

5.  Actuellement, l’administration du campus utilise une feuille de calcul Excel pour suivre l’inscription des visiteurs.

6.  Pour modifier l’enregistrement, sélectionnez l’**icône crayon** dans le coin supérieur droit de l’application.

7.  Vous pouvez modifier ici le nom de la visite et cliquer sur l'icône en forme de coche en haut à droite pour enregistrer la modification.

8.  En haut à droite de l’écran, cliquez sur l’icône **X** pour revenir à l’éditeur de l’application canevas.

Elle souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

## <a name="challenges"></a>Défis

- Ajoutez les colonnes suivantes aux formulaires dans DetailScreen1 et EditScreen1 : Début réel, Fin réelle, Code, Début prévu et Fin prévue