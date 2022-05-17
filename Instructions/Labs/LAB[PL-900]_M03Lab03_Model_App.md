---
lab:
  title: 'Labo 3 : Comment créer une application pilotée par modèle'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 56a807c49479c245f95e3af9566450651bcc3ebb
ms.sourcegitcommit: 99acd470de1164d438d7c4794faa28d6489c39db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "144812446"
---
# <a name="module-3-get-started-with-power-apps"></a>Module 3 : Bien démarrer avec Power Apps
## <a name="lab-how-to-build-a-model-driven-app"></a>Labo : Comment créer une application pilotée par modèle

# <a name="scenario"></a>Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visiteurs du campus sont actuellement enregistrés dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous allez créer une application Power Apps pilotée par modèle pour permettre au personnel de bureau du campus de gérer les enregistrements de visites sur l’ensemble du campus.

# <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Dans le cadre de la création de l’application basée sur un modèle, vous effectuerez les opérations suivantes :

-   Créer une nouvelle application pilotée par modèle nommée Gestion du campus

-   Modifier la navigation de l’application pour référencer les tables requises

-   Personnaliser les formulaires et les vues des tables requises pour l’application

Nous travaillerons avec les composants suivants :

-   **Vues** : Les vues permettent à l’utilisateur d’afficher les données existantes dans la table des formulaires.

-   **Formulaires** : C’est là que l’utilisateur crée ou met à jour de nouvelles lignes dans les tables.

Les deux seront intégrés à l’application basée sur un modèle, pour une meilleure expérience utilisateur.

## <a name="prerequisites"></a>Prérequis

-   Participation au **Module 0 - Labo : Valider l’environnement de labo**

-   Participation au **Module 2 - Labo : Modélisation des données**

-   Participation au **Module 3 - Labo : Comment générer une application canevas**

## <a name="things-to-consider-before-you-begin"></a>Éléments à considérer avant de commencer

-   Quels changements devons-nous apporter pour améliorer l’expérience utilisateur ?

-   Que devrions-nous inclure dans une application pilotée par modèle d’après le modèle de données que nous avons créé ?

-   Quelles personnalisations peuvent être effectuées sur le plan du site d’une application pilotée par modèle ?

# <a name="exercise-1-customize-views-and-forms"></a>Exercice \#1 : Personnaliser les vues et les formulaires

**Objectif** : Au cours de cet exercice, vous apprendrez à personnaliser les vues et les formulaires des tables personnalisées qui seront utilisées dans l’application pilotée par modèle.

## <a name="task-1-edit-visit-form"></a>Tâche \#1 : Modifier le formulaire de visite

1.  Connectez-vous à <https://make.powerapps.com> si vous n’êtes pas encore connecté.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Dans le volet de navigation de gauche, développez **Dataverse**, sélectionnez **Tables**, puis cliquez pour ouvrir votre table **Visite**.
>   Si vous ne voyez pas la table Visite, vérifiez que vous êtes dans l’environnement approprié (étape 2).

4.  Sélectionnez l’onglet **Formulaires**, puis cliquez pour ouvrir le formulaire Informations de type **Principal**.
>   **IMPORTANT :** *Par défaut, tous les formulaires sont nommés Informations. Vérifiez donc que le formulaire que vous sélectionnez est de type* **Principal** *et pas autre chose.*
Par défaut, le formulaire comporte deux champs : Nom (champ principal) et Propriétaire.

5.  À droite de l’écran dans le volet Propriétés, sélectionnez le champ **Nom complet**, puis remplacez-le par **Informations principales**.

6.  Dans le menu en haut de l’écran, sélectionnez **+ Champ de formulaire** et ajoutez les champs suivants sous le champ **Propriétaire** en faisant glisser les colonnes dans le formulaire ou simplement en cliquant sur les noms des colonnes appropriées :

    1.  **Visiteur**

    2.  **Début prévu**

    3.  **Fin prévue**

    4.  **Début réel**

    5.  **Fin réelle**

7.  Faites glisser la colonne **Code** et déposez-la dans l’en-tête du formulaire.

    >   L’en-tête est la zone supérieure droite du formulaire. Vous devrez peut-être réduire le panneau Propriétés sur le côté droit de l’écran pour voir le champ sur le formulaire.

