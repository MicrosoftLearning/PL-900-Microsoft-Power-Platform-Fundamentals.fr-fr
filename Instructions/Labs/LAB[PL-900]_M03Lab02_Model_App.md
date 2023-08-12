---
lab:
  title: "Labo 3\_: Comment créer une application pilotée par modèle"
  module: 'Module 3: Get started with Power Apps'
---

# Labo 3 : Comment créer une application pilotée par modèle

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visiteurs du campus sont actuellement enregistrés dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous allez créer une application Power Apps pilotée par modèle pour permettre au personnel de bureau du campus de gérer les enregistrements de visites sur l’ensemble du campus.

Étapes de labo de haut niveau

Dans le cadre de la création de l’application basée sur un modèle, vous effectuerez les opérations suivantes :

- Créer une nouvelle application pilotée par modèle nommée Gestion du campus Bellows

- Modifier la navigation de l’application pour référencer les tables requises

- Personnaliser les formulaires et les vues des tables requises pour l’application

Nous travaillerons avec les composants suivants :

- **Vues** : Les vues permettent à l’utilisateur d’afficher les données existantes dans la table des formulaires.

- **Formulaires** : C’est là que l’utilisateur crée ou met à jour de nouvelles lignes dans les tables.

Les deux seront intégrés à l’application basée sur un modèle, pour une meilleure expérience utilisateur.

Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

- Participation au **Module 2 Labo 1 : modélisation des données**

Éléments à considérer avant de commencer

- Quels changements devons-nous apporter pour améliorer l’expérience utilisateur ?

- Que devrions-nous inclure dans une application pilotée par modèle d’après le modèle de données que nous avons créé ?

- Quelles personnalisations peuvent être effectuées sur le plan du site d’une application pilotée par modèle ?

Exercice 1 : personnaliser les affichages et les formulaires

**Objectif** : Au cours de cet exercice, vous apprendrez à personnaliser les vues et les formulaires des tables personnalisées qui seront utilisées dans l’application pilotée par modèle.

Tâche n°1 : Modifier le formulaire de visite

1.  Connectez-vous à <https://make.powerapps.com> si vous n’êtes pas encore connecté.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Dans le volet de navigation gauche, sélectionnez **Tables**, puis ouvrez votre table **Visit** (Visite).

    Si vous ne voyez pas la table Visite, vérifiez que vous êtes dans l’environnement approprié (étape 2).

4.  Sous la section **Expériences des données**, sélectionnez **Formulaires**, puis ouvrez le formulaire **Informations** avec le type de formulaire **Principal**. (**Important :** Veillez à sélectionner le formulaire de type **Principal**.) 

    **IMPORTANT :** Par défaut, tous les formulaires sont nommés Informations, donc vérifiez que le formulaire que vous sélectionnez est de type **Principal** et pas autre chose. Le formulaire comporte deux champs par défaut : Nom et Propriétaire.

5.  À droite de l’écran, dans le volet **Propriétés**, sélectionnez le champ **Nom d’affichage**, puis remplacez-le par `Main Information`.

6.  Sélectionnez **Colonnes de la table** dans le volet de navigation gauche et ajoutez les champs suivants sous le champ **Owner** (Propriétaire) en faisant glisser les colonnes dans le formulaire ou en cliquant simplement sur les noms de colonne :

    1. **Visiteur**

    2. **Début prévu**

    3. **Fin prévue**

    4. **Début réel**

    5. **Fin réelle**

7.  Faites glisser la colonne **Code** et déposez-la dans l’en-tête du formulaire.

    L’en-tête est la zone supérieure droite du formulaire. Vous devrez peut-être réduire le panneau Propriétés sur le côté droit de l’écran pour voir le champ sur le formulaire.

8.  En gardant le champ **Code** sélectionné, cochez la case en regard de **Lecture seule** dans le panneau Propriétés à droite de l’écran.

9.  Sélectionnez le champ **Propriétaire**. Dans le volet Propriétés, remplacez **Étiquette** par `Host`

10. Sélectionnez le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération d’enregistrement et de publication.

11. Si la vue d’édition est ouverte dans un nouvel onglet ou une nouvelle fenêtre de navigateur, fermez cette vue. Sinon, sélectionnez **🡠 Retour** en haut à gauche de l’écran. Vous devez normalement être revenu aux Formulaires de la table **Visit**.

12. Utilisation des barres de navigation en haut à gauche (**Tables** > **Visit** > **Formulaires**). Sélectionnez **Visit** pour revenir à l’écran des propriétés de la table **Visit**. 


Tâche n° 2 : Modifier la vue Visites actives

Dans cette tâche, nous allons modifier la vue des visites actives par défaut et créer une nouvelle vue pour les visites du jour.

1.  Sous la section **Expériences des données**, sélectionnez **Vues** et ouvrez votre vue **Active Visits** (Visites actives).

2.  Ajoutez les champs suivants à la vue en cliquant sur ou en faisant glisser-déposer les champs :

    1. **Code**

    2. **Visiteur**

    3. **Début prévu**

    4. **Fin prévue**

3.  Sélectionnez le menu déroulant sur la colonne **Created On** (Créé le), puis sélectionnez **Supprimer**. Le champ **Created On** est maintenant supprimé de la vue.

4.  Redimensionnez la largeur de chaque colonne pour l’adapter aux données.

5.  Sous **Trier par...** sélectionnez X pour supprimer **Nom** et sélectionnez à la place **Début prévu**.

6.  Sélectionnez **Scheduled Start** (Début prévu) pour définir l’ordre de tri sur **Du plus récent au plus ancien**.

