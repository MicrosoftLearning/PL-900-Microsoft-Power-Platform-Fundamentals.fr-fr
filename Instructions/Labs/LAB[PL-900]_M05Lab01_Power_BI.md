---
lab:
  title: "Labo\_5\_: Comment créer un tableau de bord simple"
  module: 'Module 5: Get Started with Power BI'
---

## <a name="lab-5-how-to-build-a-simple-dashboard"></a>Labo 5 : Comment créer un tableau de bord simple

## <a name="scenario"></a>Scénario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous allez créer un rapport et un tableau de bord Power BI qui permet de visualiser les données des visites sur le campus.

## <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Nous allons suivre les étapes ci-dessous pour concevoir et créer un tableau de bord Power BI :

-   Créer un rapport avec diverses visualisations des informations concernant les visites sur le campus

-   Utiliser une requête en langage naturel pour créer des visualisations supplémentaires

## <a name="prerequisites"></a>Prérequis

- Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**
- Participation au **Module 2 Labo 1 : modélisation des données**

## <a name="things-to-consider-before-you-begin"></a>Éléments à considérer avant de commencer

-   À quel public ce rapport est-il destiné ?
-   How will the audience consume the report? Typical device? Location?
-   Avez-vous suffisamment de données à visualiser ?
-   Quelles sont les caractéristiques utilisables pour analyser les données sur les visites ?

## <a name="exercise-1-create-power-bi-report"></a>Exercice 1 : Créer des rapports Power BI

**Objectif** : Dans cet exercice, vous allez créer un rapport Power BI basé sur les données de la feuille de calcul Excel que nous avons utilisée dans un exercice précédent.

### <a name="task-1-prepare-power-bi-service"></a>Tâche \#1 : Préparer le service Power BI

1.  Téléchargez [visites.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) et enregistrez sur votre ordinateur.

2.  Accédez à <https://app.powerbi.com/> et connectez-vous si nécessaire.

3.  Dans le coin inférieur gauche de l’écran, cliquez sur **Obtenir des données**.

4.  Sélectionnez le bouton **Obtenir** sous **Fichiers**, dans la section **Créer du contenu**.

5.  Sélectionnez **Fichier local**.

6.  Localisez et sélectionnez le fichier **visits.pbix** que vous avez téléchargé précédemment.

7.  Après le chargement des données, développez **Mon espace de travail** et sélectionnez **visites** (notez que le Type est défini sur **Rapport**).

8.  Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>. If <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> menu item is not visible click <bpt id="p2">**</bpt>...<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Edit<ept id="p3">**</ept>.

Vous avez terminé la configuration du service Power BI que vous utiliserez pour vos labos.

### <a name="task-2-create-chart-and-time-visualizations"></a>Tâche \#2 : Créer un graphique et des visualisations temporelles

1.  Appuyez sur l’icône **Graphique en secteurs** dans le panneau **Visualisations** pour insérer un graphique.

2.  Press the drop-down arrow beside <bpt id="p1">**</bpt>bc_building<ept id="p1">**</ept> in the Fields pane. Drag the <bpt id="p1">**</bpt>Building<ept id="p1">**</ept> field and drop it into <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> box.

3.  Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus.

4.  Redimensionnez le graphique en secteurs à l’aide des poignées d’angle afin que tous les composants du graphique soient visibles.

5.  Cliquez sur le rapport en dehors du graphique en secteurs pour le désélectionner et sélectionnez l’histogramme empilé dans le panneau **Visualisations**.

6.  Les visiteurs du campus sont actuellement enregistrés dans des journaux papier.

7.  Faites glisser le champ **Début** et déposez-le dans la zone cible **Axe X**.

8.  Dans le panneau Visualisations, cliquez sur le **x** en regard des champs **Année** et **Trimestre** pour ne laisser que les totaux **Mois** et **Jour** pour l’Axe.

9.  Redimensionnez le graphique selon les besoins, à l’aide des poignées d’angle.

10. Testez l’interactivité du rapport :

    1.  Cliquez sur différents secteurs sur le graphique en secteurs et observez les changements sur le rapport de temps.

    2.  Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

    3.  Explorez en remontant ou en descendant d’un niveau et sélectionnez diverses barres sur l’histogramme du temps pour observer les changements sur le graphique en secteurs.

11. Enregistrez le travail en cours en appuyant sur **Enregistrer**.

## <a name="exercise-2-create-power-bi-dashboard"></a>Exercice 2 : Créer un tableau de bord Power BI

### <a name="task-1-create-power-bi-dashboard"></a>Tâche \#1 : Créer un tableau de bord Power BI

1.  Vous pouvez accéder au rapport ouvert depuis la tâche précédente.

2.  Select <bpt id="p1">**</bpt>Pin to a dashboard<ept id="p1">**</ept> on the menu. Depending on the layout you may need to press <bpt id="p1">**</bpt>...<ept id="p1">**</ept> to show additional menu items.

3.  Sélectionnez **Nouveau tableau de bord** sur l’invite **Épingler au tableau de bord**.

4.  Entrez **Gestion du campus** comme un **Nom du tableau de bord** puis appuyez sur **Épingler un élément dynamique**.

5.  A pop-up will prompt you that the dashboard has been created. Select <bpt id="p1">**</bpt>Go to dashboard<ept id="p1">**</ept>.

6.  Testez l’interactivité des graphiques en secteurs et à barres affichés.

### <a name="task-2-add-visualizations-using-natural-language"></a>Tâche \#2 : Ajouter des visualisations à l’aide du langage naturel

1.  Au sein de votre tableau de bord **Gestion du campus**, sélectionnez la barre **Poser une question sur vos données**.

2.  Enter <bpt id="p1">**</bpt>buildings by number of visits<ept id="p1">**</ept> in Q&amp;A area. A bar chart will be displayed.

3.  Sélectionnez **Épingler un élément visuel**.

4.  Sélectionnez **Tableau de bord existant**, sélectionnez votre tableau de bord **Gestion du campus**, puis appuyez sur **Épingler**.

5.  Cliquez sur **Quitter les Q/R**.

Your <bpt id="p1">**</bpt>Campus Management<ept id="p1">**</ept> dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&amp;A visual.

Votre tableau de bord doit ressembler à ce qui suit :

![](media/5-powerbi-result.png)