8.  En gardant le champ **Code** sélectionné, cochez la case en regard de **Lecture seule** dans le panneau Propriétés à droite de l’écran.

9.  Sélectionnez le champ **Propriétaire**. Dans le volet Propriétés, remplacez **Étiquette** par **Hôte**

10.  Cliquez sur **Enregistrer** en haut à droite et attendez la fin de l’enregistrement.

11.  Cliquez sur **Publier** en haut à droite et attendez la fin de la publication.

12.  Si la vue d’édition est ouverte dans un nouvel onglet ou une nouvelle fenêtre de navigateur, fermez cette vue. Sinon, cliquez sur **Retour** en haut à gauche de l’écran. Vous devez maintenant revenir à l’onglet formulaires de tables de visite.

## <a name="task-2-edit-active-visits-view"></a>Tâche \#2 : Modifier la vue Visites actives

Dans cette tâche, nous allons modifier la vue des visites actives par défaut et créer une nouvelle vue pour les visites du jour.

1.  Sélectionnez l’onglet **Vues** et cliquez pour ouvrir la vue **Visites actives**.

2.  Ajoutez les champs suivants à la vue en cliquant sur ou en faisant glisser-déposer les champs :

    1.  **Code**

    2.  **Visiteur**

    3.  **Début prévu**

    4.  **Fin prévue**

3.  Cliquez sur la colonne **Créé le** et sélectionnez **Supprimer**. Le champ **Créé sur** sera maintenant supprimé de la vue.

4.  Redimensionnez la largeur de chaque colonne pour faire rentrer les données.

5.  Cliquez sur **Enregistrer** et attendez la fin de l’enregistrement.

6.  Cliquez sur **Publier** et attendez la fin de la publication.

## <a name="task-3-create-new-view-for-todays-visits"></a>Tâche \#3 : Créer une vue pour les visites du jour

Nous allons maintenant cloner la vue afin de créer une nouvelle vue pour les visites d’aujourd’hui.

1.  Cliquez sur la **flèche déroulante** affichée en regard du bouton Enregistrer (attention à ne pas appuyer sur le bouton lui-même) et sélectionnez **Enregistrer sous**.

2.  Changez le nom en **Visites du jour** et appuyez sur **Enregistrer**.

3.  Cliquez sur le lien **Modifier les filtres** dans le panneau Propriétés.

2.  Cliquez sur **Ajouter**, puis sélectionnez **Ajouter une ligne**.

3.  Sélectionnez le champ **Début programmé**, puis sélectionnez la condition **Aujourd’hui** dans la liste déroulante.

4.  Cliquez sur **...** dans la ligne **État**, puis sur **Supprimer** pour supprimer cette condition de filtre.

5.  Appuyez sur **OK** pour enregistrer la condition. La vue est désormais filtrée pour n’afficher que les enregistrements dont la date de début programmé est aujourd’hui.

6.  Ajoutez les champs **Début réel** et **Fin réelle** à la vue.

> **Remarque :** Étant donné que nous ne filtrons plus l’état de la vue, nous verrons toutes les visites d’aujourd’hui, y compris les visites terminées. Ces champs permettront de différencier les visites terminées et les visites en cours.

7.  Cliquez sur **Enregistrer**.

8.  Cliquez sur **Publier** et attendez la fin de la publication.

# <a name="exercise-2-create-model-driven-application"></a>Exercice \#2 : Créer une application pilotée par modèle

**Objectif** : Au cours de cet exercice, vous allez créer l’application pilotée par modèle, personnaliser le plan du site et tester l’application.

>   Pour des raisons de simplicité et de rapidité, nous n’aborderons pas certaines des colonnes de la table Visite dans ce labo. 

## <a name="task-1-create-application"></a>Tâche \#1 : Créer une application

1.  Connectez-vous à <https://make.powerapps.com> (si ce n’est déjà fait).

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Créer l’application pilotée par modèle :

    1.  Sélectionnez **Application vide** dans la section **Démarrer à partir de** de l’écran d’accueil.

    2.  Sous **Application vide basée sur Dataverse**, sélectionnez **Créer**.

    3.  Sélectionnez l’expérience **Concepteur d’application moderne**.
    
    4.  Sélectionnez **Create** (Créer).
    
    5.  Entrez **Gestion du campus Bellows** comme nom et sélectionnez **Créer**.

