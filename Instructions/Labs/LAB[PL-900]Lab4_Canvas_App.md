---
lab:
  title: "Labo\_4\_: Créer une application de canevas"
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 2: Build a canvas app'
---
## Objectif d’apprentissage

Dans cet exercice, vous allez utiliser Copilot pour créer une application canevas que les employés peuvent utiliser pour demander et gérer les demandes de congé et d’achat d’équipement. Une fois l’application créée, vous allez utiliser le concepteur Copilot et Power Apps pour modifier l’application.

À l’issue de ce labo, vous pourrez :

- Utilisez Copilot pour vous aider à créer un modèle de données pour prendre en charge votre application.
- Modifiez une application canevas.

### Scénario

Contoso Consulting est une organisation de services professionnels spécialisée dans les services de conseil en informatique et en IA Ils cherchent à créer une application de congé que les employés peuvent utiliser pour demander un congé.

### Détails du labo

Avant de commencer cet exercice, vous devez avoir effectué le labo suivant :

- **Lab 2 – Créer un modèle de données**

> **Important** : ce labo utilise l’IA pour générer les composants. Étant donné que les résultats de l’IA peuvent varier, il est important de noter que vos résultats peuvent être différents (mais similaires) de ce qui est défini dans le labo. Les concepts de base décrits dans le labo seront les mêmes, peu importe ce qui a été créé ou ce qu’il a été nommé. Si les tables et colonnes ne correspondent pas exactement, vous devrez peut-être ajuster ce qui a été créé pour vous.

La durée de cet exercice est estimée entre **60 et 75** minutes.
> **Remarque :** si vous rencontrez un message d’erreur **Besoin d’attention** sur la table lors de la création d’une colonne de choix avec Copilot, vous pouvez créer la colonne manuellement en suivant les étapes ci-dessous :
1. Sélectionnez **Options d’affichage**, puis sélectionnez **Afficher les données**. La structure de la table devient visible.
1. Cliquez sur **Nouvelle colonne** pour ajouter une nouvelle colonne.

## Tâche 1 : Connectez-vous à Power Apps et explorez l’interface