7.  Sélectionnez le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération de publication.


Tâche n°3 : Créer une vue pour les visites du jour

Nous allons maintenant cloner la vue afin de créer une nouvelle vue pour les visites du jour.

IMPORTANT : Veillez à ne pas fermer la vue Visites actives, car nous allons l’exploiter pour créer la vue de visites du jour.

1.  Sélectionnez **Enregistrer sous**.

2.  Changez le **Nom** en `Today’s Visits` et sélectionnez **Enregistrer**.

3.  Sélectionnez **Modifier les filtres** dans le panneau Propriétés.

4.  Sélectionnez **+ Ajouter**, puis sélectionnez **Ajouter une ligne**.

5.  Sélectionnez **Scheduled Start** comme champ, puis remplacez **Égal à** par **Today** comme condition dans le menu déroulant.

6.  Sélectionnez **…** . **Plus de commandes** sur la ligne **Status** (État), puis sélectionnez **Supprimer** pour supprimer cette condition de filtrage.

7.  Sélectionnez **OK** pour enregistrer la condition. La vue est maintenant filtrée pour afficher seulement les enregistrements où **Scheduled Start** correspond à la date du jour.

8.  Ajoutez les champs **Début réel** et **Fin réelle** à la vue.

    **Remarque :** Étant donné que nous ne filtrons plus l’état de la vue, nous verrons toutes les visites du jour, y compris les visites terminées. Ces champs permettront de différencier les visites terminées et les visites en cours.

9.  Sélectionnez le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération de publication.


Exercice 2 : créer une application pilotée par modèle

**Objectif** : au cours de cet exercice, vous allez créer une application pilotée par modèle, personnaliser le plan du site et tester l’application.

Pour rester simples et faute de temps, nous n’aborderons pas certaines des colonnes de la table Visite dans ce labo.

Tâche no 1 : Créer une application

1.  Connectez-vous à <https://make.powerapps.com> si vous n’êtes pas encore connecté.

2.  Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3.  Sélectionnez **+ Créer** dans le volet de navigation gauche.

4.  Créer l’application pilotée par modèle :

    1. Sélectionnez **Application vide** dans la section **Démarrer à partir de** de l’écran **Créer votre application**.

    2. Sous **Application vide basée sur Dataverse**, sélectionnez **Créer**.

    3. Entrez `Bellows Campus Management` pour **Nom**, puis sélectionnez **Créer**.

5.  Une fois votre nouvelle application pilotée par modèle chargée, sélectionnez le bouton **+ Ajouter une page**.

6.  Dans l’écran **Ajouter une page**, choisissez **Table Dataverse**, puis sélectionnez le bouton **Suivant**.

7.  Sélectionnez les tables suivantes :

    1. Accédez à

    2. Contact

8.  Une fois que vous avez les 2 tables, sélectionnez **Ajouter**.

9.  À l’aide des icônes de navigation situées à gauche de l’écran, sélectionnez **Navigation**.

10. Dans le volet de navigation, sélectionnez **Nouveau groupe** sous l’indication Navigation. Vous devrez peut-être développer le menu à gauche.

11. À droite de l’écran, dans la section **Options d’affichage**, changez la propriété **Titre** en `Security`.

12. Sélectionnez **Enregistrer** et attendez la fin de l’enregistrement.

13. Une fois l’opération **Enregistrer** terminée, sélectionnez le bouton **Publier** pour publier vos modifications.


Tâche 2 : Tester l’application

Lancer l’application

1. Sélectionnez le bouton **Lecture** pour charger l’application pilotée par modèle dans un nouvel onglet.

Créer un contact

2.  L’application doit s’ouvrir sur la vue **Mes contacts actifs**. Si ce n’est pas le cas, sélectionnez **Contacts** dans la navigation de gauche.

3.  Sélectionnez **+ Nouveau** dans la barre de commandes.

4.  Entrez `John` pour **First Name** (Prénom) et `Doe` pour **Name** (Nom).

5.  Indiquez votre adresse e-mail personnelle dans **E-mail**. Ceci sera utilisé dans un prochain labo, où vous recevrez un e-mail.

6.  Sélectionnez **Enregistrer et fermer**.

7.  Vous devriez maintenant voir le contact créé dans la vue **Mes contacts actifs**.

Créer une visite

8.  Sélectionnez **Visits** dans la navigation gauche (également appelée « plan du site »).

9.  Sélectionnez **+Nouveau**.

10. Renseignez les champs comme suit :

    1. **Nom** : `New test visit`

    2. **Visitor** (Visiteur) : sélectionnez **John Doe**

    3. **Scheduled Start** : sélectionnez la date de demain et 14h00 comme heure de début.

    4. **Scheduled End** : sélectionnez la date de demain et 15h30 comme heure de fin.

11. Sélectionnez **Enregistrer et fermer**. Ceci va créer la visite et vous devez normalement la voir dans la vue **Active Visits**.

12. Passez à la vue **Today’s Visits** (Visites du jour) en utilisant la liste déroulante en regard de **Active Visits**. Vous ne devriez plus voir la nouvelle visite dans la vue, car elle est prévue pour demain.

13. Vous pouvez ajouter quelques autres enregistrements de test.

Votre application pilotée par modèle en cours d’exécution doit ressembler à ceci :

![](media/3-model-driven-app.png)

Félicitations ! Vous avez créé et configuré votre première application pilotée par modèle.

## Défis

- Sélectionnez des vues et des formulaires spécifiques pour les contacts.

