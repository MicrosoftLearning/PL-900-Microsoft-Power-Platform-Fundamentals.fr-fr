---
lab:
  title: "Labo 3\_: Comment créer une application pilotée par modèle"
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Labo 3 : Comment créer une application pilotée par modèle

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai qui ne peut pas être utilisé ni être accessible une fois la classe terminée, ni faire l’objet d’une prolongation. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est un établissement d’enseignement avec plusieurs campus et plusieurs cursus. De nombreux enseignants et administrateurs de Bellow College doivent assister à des événements et acheter des articles. Le suivi de ces dépenses a toujours été un défi en soi.

L’administration des campus aimerait moderniser son système de notes de frais en fournissant aux employés un moyen numérique de soumettre leurs dépenses.

Tout au long de ce cours, vous allez créer des applications et effectuer une automatisation pour permettre aux employés de Bellows College de gérer les dépenses.

## Étapes de labo de haut niveau

Dans le cadre de la création de l’application basée sur un modèle, vous effectuerez les opérations suivantes :

- Créer une nouvelle application pilotée par modèle nommée Gestion des dépenses Bellows

- Modifier la navigation de l’application pour référencer les tables requises

- Personnaliser les formulaires et les vues des tables requises pour l’application

Nous travaillerons avec les composants suivants :

- **Vues** : Les vues permettent à l’utilisateur d’afficher les données existantes dans la table des formulaires.

- **Formulaires** : C’est là que l’utilisateur crée ou met à jour de nouvelles lignes dans les tables.

Les deux seront intégrés à l’application basée sur un modèle, pour une meilleure expérience utilisateur.

### Prérequis

- Conclusion du **Module 1 Lab 0 – Valider l'environnement de laboratoire **

**Éléments à prendre en compte avant de commencer**

- Quels changements devons-nous apporter pour améliorer l’expérience utilisateur ?

- Que devrions-nous inclure dans une application pilotée par modèle d’après le modèle de données que nous avons créé ?

- Quelles personnalisations peuvent être effectuées sur le plan du site d’une application pilotée par modèle ?

## Exercice 1 : personnaliser les affichages et les formulaires

**Objectif** : Au cours de cet exercice, vous apprendrez à personnaliser les vues et les formulaires des tables personnalisées qui seront utilisées dans l’application pilotée par modèle.

### Tâche n°1 : Modifier le formulaire de notes de frais

1. Si ce n’est pas déjà fait, connectez-vous à https://make.powerapps.com

1. Sélectionnez l’environnement **Dev One** en haut à droite, si ce n’est pas déjà fait.

1. Dans le volet de navigation à gauche, sélectionnez **Tables** et ouvrez votre table **Notes de frais**.

Si vous ne voyez pas la table Note de frais, vérifiez que vous êtes dans l’environnement approprié (étape 2).

1. Sous la section **Expériences des données**, sélectionnez **Formulaires**, puis ouvrez le formulaire **Informations** avec le type de formulaire **Principal**. (**Important :** Veillez à sélectionner le formulaire de type **Principal**.)

    >**IMPORTANT :** Par défaut, tous les formulaires sont nommés Informations, donc vérifiez que le formulaire que vous sélectionnez est de type **Principal** et pas autre chose. Le formulaire comporte deux champs par défaut : Nom et Propriétaire.

1. À droite de l’écran dans le volet **Propriétés**, sélectionnez le champ **Nom d’affichage**, puis remplacez par Informations de la note

1. Sélectionnez **Colonnes de la table** dans le volet de navigation gauche et ajoutez les champs suivants sous le champ **Owner** (Propriétaire) en faisant glisser les colonnes dans le formulaire ou en cliquant simplement sur les noms de colonne :

    - **Description**

    - **Objet de la note**

    - **Date d’échéance de la note**

    - **Montant total de la note**

1. Glissez-déplacez la colonne **Raison du statut** dans l’en-tête du formulaire.

L’en-tête est la zone supérieure droite du formulaire. Vous devrez peut-être réduire le panneau Propriétés sur le côté droit de l’écran pour voir le champ sur le formulaire.

1. Sélectionnez le champ **Propriétaire**. Dans le volet Propriétés, remplacez l’**Étiquette** par Demandeur

1. Sélectionnez le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération d’enregistrement et de publication.

1. Si la vue d’édition est ouverte dans un nouvel onglet ou une nouvelle fenêtre de navigateur, fermez cette vue. Sinon, sélectionnez **🡠 Retour** en haut à gauche de l’écran. Vous devriez normalement être revenu aux Formulaires de la table **Note de frais**.

1. Utilisation des barres de navigation en haut à gauche (**Tables** > **Note de frais** > **Formulaires**). Sélectionnez **Note de frais** pour revenir à l’écran des propriétés de la table **Note de frais**.

## Tâche n° 2 : Modifier la vue Notes de frais actives

Dans cette tâche, nous allons modifier la vue par défaut Notes de frais actives et créer une vue pour les notes de frais dues aujourd’hui.

1. Sous la section **Expériences des données**, sélectionnez **Vues** et ouvrez votre vue **Notes de frais actives**.

1. Ajoutez les champs suivants à la vue en cliquant sur ou en faisant glisser-déposer les champs :

    - **Objet de la note**

    - **Date d’échéance de la note**

    - **Total de la note**

1. Sélectionnez le menu déroulant sur la colonne **Created On** (Créé le), puis sélectionnez **Supprimer**. Le champ **Created On** est maintenant supprimé de la vue.

