---
lab:
  title: 'Labo 2 : Comment créer une application canevas'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 24d99d14079d40f74a43ed0de64dd6ae5d7046c7
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810918"
---
# <a name="module-3-get-started-with-power-apps"></a>Module 3 : Bien démarrer avec Power Apps
## <a name="lab-how-to-build-a-canvas-app"></a>Labo : Comment créer une application canevas

# <a name="scenario"></a>Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visites sur le campus sont actuellement enregistrées dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

Actuellement, l’administration du campus utilise une feuille de calcul Excel pour suivre l’inscription des visiteurs. Elle souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

# <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Nous allons suivre le plan ci-dessous pour concevoir l’application canevas :

-   Créer une application canevas à partir de données dans la table Visite

-   Configurer l’affichage des visites sur l’écran de navigation

-   Apporter des modifications de base à l’application

-   Tester les fonctionnalités de l’application

## <a name="prerequisites"></a>Prérequis

-   Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

# <a name="exercise-1-create-visits-app"></a>Exercice \#1 : Créer l’application Visites

**Objectif** : Dans cet exercice, vous allez créer une application canevas en connectant la table Visites Initiales que vous avez créée précédemment.

## <a name="task-1-create-a-visits-app"></a>Tâche \#1 : Créer une application Visites

1.  Accédez à <https://make.powerapps.com>. Vous devrez peut-être vous authentifier à nouveau. Cliquez sur **Se connecter** et suivez les instructions si nécessaire.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Si nécessaire, cliquez sur l’icône **Accueil** à gauche de l’écran. Sous la section **Démarrer à partir de**, sélectionnez **Dataverse**.

4.  Sélectionnez votre connexion Dataverse. 

    >   **REMARQUE :** *Si une connexion Dataverse n’existe pas :*
    >   -   Sélectionnez **Nouvelle connexion**.
    >   -   Localisez **Microsoft Dataverse**.
    >   -   Cliquez sur **Créer**

5.  Recherchez et sélectionnez la table **Visites** que vous avez créée dans le labo précédent.

6.  Cliquez sur le bouton **Connecter** en bas à droite.

7.  Une fois votre application créée, dans l’écran Bienvenue de Power Apps Studio, cochez la case **Ne plus afficher ce message**, puis sélectionnez **Ignorer**.

8.  Une fois l’application créée, elle doit ressembler à l’image ci-dessous.

![Application canevas créée à partir des données Visite.](media/2-canvas-app-from-data.png)

9. Dans le Concepteur d’application, sélectionnez le bouton de **prévisualisation de l’application** (icône Lecture) dans la barre de commandes. *(Vous pouvez également appuyer sur la touche F5 de votre clavier pour prévisualiser l’application.)* Parcourez l’application pour constater qu’elle est application est prête à l'emploi.

10. Fermez l’aperçu de l’application en sélectionnant le **X** en haut à droite de l’écran.

Félicitations, vous avez créé une application Power Apps à partir d’une table Dataverse. L’étape suivante du processus consiste à personnaliser l’application pour refléter la stratégie de marque de votre établissement. La série suivante d’étapes vous guidera tout au long des tâches nécessaires pour personnaliser davantage l’application.

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tâche \#2 : Modifier l’application nouvellement créée et lui appliquer un thème

Dans cette tâche, vous allez personnaliser le texte d’en-tête de chacun des trois écrans de votre application (Parcourir, Détails et Modifier) et modifier le thème de l’application.

1.  Vous êtes sur l’écran Parcourir. Sélectionnez l’étiquette **Visites** à l’écran.

3.  À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle  **Texte** par « **Visites de Bellows College** ».

4. Dans les propriétés, définissez la **Taille de police** sur **24**.

4.  Cliquez sur l’arrière-plan vide pour afficher le texte mis à jour sur votre écran Parcourir.

5.  Dans le volet de navigation de gauche, sélectionnez **DetailScreen1**.

5.  Sélectionnez l’étiquette **Visites** à l’écran.

6.  À droite de l’écran, sous l’onglet Propriétés, remplacez la propriété du contrôle  **Texte** par « **Détails de la visite** ».

7.  Cliquez sur l’arrière-plan vide pour afficher le texte mis à jour sur votre écran Détails.

8.  En utilisant les options de navigation sur la gauche, sélectionnez **EditScreen1** (vous devrez peut-être faire défiler l'écran pour voir cette option dans l’arborescence).

9.  Sélectionnez l’étiquette **Visites** à l’écran.

10.  À droite de l’écran, sous l’onglet Propriétés, remplacez le texte Table1 dans la propriété du contrôle  **Texte** par « **Modifier les détails** ».

11.  Cliquez sur l’arrière-plan vide pour afficher le texte mis à jour sur votre écran Modifier.

12. Dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

13. Dans la barre d’outils de commande, sélectionnez le bouton **Thème** et, dans la liste qui s’affiche, sélectionnez la couleur de thème **Rouge**.

## <a name="task-3-test-your-visits-app"></a>Tâche \#3 : Tester l’application Visites

Dans cette tâche, vous allez tester votre nouvelle application.

1.  Ouvrez votre application dans le Concepteur d’application, sélectionnez **Fichier**, remplacez le nom de votre application par **Application Visites**, puis sélectionnez **Enregistrer**.

2.  Cliquez sur la flèche **retour** pour revenir à votre application.

3.  Dans le volet de navigation de gauche, sélectionnez **BrowseScreen1**.

4.  Dans le Concepteur d’application, sélectionnez le bouton de **prévisualisation de l’application** (icône Lecture) dans la barre de commandes. *(Vous pouvez également appuyer sur la touche F5 de votre clavier pour prévisualiser l’application.)*

4.  Une fois l’application ouverte, dans le champ **Éléments de recherche**, entrez le texte **Maria**
     *(Notez la façon dont les éléments de la galerie sont filtrés en fonction de ce que vous tapez dans le champ de recherche.)*

5.  Une fois l’enregistrement **Contoso Suites** pour **Maria Campbell** affiché, cliquez sur la ligne pour accéder aux détails de cette visite. (**Remarque** : *Si plusieurs enregistrements Contoso Suites pour Maria Campbell sont affichés, sélectionnez-en un.* )

6.  Pour modifier l’enregistrement, sélectionnez l’**icône crayon** dans le coin supérieur droit de l’application.

7.  Vous pouvez modifier ici le nom de la visite et cliquer sur l'icône en forme de coche en haut à droite pour enregistrer la modification.

8.  En haut à droite de l’écran, cliquez sur l’icône **X** pour revenir à l’éditeur de l’application canevas.

Félicitations ! Vous avez créé et configuré votre première application canevas.

# <a name="challenges"></a>Défis

-   Ajoutez les colonnes suivantes aux formulaires dans DetailScreen1 et EditScreen1 : Début réel, Fin réelle, Code, Début prévu et Fin prévue
