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

1. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) si vous n’êtes pas encore connecté.

2. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3. Dans le volet de navigation de gauche, sélectionnez **Tables**, puis cliquez pour ouvrir votre table **Visit**.

Si vous ne voyez pas la table Visite, vérifiez que vous êtes dans l’environnement approprié (étape 2).

4. Sous la section **Expériences des données**, sélectionnez **Formulaires**, puis cliquez pour ouvrir le formulaire Informations de type **Principal**. (**Important :** Veillez à sélectionner celui avec le type de formulaire **Principal**.) 

**IMPORTANT :** Par défaut, tous les formulaires sont nommés Informations, donc vérifiez que le formulaire que vous sélectionnez est de type **Principal** et pas autre chose. Le formulaire comporte deux champs par défaut : Nom et Propriétaire.

1. À droite de l’écran dans le volet Propriétés, sélectionnez le champ **Nom complet**, puis remplacez-le par **Informations principales**.

2. Sélectionnez la **Table Colonnes** dans le volet de navigation de gauche et ajoutez les champs suivants sous le champ **Propriétaire** en faisant glisser les colonnes dans le formulaire ou en cliquant simplement sur les noms de colonne :

    1. **Visiteur**

    2. **Début prévu**

    3. **Fin prévue**

    4. **Début réel**

    5. **Fin réelle**

3. Faites glisser la colonne **Code** et déposez-la dans l’en-tête du formulaire.

L’en-tête est la zone supérieure droite du formulaire. Vous devrez peut-être réduire le panneau Propriétés sur le côté droit de l’écran pour voir le champ sur le formulaire.

1. En gardant le champ **Code** sélectionné, cochez la case en regard de **Lecture seule** dans le panneau Propriétés à droite de l’écran.

2. Sélectionnez le champ **Propriétaire**. Dans le volet Propriétés, remplacez **Étiquette** par **Hôte**

3. Cliquez sur le bouton **Enregistrer et publier** en haut à droite et attendez la fin de l’opération d’enregistrement et de publication.

4. Si la vue d’édition est ouverte dans un nouvel onglet ou une nouvelle fenêtre de navigateur, fermez cette vue. Sinon, cliquez sur **Retour** en haut à gauche de l’écran. Vous devez ensuite revenir aux Formulaires de tables de visite.

5. Utilisation des barres de navigation en haut à gauche (Tables>Visite>Formulaires). Sélectionnez **Visite** pour revenir à l’écran principale de la table **Visite**.

Tâche n° 2 : Modifier la vue Visites actives

Dans cette tâche, nous allons modifier la vue des visites actives par défaut et créer une nouvelle vue pour les visites du jour.

1. Dans la section **Expériences des données**, sélectionnez **Vues** et cliquez pour ouvrir votre vue **Visites actives**.

2. Ajoutez les champs suivants à la vue en cliquant sur ou en faisant glisser-déposer les champs :

    1. **Code**

    2. **Visiteur**

    3. **Début prévu**

    4. **Fin prévue**

3. Cliquez sur la colonne **Créé le** et sélectionnez **Supprimer**. Le champ **Créé sur** sera maintenant supprimé de la vue.

4. Redimensionnez la largeur de chaque colonne pour faire rentrer les données.

5. Sous **Trier par...** sélectionnez X pour supprimer **Nom** et sélectionnez à la place **Début prévu**.

6. Sélectionnez **Début prévu** pour définir l’ordre de tri sur **Du plus récent au plus ancien**.

7. Cliquez sur **Enregistrer** et attendez la fin de l’enregistrement.

8. Cliquez sur **Publier** et attendez la fin de la publication.

Tâche n°3 : Créer une vue pour les visites du jour

Nous allons maintenant cloner la vue afin de créer une nouvelle vue pour les visites du jour.

IMPORTANT : Veillez à ne pas fermer la vue Visites actives, car nous allons l’exploiter pour créer la vue de visites du jour.

1. Cliquez sur la **flèche déroulante** affichée en regard du bouton Enregistrer (attention à ne pas appuyer sur le bouton lui-même) et sélectionnez **Enregistrer sous**.

2. Changez le nom en **Visites du jour** et appuyez sur **Enregistrer**.

3. Cliquez sur le lien **Modifier les filtres** dans le panneau Propriétés.

4. Cliquez sur **Ajouter**, puis sélectionnez **Ajouter une ligne**.

5. Sélectionnez le champ **Début programmé**, puis sélectionnez la condition **Aujourd’hui** dans la liste déroulante.

6. Cliquez sur **…** dans la ligne **État**, puis sur **Supprimer** pour supprimer cette condition de filtre.