1.  Ouvrez un navigateur web et accédez au portail de création [Power Apps](https://make.powerapps.com/).
1.  À l’aide de la barre de navigation à gauche, sélectionnez **Créer**.
1.  Sous **Créer vos applications**, choisissez **Démarrer avec Copilot**.
1.  Dans l’écran **Décrivez les tables que vous souhaitez que Copilot génère**, tapez : *` I want to store time off requests sent by employees. The table should identify the start and end times of the request.`*
1.  Sélectionnez le bouton **Options de table**. Dans le menu qui s’affiche, sélectionnez **Un tableau**.

    ![Capture d’écran de prise en main de l’écran Copilot](media/60a2ec72988f48c91df7c370532cb331.png)

1.  Sélectionnez le bouton **Générer**.

    Copilot doit avoir créé une table de **Demande de congé**. Ensuite, nous allons ajouter d’autres colonnes à la table.

    **Remarque** : Si nécessaire, veuillez ajouter Nom de la table au prompt.

1.  Dans le volet **Copilot**, entrez : *`Add a choice column called Time Off Reason.`*
1.  Dans le volet **Copilot**, ajoutez les invites suivantes de façon individuelle.
    - *`Add a choice column named Time off Type.`*
    - *`Add a Date column called Submission Date.`*
    - *`Add a choice column to the Time Off request table called Approval Status.`*
    - *`Add a multi-line text column called Request Details.`*

    Votre table de congé doit ressembler à l’image suivante :

    ![Capture d’écran de la table de demande de congé terminée ](media/2ac256daafe1853e5367852467690c76.png)

    Ensuite, nous allons ajouter la table utilisateur au modèle de données afin de pouvoir associer des demandes de congé à des utilisateurs spécifiques.

1.  Dans la **Barre de commandes**, sélectionnez **+ Table existante**.
1.  Passez de **Recommandé** à **Toutes les tables**.
1.  Dans le champ **Recherche**, entrez **Utilisateur**.
1.  Sélectionnez la table **Utilisateur**, puis cliquez sur le bouton **Ajouter Sélectionné**.
1.  Dans la **Barre de commandes**, sélectionnez **Créer des relations**.
1.  Configurez la relation comme suit :

    -   **Un :** Utilisateur
    -   **Plusieurs :** Demande d'absence
    -   **Nom d’affichage** : `Requesting Employee`
  
1.  Cliquez sur **Terminé**.

    Votre modèle de données terminé doit ressembler à l’image :

    ![Capture d’écran du modèle de données terminé ](media/daa74d51e2ceada8e1e8b004cae9942a.png)

1.  Sélectionnez le bouton **Enregistrer et ouvrir l’application**.

> [!NOTE]
> La création de votre nouvelle application peut prendre plusieurs minutes.

## Tâche 2 : Personnaliser votre nouvelle application

Maintenant que votre nouvelle application a été créée, nous allons y apporter quelques modifications pour qu’elle réponde au mieux à nos besoins. Dans un premier temps, nous allons apporter quelques modifications à l’Écran de bienvenue.

1.  Une fois votre nouvelle application ouverte, sélectionnez l’espace réservé **Image** au-dessus du texte **Demandes de congés**.
1.  Dans le menu qui s’affiche, sélectionnez **Modifier** \> **Charger**.
1.  Choisissez l’image **Congé** dans le dossier fichiers de classe, puis sélectionnez **Ouvrir**.
1.  Ensuite, sélectionnez l’espace réservé **Image** au-dessus de **Utilisateurs**.
1.  Dans le menu qui s’affiche, sélectionnez **Modifier** \> **Charger**.
1.  Choisissez l’image **Employé** dans le dossier fichiers de classe, puis sélectionnez **Ouvrir**.

    Ensuite, nous allons ajuster la taille des images pour faciliter la lecture des utilisateurs. En outre, nous allons ajuster le texte affiché pour chaque élément.

1.  Dans la **Barre de commandes**, sélectionnez le bouton **Propriétés**. (*Situé juste à droite du bouton Édition.*)
1.  Sélectionnez l’image **Congé** que vous avez ajoutée précédemment.
1.  Dans le volet **Propriétés**, configurez l’image comme suit :
    
    -   **Position de l’image :** Remplissage
    -   **Largeur :** 300
    -   **Hauteur :** 300
      
1.  Répétez l’étape précédente pour définir la **Hauteur** et la **Largeur** de l’image de l’**Employé** sur **300** x **300**.
1.  Sélectionnez le texte ci-dessous **Demandes de congés**.
1.  Dans le volet **Propriétés**, sélectionnez le champ **Texte** et remplacez le texte par : *`Create, View, and Manage you time off requests.`*
1.  Sélectionnez le texte de l’**Écran de bienvenue** dans l’**En-tête**.
1.  Dans le volet **Propriétés** à droite, sélectionnez le champ **Logo**.
1.  Dans le menu qui s’affiche, sélectionnez **Charger**.
1. Sélectionnez le **Logo Contoso** dans vos fichiers de classe et sélectionnez **Ouvrir**.
1. Dans le volet **Propriétés** sous le groupe **Style** et thème, sélectionnez l’icône de couleur **Remplissage**.
1. Cliquez sur l’onglet **Personnalisé**.
1. Remplacez la couleur **Hexadécimale** par : `101E2B`
1. Vérifiez que l’**En-tête** est toujours sélectionné et modifiez le **Titre** en `Contoso Employee Hub`.
1. Dans la barre **Commande**, sélectionnez le bouton **Enregistrer** pour enregistrer l’application.
1. Dans l’écran **Enregistrer**, définissez le **Nom** sur `Contoso Employee Hub`, puis sélectionnez **Enregistrer.**

    Votre application ressemblera à l’image.

    ![Capture d’écran de l’écran de bienvenue de l’application Canvas.](media/533c80cc861941b6a353b56bfc0dbc0f.png)

## Tâche 3 : ajouter un nouvel écran à votre application.

Alors que vous développez l’application, l’un de vos responsables vous contacte et vous demande si les employés pourraient également utiliser cette application pour vérifier l’équipement. Contoso stocke déjà les informations relatives au contrôle de l’équipement dans Dataverse, il suffit donc de rendre ces informations disponibles dans l’application.

1.  Une fois votre application toujours ouverte, développez le volet **Copilot** (si nécessaire). Dans Copilot, entrez ce qui suit : *`Add a new screen called Equipment Checkout.`*
1.  Sélectionnez **Envoyer**.
1.  Sélectionnez le bouton **Conserver** pour accepter l’écran.
1.  Un nouvel écran appelé **Vérification de l’équipement** est ajouté à votre application.
1.  Dans l’écran **Vérification de l’équipement**, cliquez sur **Avec la disposition**, puis choisissez la disposition **Barre latérale**.
1.  Développez les différents conteneurs jusqu’à ce que **SideBarContainer** soit visible.

    ![Capture d’écran de l’arborescence ](media/cde6257402b7a8786e679ab64ee0f882.png)

1.  Cliquez avec le bouton droit sur **SidebarContainer** et renommez-le **EquipContainer1**.
1.  Une fois le conteneur **EquipContainer1** sélectionné, cliquez sur le bouton **Ouvrir le menu d’insertion**.
1.  Dans la fenêtre **Recherche**, entrez **Galerie**, puis sélectionnez **Galerie verticale**.
1.  Lorsque vous êtes invité à fournir une source de données dans le champ **Recherche** qui s’affiche, entrez **Équipement** et sélectionnez la table **Équipement**.
1. Dans l’**arborescence** située à gauche de l’écran, sélectionnez le contrôle **Gallery1** que vous venez d’ajouter.
1. Faites un clic droit sur le nom de la galerie, choisissez **Renommer**, et renommez-le en `Equipment List`.
1. Passez sur la galerie **Liste des équipements**. Dans la barre d’outils qui apparaît au-dessus de la galerie, sélectionnez **Disposition**.
1. Sélectionnez l’option **Disposition du titre et du sous-titre**.
1. Lorsque la galerie **Liste des équipements** est sélectionnée, dans le volet **Propriétés**, configurez-la comme suit :

    -   **Largeur** : `360`
    -   **Hauteur flexible :** Activé(e)
    -   **Hauteur minimale :** `287`

    Ensuite, nous allons ajouter un conteneur supplémentaire au conteneur **EquipmentContiner1** pour stocker un contrôle de recherche que nous allons utiliser pour filtrer le contenu de la galerie **Liste des équipements**.

1.  Dans l’**arborescence**, sélectionnez **EquipContainer1**.
1.  Placez le curseur sur le conteneur et sélectionnez l’icône **Copilot**.
1.  Entrez le texte suivant : *`Insert a Horizontal container.`*

    ![Capture d’écran de l’insertion d’une galerie dans un conteneur.](media/b9b784ea5625469c8785650b977f32d1.png)

1.  Sélectionnez le bouton **Conserver**.
1.  Un nouveau conteneur est ajouté en bas du conteneur **EquipContainer1**.
1.  Dans l’**arborescence**, cliquez, maintenez le bouton enfoncé et faites glisser le nouveau conteneur, puis placez-le au-dessus de la galerie **Liste des équipements**.
1.  Renommez le conteneur en `EquipSearchContainer`.
1.  Lorsque le conteneur **EquipSearchContainer** est sélectionnée, dans le volet **Propriétés**, configurez-le comme suit :
    
    -   **Largeur minimale :** `0`
    -   **Hauteur flexible :** Désactivé(e)
    -   **Hauteur** : `44`
    
1.  Lorsque le conteneur **EquipSearchContainer** est sélectionné, sélectionnez le bouton **Ouvrir le menu d’insertion**.
1. Dans le champ **Recherche**, entrez **Texte**, puis sélectionnez **Entrée de texte**.
1. Renommez le champ **Entrée de texte**, en `EquipSearchInput`.
1. Lorsque **EquipSearchInput** est sélectionné, dans le volet **Propriétés**, configurez-le comme suit :

    -   **Par défaut :** Vide (rien)
    -   **Texte d’information :** Rechercher
    -   **Police :** Ouvrir Sans
    -   **Taille de police :** 14
    -   **Marge intérieure** (Les valeurs ci-dessous peuvent déjà y être.)
        -   **Haut de la page :** 5
        -   **Bas de la page :**  5
        -   **Gauche :** 12
        -   **Droite :** 5
    -   **Hauteur :** 44
    -   **Largeur flexible :** Activé(e)
    -   **Largeur minimale :** 0

        ![Capture d’écran des propriétés d’entrée de recherche.](media/b0e092b4795edf58dad1153209639051.png)

1. Dans l’**arborescence**, sélectionnez **EquipSearchContainer**.
1. Placez le curseur sur le conteneur, sélectionnez l’icône **Copilot**, puis entrez *`Add a Search Icon.`*
1. Sélectionnez **Conserver**.

    > **Remarque :** Si Copilot ajoute la mauvaise icône, supprimez-la et insérez la loupe manuellement.

1. Lorsque l’icône **Recherche** est sélectionnée, dans le volet **Propriétés**, configurez le contrôle comme suit :

    -   **Remplissage**
        -   **Haut de la page :** 10
        -   **Bas de la page :** 10
        -   **Gauche :** 10
        -   **Droite :** 10
    -   **Hauteur :** 44
    -   **Largeur :** 44

    ![Capture d’écran des propriétés de l’icône de recherche](media/cb3305731a09bca0bbf166d55d9822a4.png)



    Enfin, nous allons configurer la galerie **Liste des équipements** pour remplir ses données en fonction du texte entré dans le champ de contrôle de recherche.

1.  Sélectionnez la galerie **Liste des équipements** que nous avons créée précédemment.
1.  Dans la propriété **Éléments**, entrez la formule suivante : `Search([@'Equipment'], EquipSearchInput.Text, 'Equipment Name',Category)`

    ![Capture d’écran de la formule PowerFx d’éléments.](media/powerfx-formula.png)

1. Dans la barre **Commande**, sélectionnez le bouton **Enregistrer** pour enregistrer votre application.

> **Important :** Si vous avez copié et collé la formule dans la barre de formule, il est possible que les « » soient incorrects pour l’équipement et le nom de l’équipement. Si vous obtenez une erreur de formule, essayez de les supprimer et de les entrer à nouveau.

## Tâche 4 : générer un conteneur pour afficher les opérations d’enregistrement.

Lorsqu’un utilisateur sélectionne un enregistrement dans la liste Équipement, nous voulons ouvrir l’enregistrement dans un autre conteneur pour lui permettre de modifier l’enregistrement sélectionné.

1.  Sélectionnez **MainContainer** et renommez-le en `DetailsContainer`.
1.  Dans **DetailsContainer**, sélectionnez le bouton **Insérer**.
1.  Dans le champ **Recherche**, entrez **Conteneur** et choisissez **Conteneur vertical**.
1.  Faites un clic droit et **renommez** le conteneur en `RecordDetails`.
1.  Dans le conteneur **RecordDetails**, sélectionnez le bouton **Insérer**.
1.  Dans le menu **Insertion**, sélectionnez **Modifier le formulaire**.
1.  Dans l’écran de sélection de la source de données, sélectionnez **Équipement**. *(Cela peut prendre jusqu’à 30 secondes pour que les données s’affichent).*
1.  Faites un clic droit sur le formulaire que vous venez d’ajouter et **renommez-le** en `EquipmentForm`.
1.  Dans le volet **Propriétés**, sélectionnez l’onglet **Avancé** et définissez la propriété **Élément** sur : `'Equipment List'.Selected` *(Le formulaire sera alors rempli avec l’enregistrement actuellement sélectionné.)*
1. Sélectionnez l’onglet **Affichage** et configurez le formulaire comme suit :

    -   **Colonnes :** 2
    -   **Mode par défaut :** Modifier

    Nous allons maintenant ajouter un autre conteneur qui sera utilisé pour contrôler les opérations sur le formulaire.

1.  Vérifiez que vous avez sélectionné **DetailsContainer**.
1.  Sélectionnez l’icône **Copilot** qui s’affiche. Entrez les informations suivantes : *`Insert a horizontal container.`*
1.  Sélectionnez **Conserver**.
1.  Faites un clic droit sur le conteneur et **renommez-le** en `SelectedRecord1`
1.  À l’aide de l’**arborescence**, déplacez le conteneur **SelectedRecord1** au-dessus du conteneur **RecordDetails**.
1.  Configurez le conteneur **SelectedRecord1** comme suit :
    
    -   **Largeur minimale :** 250
    -   **Hauteur flexible :** Désactivé(e)
    -   **Height** : 50
    
1.  Lorsque le conteneur **SelectedRecord1** est sélectionné, sélectionnez le bouton **Insérer**.
1.  Sélectionnez **Étiquette de texte**.
1.  Donnez le nom `SelectedRecordTitle` au contrôle Libellé de texte.
1. Configurez **SelectedRecordTitle** comme suit :

    1.  **Remplissage**
        1.  **Haut de la page :** 5
        2.  **Bas de la page :** 5
        3.  **Gauche :** 30
        4.  **Droite :** 5
    2.  **Largeur flexible :** Activé(e)
    3.  **Largeur minimale :** 150
    4.  **Hauteur :** 40
       
1. Sélectionnez le conteneur **SelectedRecord1**, puis cliquez sur le bouton **Insérer**.
1. Dans le champ **Recherche**, entrez **Enregistrer**, puis sélectionnez l’icône **Enregistrer**.
1. Configurez le bouton **Enregistrer** comme suit :

    -   **Hauteur :** 40
    -   **Width** : 40
      
1. Sélectionnez la propriété **OnSelect** et entrez la formule suivante : `SubmitForm(EquipmentForm)`.

    ![Capture d’écran de la formule PowerFx OnSelect.](media/e5b22c91a437e6918269d65e2616afc8.png)

## Tâche 5 : modifier l’en-tête sur la page.

La dernière étape de création de cet écran consiste à remplir le conteneur du lecteur avec des données.

1.  Sélectionnez **HeaderContainer** en haut de l’application.
1.  Sélectionnez le bouton **Insérer**.
1.  Sélectionnez **Libellé de texte**.
1.  Configurez le contrôle **Étiquette de texte** comme suit :
   
    -   **Text**: `Equipment Checkout`
    -   **Police :** Ouvrir Sans
    -   **Taille de police :** 16
    -   **Épaisseur de police :** Demi-gras
    -  **Remplissage**
        -   **Haut de la page :** 16
        -   **Bas de la page :** 16
        -   **Gauche :** 16
        -   **Droite :** 16
    -   **Hauteur :** 40
    -   **Largeur flexible :** Activé(e)

        ![Capture d’écran des propriétés de l’étiquette de texte.](media/088cafeec651b099fa49ac1f151cd228.png)

1.  Sélectionnez **HeaderContainer**, choisissez **Insérer**, puis sélectionnez l’**icône Accueil**.
1.  Définissez la propriété **OnSelect** du bouton d’accueil sur : `Back()`

    ![Capture d’écran de la commande de navigation Retour.](media/38d0e5367ee41da58ac9902f8056b1af.png)

## Tâche 6 : Terminer la configuration de l’Écran de bienvenue

Après examen, nous avons jugé inutile de créer d’utilisateurs dans cette application, et nous allons donc modifier l’Écran de bienvenue pour vous permettre d’accéder à la vérification des équipements.

1.  À l’aide de l’**Arborescence**, sélectionnez l’**Écran de bienvenue**.
1.  Sélectionnez l’**image** au-dessus d’**Utilisateurs**.
1.  Dans le menu qui s’affiche, sélectionnez **Modifier**, puis choisissez **Charger**.
1.  Recherchez l’image **Équipement** dans votre dossier étudiant, puis choisissez **Ouvrir**.
1.  Définissez la propriété **OnSelect** de l’image sur : `Navigate('Equipment Checkout')`
1.  Sélectionnez le texte **Utilisateurs** et définissez la propriété **Texte** sur `Equipment`.
1.  Sélectionnez le **texte** en dessous d’**Équipement** et remplacez la propriété **Texte** par : `Check out equipment and edit reservations`.

    ![Une capture d’écran d’un contenu généré par l’IA de l’ordinateur peut être incorrecte.](media/561d1e8cd023541761b6523138c2fde8.png)

1. Sélectionnez le bouton **Enregistrer** pour enregistrer votre application.

## Tâche 7 : Tester votre application

1.  Dans la **Barre de commandes**, sélectionnez le bouton **Lire**.
1.  Sélectionnez l’image **Équipement**.
1.  Dans le champ **Recherche**, entrez **Électronique**. (*Remarquez la façon dont la liste est filtrée*)
1.  Sélectionnez l’enregistrement **Ordinateur portable**.
1.  Changez la **Catégorie** en **Meubles**.
1.  Sélectionnez le bouton **Enregistrer**.
1.  Notez comment la catégorie **Ordinateur portable** change en **Meubles**.
1.  Sélectionnez le bouton **Accueil**.
1.  Sélectionnez le **X violet** pour quitter le mode **Aperçu**.

## Tâche 8 : enregistrer et publier l’application

**Objectif :** Enregistrez et publiez l’application pour la rendre accessible sur les navigateurs web, les appareils mobiles ou les plateformes incorporées telles que SharePoint ou Teams.

1.  Dans Power Apps Studio, sélectionnez le bouton **Enregistrer**.
1.  Cliquez sur le bouton **Publier**.
1.  Choisissez **Publier cette version**.