4.  Une fois votre nouvelle application pilotée par modèle chargée, sélectionnez le bouton **+ Ajouter une page**.

5.  Dans l’écran Ajouter une page, choisissez **Vue et formulaire basés sur une table**, puis sélectionnez le bouton **Suivant**.

6.  Ajoutez les tables suivantes :

    1.  Accédez à

    2.  Contact

7.  Une fois que vous avez sélectionné les 2 tables, sélectionnez **Ajouter**.

8.  À l’aide des icônes de navigation situées à gauche de l’écran, sélectionnez **Navigation**.

9.  Dans le volet de navigation, sélectionnez le **Groupe 1** sous l’indication Barre de navigation.

10.  À droite de l’écran, dans la section **Options d’affichage**, remplacez la propriété **Titre** par **Sécurité**.

## <a name="task-2-edit-your-app"></a>Tâche \#2 : Modifier votre application
Tous les composants nécessaires étant désormais ajoutés à l’application pilotée par modèle, nous allons organiser les éléments.

1.  Dans le volet de navigation, sous le groupe de sécurité, sélectionnez **SubArea1**.

2.  Sélectionnez les **Points de suspension**, et dans le menu qui s’affiche, sélectionnez **SubArea1**.

3.  Dans le volet de navigation à gauche de l’écran, sélectionnez **Pages**.

4.  Recherchez et développez **Visite** dans le volet Pages.

5.  Sélectionnez **Formulaire de visite**.

6.  À droite de l’écran, sélectionnez **Gérer les formulaires**.

7.  Sélectionnez le formulaire **Informations principales**, puis cliquez sur **Enregistrer**.

8.  Sous **Visite** dans le volet Pages, sélectionnez **Vue des visites**.

9.  À droite de l’écran, sélectionnez **Gérer les vues**.

10. Sélectionnez les formulaires **Visites du jour** et **Visites actives**, puis sélectionnez **Enregistrer**.

11. Sélectionnez **Enregistrer**.

12. Une fois l’opération **Enregistrer** terminée, sélectionnez le bouton **Publier** pour publier vos modifications.

## <a name="task-3-test-application"></a>Tâche \#3 : Application de test

1.  Lancer l’application

    1.  Sélectionnez **Lire** pour ouvrir votre application dans une nouvelle fenêtre.

2.  Créer un nouveau contact

    1.  L’application doit s’ouvrir sur la vue **Mes contacts actifs**. Si ce n’est pas le cas, sélectionnez Visites sur la partie gauche. 

    2.  Cliquez sur **Nouveau** dans le menu supérieur.

    3.  Dans **Prénom**, indiquez `John` puis, dans le champ **Nom de famille**, indiquez `Doe`.

    4.  Indiquez votre adresse e-mail personnelle dans **E-mail**. Elle sera utilisée dans un prochain labo où vous recevrez un e-mail. 

    5.  Cliquez sur **Enregistrer et fermer**.

    6.  Vous devriez maintenant voir le contact créé dans la vue **Contacts actifs**.

4.  Créer une nouvelle visite

    1.  Sélectionnez **Visites** dans le plan du site.

    2.  Cliquez sur **Nouveau**.

    3.  Si nécessaire, remplissez les champs.

        1.  **Nom** : `New test visit`

        2.  **Visiteur** : sélectionnez John Doe.

        3.  **Début planifié** : sélectionnez la date de demain et 14 h 00 comme heure de début.

        4.  **Fin planifiée** : sélectionnez la date de demain et 15 h 30 comme heure de fin.

    4.  Cliquez sur **Enregistrer et fermer**. La visite sera alors créée. Vous devez pouvoir la voir dans la vue Visites actives.

    5.  Changez la vue en **Visites du jour**. Vous ne devriez plus voir la nouvelle visite dans la vue, car elle est prévue pour demain.

5.  Vous pouvez ajouter d’autres enregistrements test.

    Votre application en cours d’exécution doit ressembler à ceci :

![](media/3-model-driven-app.png)

Félicitations ! Vous avez créé et configuré votre première application pilotée par modèle.

# <a name="challenges"></a>Défis

-   Sélectionner des vues et des formulaires spécifiques pour les contacts