7. Appuyez sur **OK** pour enregistrer la condition. La vue est désormais filtrée pour n’afficher que les enregistrements dont la date de début programmé est aujourd’hui.

8. Ajoutez les champs **Début réel** et **Fin réelle** à la vue.

**Remarque :** Étant donné que nous ne filtrons plus l’état de la vue, nous verrons toutes les visites du jour, y compris les visites terminées. Ces champs permettront de différencier les visites terminées et les visites en cours.

1. Cliquez sur **Enregistrer** et attendez la fin de l’enregistrement.

2. Cliquez sur **Publier** et attendez la fin de la publication.

Exercice 2 : créer une application pilotée par modèle

**Objectif** : au cours de cet exercice, vous allez créer une application pilotée par modèle, personnaliser le plan du site et tester l’application.

Pour rester simples et faute de temps, nous n’aborderons pas certaines des colonnes de la table Visite dans ce labo.

Tâche no 1 : Créer une application

1. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) (si ce n’est déjà fait).

2. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3. Si nécessaire, cliquez sur l’icône **Accueil** à gauche de l’écran.

4. Créer l’application pilotée par modèle :

    1. Sélectionnez **Application vide** dans la section **Démarrer à partir de** de l’écran d’accueil.

    2. Sous **Application vide basée sur Dataverse**, sélectionnez **Créer**.

    3. Entrez **Gestion du campus Bellows** comme nom et sélectionnez **Créer**.

5. Une fois votre nouvelle application pilotée par modèle chargée, sélectionnez le bouton **+ Ajouter une page**.

6. Dans l’écran **Ajouter une page**, choisissez **Table Dataverse**, puis sélectionnez le bouton **Suivant**.

7. Ajoutez les tables suivantes :

    1. Accédez à

    2. Contact

8. Une fois que vous avez sélectionné les 2 tables, sélectionnez **Ajouter**.

9. À l’aide des icônes de navigation situées à gauche de l’écran, sélectionnez **Navigation**.

10. Dans le volet de navigation, sélectionnez le **Groupe 1** sous l’indication Barre de navigation. Vous devrez peut-être développer le menu à gauche.

11. À droite de l’écran, dans la section **Options d’affichage**, remplacez la propriété **Titre** par **Sécurité**.

12. Dans le volet de navigation, sous le groupe de sécurité, sélectionnez **SubArea1**.

13. Sélectionnez les **points de suspension**, puis dans le menu qui s’affiche, choisissez **Supprimer de la navigation**.

14. Sélectionnez **Enregistrer** et attendez la fin de l’enregistrement.

15. Une fois l’opération **Enregistrer** terminée, sélectionnez le bouton **Publier** pour publier vos modifications.

Tâche 2 : Tester l’application

1. Lancer l’application

    1. Sélectionnez le bouton **Lecture** pour charger la nouvelle application dans un nouvel onglet.

2. Créer un nouveau contact

    1. L’application doit s’ouvrir sur la vue **Mes contacts actifs**. Si ce n’est pas le cas, sélectionnez Contacts dans la navigation de gauche.

    2. Cliquez sur **+ Nouveau** dans le menu supérieur.

    3. Indiquez John comme **Prénom** et Doe comme **Nom**.

    4. Indiquez votre adresse e-mail personnelle dans **E-mail**. Elle sera utilisée dans un prochain labo où vous recevrez un e-mail.

    5. Cliquez sur **Enregistrer &amp; fermer**.

    6. Vous devriez maintenant voir le contact créé dans la vue **Mes contacts actifs**.

3. Créer une nouvelle visite

    1. Sélectionnez **Visites** à partir de la navigation de gauche du plan du site.

    2. Cliquez sur **+ Nouveau**.

    3. Si nécessaire, remplissez les champs.

        1. **Nom** : Nouvelle visite test

        2. **Visiteur** : sélectionnez John Doe.

        3. **Début planifié** : sélectionnez la date de demain et 14h00 comme heure de début.

        4. **Fin planifiée** : sélectionnez la date de demain et 15h30 comme heure de fin.

- Cliquez sur **Enregistrer &amp; fermer**. La visite sera alors créée. Vous devez pouvoir la voir dans la vue Visites actives.

- Passez à la vue **Visites du jour** en utilisant la liste déroulante à côté de **Visites actives**. Vous ne devriez plus voir la nouvelle visite dans la vue, car elle est prévue pour demain.

1. Vous pouvez ajouter d’autres enregistrements test.

Votre application en cours d’exécution doit ressembler à ceci :

![](media/3-model-driven-app.png)

Félicitations ! Vous avez créé et configuré votre première application pilotée par modèle.

## Défis

- Sélectionnez des vues et des formulaires spécifiques pour les contacts.