1. Redimensionnez la largeur de chaque colonne pour l’adapter aux données.

1. Sous **Trier par...** sélectionnez X pour supprimer **Nom** et sélectionnez à la place **Montant total de la note**.

1. Sélectionnez **Montant total de la note** pour remplacer l’ordre de tri par **Du plus grand au plus petit**.

1. Sélectionnez le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération de publication.

### Tâche n°3 : Créer une vue pour les notes dues aujourd’hui

Nous allons maintenant cloner la vue afin de créer une nouvelle vue pour les notes dues aujourd’hui.

>    **IMPORTANT :** Veillez à ne pas fermer la vue Notes de frais actives, car nous allons l’exploiter pour créer la vue Notes dues aujourd’hui.

1. Sélectionnez **Enregistrer sous**.

1. Remplacez le **Nom** par Notes de frais dues aujourd’hui, puis sélectionnez **Enregistrer**.

1. Sélectionnez **Modifier les filtres** dans le panneau Propriétés.

1. Sélectionnez **+ Ajouter**, puis sélectionnez **Ajouter une ligne**.

1. Sélectionnez **Date d’échéance de la note** comme champ, puis remplacez **Égal à** par **Aujourd’hui** comme condition dans la liste déroulante.

1. Sélectionnez **…** . **Plus de commandes** sur la ligne **Status** (État), puis sélectionnez **Supprimer** pour supprimer cette condition de filtrage.

1. Sélectionnez **OK** pour enregistrer la condition. La vue est maintenant filtrée pour afficher uniquement les enregistrements dont la **Date d’échéance de la note** est aujourd’hui.

1. Ajoutez le champ **Montant de remboursement** dans la vue.

1. Sélectionnez le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération de publication.

## Exercice 2 : créer une application pilotée par modèle

**Objectif** : au cours de cet exercice, vous allez créer une application pilotée par modèle, personnaliser le plan du site et tester l’application.

Pour rester simples et gagner du temps, nous n’aborderons pas toutes les colonnes Note de frais dans ce labo.

### Tâche no 1 : Créer une application

1. Si ce n’est pas déjà fait, connectez-vous à https://make.powerapps.com

1. Sélectionnez l’environnement **Dev One** en haut à droite, si ce n’est pas déjà fait.

1. Sélectionnez **+ Créer** dans le volet de navigation gauche.

1. Créer l’application pilotée par modèle :

    - Sélectionnez **Application vide** dans la section **Démarrer à partir de** de l’écran **Créer votre application**.

    - Sous **Application vide basée sur Dataverse**, sélectionnez **Créer**.

    - Entrez Gestion des dépenses des employés comme **Nom** et sélectionnez **Créer**.

1. Une fois votre nouvelle application pilotée par modèle chargée, sélectionnez le bouton **+ Ajouter une page**.

1. Dans l’écran **Ajouter une page**, choisissez **Table Dataverse**, puis sélectionnez le bouton **Suivant**.

1. Sélectionnez les tables suivantes :

    - Note de frais

    - Contact

1. Une fois que vous avez les 2 tables, sélectionnez **Ajouter**.

1. À l’aide des icônes de navigation situées à gauche de l’écran, sélectionnez **Navigation**.

1. Dans le volet de navigation, sélectionnez **Nouveau groupe** sous l’indication Navigation. Vous devrez peut-être développer le menu à gauche.

1. À droite de l’écran, dans la section **Options d’affichage**, remplacez la propriété **Titre** par Notes

1. Sélectionnez **Enregistrer** et attendez la fin de l’enregistrement.

1. Une fois l’opération **Enregistrer** terminée, sélectionnez le bouton **Publier** pour publier vos modifications. Attendez la fin de la publication.

## Tâche 2 : Tester l’application

**Démarrer l’application**

1. Sélectionnez le bouton **Lecture** pour charger l’application pilotée par modèle dans un nouvel onglet.

**Créer un contact**

1. L’application doit s’ouvrir sur la vue **Mes contacts actifs**. Si ce n’est pas le cas, sélectionnez **Contacts** dans le menu de gauche.

1. Sélectionnez **+ Nouveau** dans la barre de commandes.

1. Entrez John comme **Prénom** et Doe comme **Nom**

1. Indiquez votre adresse e-mail personnelle dans **E-mail**. Ceci sera utilisé dans un prochain labo, où vous recevrez un e-mail.

1. Cliquez sur **Enregistrer et fermer**.

1. Vous devriez maintenant voir le contact créé dans la vue **Mes contacts actifs**.

**Créer une note de frais**

1. Sélectionnez **Notes de frais** dans la navigation de gauche (également appelée « plan du site »).

1. Cliquez sur **+ Nouveau**.

1. Renseignez les champs comme suit :

    - **Nom du rapport** : nouveau rapport de test

    - **Objet de la note** : sélectionner **Conférence**

    - **Date d’échéance de la note** : sélectionner la date d’aujourd’hui

1. Cliquez sur **Enregistrer et fermer**. Cette opération crée un rapport de test que vous devriez voir dans la vue **Notes de frais actives**.

1. Passez à la vue **Notes de frais dues aujourd’hui** en utilisant la liste déroulante à côté de **Notes de frais actives**. 

1. Vous pouvez ajouter quelques autres enregistrements de test.

Votre application pilotée par modèle en cours d’exécution doit ressembler à ceci :

![Capture d’écran de l’application pilotée par modèle qui vient d’être créée.](media/lab-3-create-a-model-app-01.png)

Félicitations ! Vous avez créé et configuré votre première application pilotée par modèle.
