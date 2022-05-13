---
lab:
  title: 'Labo 6 : Création d’une solution automatisée'
  module: 'Module 4: Get Started with Power Automate'
ms.openlocfilehash: c37bbf2975aa1964493e93716d0b3aeb32030c99
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424632"
---
# <a name="module-4-get-started-with-power-automate"></a>Module 4 : démarrage de Power Automate
## <a name="lab-how-to-build-an-automated-solution"></a>Labo : Création d’une solution automatisée

## <a name="scenario"></a>Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visiteurs du campus sont actuellement enregistrés dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Au cours de ce labo, vous créerez des flux Power Automate pour automatiser différents aspects de la gestion du campus.

# <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Les éléments suivants ont été identifiés comme des exigences que vous devez implémenter pour terminer le projet :

-   Le personnel de sécurité doit recevoir des notifications des visiteurs dépassant leur plage horaire programmée.

## <a name="prerequisites"></a>Prérequis

-   Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

-   Participation au **Module 2 - Labo 1 : Présentation de Microsoft Dataverse**

-   Contact John Doe créé avec une adresse e-mail personnelle dans

## <a name="things-to-consider-before-you-begin"></a>Éléments à considérer avant de commencer

-   Comment mesurer les dépassements de plage horaire et appliquer des politiques strictes ?

# <a name="exercise-1-create-visit-notification-flow"></a>Exercice \#1 : Créer un flux de notification de visite

**Objectif** : Dans cet exercice, vous allez créer un flux Power Automate qui met en place ces conditions. Le visiteur doit recevoir un e-mail contenant le code unique attribué à la visite.

## <a name="task-1-create-a-flow"></a>Tâche \#1 : Créer un flux

1.  Accédez à <https://make.powerapps.com>. Vous devrez peut-être vous authentifier à nouveau. Cliquez sur **Se connecter** et suivez les instructions si nécessaire.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

2.  Dans le volet de navigation de gauche, sélectionnez **Flux**.

4.  Si vous y êtes invité, sélectionnez **Démarrage**.

5.  Cliquez sur **Nouveau flux**, puis sélectionnez **Flux cloud automatisé**.

6.  Sous **Choisir le déclencheur de votre flux**, recherchez **Dataverse**.

7.  Sélectionnez le déclencheur **Lorsqu’une ligne est ajoutée, modifiée ou supprimée**, puis cliquez sur **Créer**.

8.  Remplissez les conditions du déclencheur pour le flux :

    1.  Sélectionner **Ajouté** pour **Type de modification**

    2.  Sélectionnez **Visites** dans la zone **Nom de table**.

    3.  Sélectionnez **Organisation** dans la liste **Étendue**.

    4.  À l’étape de déclenchement, cliquez sur les points de suspension ( **...** ), puis sur **Renommer**.
        Renommez ce déclencheur **« Lorsqu’une visite est ajoutée »** . Il s’agit d’une bonne pratique, qui vous permet, ainsi qu’autres éditeurs de flux, de comprendre le but de l’étape sans vous plonger dans les détails.

## <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Tâche \#2 : Créer une étape pour obtenir la ligne du visiteur

1.  Sélectionnez **Nouvelle étape**. Cette étape est nécessaire pour récupérer les informations des visiteurs, y compris les adresses e-mail.

2.  Recherchez **Dataverse**.

3.  Sélectionnez l’action **Obtenir une ligne par ID**.

4.  Sélectionnez **Contacts** comme **Nom de table**.

5.  Dans le champ **ID de ligne**, sélectionnez **Visiteur (valeur)** dans la liste Contenu dynamique.

6.  Dans cette action, cliquez sur les points de suspension ( **...** ), puis sur **Renommer**.
        Renommez cette action **« Obtenir le visiteur »** . Il s’agit d’une bonne pratique, qui vous permet, ainsi qu’autres éditeurs de flux, de comprendre le but de l’étape sans vous plonger dans les détails.

## <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Tâche \#3 : Créer une étape pour envoyer un e-mail au visiteur

1.  Cliquez sur **Nouvelle étape**. Il s’agit de l’étape qui permettra de créer et d’envoyer des e-mails au visiteur.

2.  Recherchez *message*, sélectionnez le connecteur **Office 365 Outlook** et l’action **Envoyer un e-mail (V2)** .

3.  Si vous êtes invité à accepter les conditions d’utilisation de cette action, cliquez sur **Accepter**.

4.  Sélectionnez **Ajouter du contenu dynamique** sous le champ **À**. 
    
5.  Sélectionnez **E-mail** dans la liste Contenu dynamique.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

5.  Entrez **Votre visite prévue à Bellows College** dans le champ **Sujet**.

6.  Entrez le texte suivant dans le **Corps du courriel**.

>   Le contenu dynamique doit être placé là où les champs sont nommés entre crochets. Il est recommandé de commencer par copier et coller l’ensemble du texte, puis d’ajouter du contenu dynamique aux endroits appropriés.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

7.  Mettez en surbrillance le texte **{Prénom}** . Remplacez-le par le champ **Prénom** de l’étape **Obtenir le visiteur**.

8.  Mettez en surbrillance le texte **{Début prévu}** . Remplacez-le par le champ **Début prévu** de l’étape **Obtenir le visiteur**.

9.  Mettez en surbrillance le texte **{Fin prévue}** . Remplacez-le par le champ **Fin prévue** de l’étape **Obtenir le visiteur**.

10.  Sélectionnez le nom du flux dans la partie supérieure et renommez-le `Visit
        Notification`.

11.  Cliquez sur **Enregistrer**.

Laissez cet onglet de flux ouvert pour la tâche suivante. Votre flux doit ressembler à ce qui suit :

![Exemple d’étapes de flux.](media/4-Flow.png)

## <a name="task-2-validate-and-test-the-flow"></a>Tâche \#2 : Valider et tester le flux

1.  Ouvrez un nouvel onglet dans votre navigateur et accédez à <https://make.powerapps.com>.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Cliquez sur **Applications** et sélectionnez l’application pilotée par modèle **Gestion du campus** que vous avez créée précédemment.

3.  En laissant cet onglet ouvert, revenez à l’onglet précédent avec votre flux.

4.  Dans la barre de commandes, cliquez sur **Test**. Sélectionnez **Manuel**, puis **Enregistrer et tester**.

5.  Dans le volet de navigation de gauche, sélectionnez **Visites**.

6. Appuyez sur le bouton **+ Nouveau** pour ajouter un nouvel enregistrement **Visite**.

7. Renseignez l’enregistrement Visite comme ceci :

    -   **Nom :** Visite test

    -   **Visiteur :** John Doe

    -   **Début prévu :** Demain à 8 h 00

    -   **Fin prévue :** Demain à 9 h 00

8. Sélectionnez le bouton **Enregistrer et fermer**.

Après un court délai, vous devriez voir un e-mail dans votre boîte de réception, car vous avez indiqué l’e-mail de John Doe comme votre e-mail personnel. 

# <a name="challenges"></a>Défis

-   Essayez différentes options de mise en forme sur l’e-mail. Comment pouvez-vous le rendre plus professionnel ? 
