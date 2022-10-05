---
lab:
  title: "Labo\_4\_: Création d’une solution automatisée"
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>Labo 4 : Création d’une solution automatisée

## <a name="scenario"></a>Scénario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous allez créer un flux Power Automate pour prévenir par un e-mail un visiteur qu’une visite est programmée.

## <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Les éléments suivants ont été identifiés comme des exigences que vous devez implémenter pour terminer le projet :

- Les contacts doivent être avertis par e-mail lorsqu’une visite est planifiée.

## <a name="prerequisites"></a>Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**
- Participation au **Module 2 Labo 1 : modélisation des données**
- Participation au **Module 2 Labo 3 : comment générer une application pilotée par modèle**
- Contact John Doe créé avec une adresse e-mail personnelle renseignée

## <a name="exercise-1-create-visit-notification-flow"></a>Exercice 1 : Créer un flux de notification de visite

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>Tâche \#1 : Créer un flux

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Dans le volet de navigation de gauche, sélectionnez **Flux**.

4.  Si vous y êtes invité, sélectionnez **Démarrage**.

5.  Cliquez sur **Nouveau flux**, puis sélectionnez **Flux cloud automatisé**.

6.  Entrez « Notification de visite » dans **Nom du flux**.

7.  Sous **Choisir le déclencheur de votre flux**, recherchez **Dataverse**.

8.  Sélectionnez le déclencheur **Lorsqu’une ligne est ajoutée, modifiée ou supprimée**, puis cliquez sur **Créer**.

9.  Remplissez les conditions du déclencheur pour le flux :

    1.  Sélectionner **Ajouté** pour **Type de modification**

    2.  Sélectionnez **Visites** dans la zone **Nom de table**.

    3.  Sélectionnez **Organisation** dans la liste **Étendue**.

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Tâche \#2 : Créer une étape pour obtenir la ligne du visiteur

1.  Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus.

2.  Recherchez **Dataverse**.

3.  Sélectionnez l’action **Obtenir une ligne par ID**.

4.  Sélectionnez **Contacts** comme **Nom de table**.

5.  Les visiteurs du campus sont actuellement enregistrés dans des journaux papier.

6.  Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Tâche \#3 : Créer une étape pour envoyer un e-mail au visiteur

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  Recherchez *message*, sélectionnez le connecteur **Office 365 Outlook** et l’action **Envoyer un e-mail (V2)** .

3.  Si vous êtes invité à accepter les conditions d’utilisation de cette action, cliquez sur **Accepter**.

4.  Sélectionnez **Ajouter du contenu dynamique** sous le champ **À**. 
    
5.  Sélectionnez **E-mail** dans la liste Contenu dynamique.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  Entrez **Votre visite prévue à Bellows College** dans le champ **Sujet**.

7.  Entrez le texte suivant dans le **Corps du courriel**.

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  Cliquez sur **Enregistrer**.

Leave this flow tab open for the next task. You flow should look approximately like the following:

![Exemple d’étapes de flux.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>Tâche \#4 : Valider et tester le flux

1.  Ouvrez un nouvel onglet dans votre navigateur et accédez à <https://make.powerapps.com>.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Cliquez sur **Applications** et sélectionnez l’application pilotée par modèle **Gestion du campus Bellows** que vous avez créée précédemment.

3.  En laissant cet onglet de navigateur ouvert, revenez à l’onglet précédent avec votre flux.

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  Accédez à l’onglet du navigateur en ayant votre application pilotée par modèle ouverte. 

6.  Dans le volet de navigation de gauche, sélectionnez **Visites**.

6. Appuyez sur le bouton **+ Nouveau** pour ajouter un nouvel enregistrement **Visite**.

7. Renseignez l’enregistrement Visite comme ceci :

    -   **Nom :** Visite test

    -   **Visiteur :** John Doe

    -   **Début prévu :** Demain à 8 h 00

    -   **Fin prévue :** Demain à 9 h 00

8. Sélectionnez le bouton **Enregistrer et fermer**.

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>Défis

- Play around with the formatting on the email. How can you make it more professional looking?