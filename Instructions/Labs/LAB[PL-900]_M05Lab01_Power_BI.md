---
lab:
  title: 'Labo 7 : Comment créer un tableau de bord simple'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: b707cbf6b60af3b6d6a166565ccdeaeec844cb4a
ms.sourcegitcommit: fc79a9b68a8235b37fd90ef84ba8ae1aa2e581f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2022
ms.locfileid: "144424652"
---
# <a name="module-5-get-started-with-power-bi"></a>Module 5 : démarrage de Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Labo : Comment créer un tableau de bord simple

# <a name="scenario"></a>Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visiteurs du campus sont actuellement enregistrés dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous allez créer un tableau de bord Power BI qui visualise les données sur les visites sur le campus.

# <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Nous allons suivre les étapes ci-dessous pour concevoir et créer un tableau de bord Power BI :

-   Se connecter à Dataverse

-   Transformez les données pour inclure des descriptions conviviales pour les lignes associées (recherches)

-   Créez et publiez un rapport avec diverses visualisations des informations sur les visites du campus

-   Utiliser une requête en langage naturel pour créer des visualisations supplémentaires

-   Créer une vue mobile du tableau de bord Power BI

## <a name="prerequisites"></a>Prérequis

-   Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

-   Participation au **Module 2 - Labo 1 : Présentation de Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Éléments à considérer avant de commencer

-   À quel public ce rapport est-il destiné ?

-   Comment les participants utiliseront-ils le rapport ? Appareil courant ? L’emplacement ?

-   Avez-vous suffisamment de données à visualiser ?

-   Quelles sont les caractéristiques utilisables pour analyser les données sur les visites ?

# <a name="exercise-1-create-power-bi-report"></a>Exercice \#1 : Créer des rapports Power BI

**Objectif** : Dans cet exercice, vous allez créer un rapport Power BI basé sur les données de la feuille de calcul Excel que nous avons utilisée dans un exercice précédent.

## <a name="task-1-prepare-power-bi-service"></a>Tâche \#1 : Préparer le service Power BI

1.  Téléchargez [visites.pbix](../../Allfiles/visits.pbix) et enregistrez sur votre ordinateur.

2.  Accédez à <https://app.powerbi.com/> et connectez-vous si nécessaire.

3.  Dans le coin inférieur gauche de l’écran, cliquez sur **Obtenir des données**.

4.  Sélectionnez le bouton **Obtenir** sous **Fichiers**, dans la section **Créer du contenu**.

5.  Sélectionnez **Fichier local**.

6.  Localisez et sélectionnez le fichier **visits.pbix** que vous avez téléchargé précédemment.

7.  Une fois le chargement des données terminé, sélectionnez le rapport **visites** (notez que le Type est défini sur **Rapport**).

8.  Cliquez sur **Modifier**. Si l’élément de menu **Modifier** n’est pas visible cliquez sur **...** , puis sélectionnez **Modifier**.

Vous avez terminé la configuration du service Power BI que vous utiliserez pour vos labos. 

## <a name="task-2-create-chart-and-time-visualizations"></a>Tâche \#2 : Créer un graphique et des visualisations temporelles

1.  Appuyez sur l’icône **Graphique en secteurs** dans le panneau **Visualisations** pour insérer un graphique.

2.  Appuyez sur la flèche déroulante en regard de **bc_Building** dans le volet Champs. Faites glisser le champ **Bâtiment** et déposez-le dans la zone **Légende**.

3.  Appuyez sur la flèche déroulante en regard de **bc_Visit** dans le volet Champs. Faites glisser le champ **Visite** et déposez-le dans la zone **Valeurs**.

4.  Redimensionnez le graphique en secteurs à l’aide des poignées d’angle afin que tous les composants du graphique soient visibles.

5.  Cliquez sur le rapport en dehors du graphique en secteurs pour le désélectionner et sélectionnez l’histogramme empilé dans le panneau **Visualisations**.

6.  Appuyez sur la flèche déroulante en regard de **bc_Visit** dans le volet Champs. Faites glisser le champ **Visite** et déposez-le dans la zone **Valeurs**.

7.  Faites glisser le champ **Début** et déposez-le dans la zone cible **Axe**.

8.  Dans le panneau Visualisations, cliquez sur le **x** en regard des champs **Année** et **Trimestre** pour ne laisser que les totaux **Mois** et **Jour** pour l’Axe.

9.  Redimensionnez le graphique selon les besoins, à l’aide des poignées d’angle.

10. Testez l’interactivité du rapport :

    1.  Sélectionnez différents secteurs sur le graphique en secteurs et observez les changements sur le rapport de temps.

    2.  Cliquez sur l’histogramme. Appuyez sur la flèche vers le bas pour activer le mode **Descendre dans la hiérarchie**, puis cliquez sur une colonne pour descendre au niveau suivant (jours). 
    
    3.  Explorez en remontant ou en descendant d’un niveau et sélectionnez diverses barres sur l’histogramme du temps pour observer les changements sur le graphique en secteurs.

11. Enregistrez le travail en cours en appuyant sur **Enregistrer**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Exercice \#2 : Créer un tableau de bord Power BI

## <a name="task-1-create-power-bi-dashboard"></a>Tâche \#1 : Créer un tableau de bord Power BI

1.  Vous pouvez accéder au rapport ouvert depuis la tâche précédente.

2.  Sélectionnez **Épingler à un tableau de bord** dans le menu. Selon la disposition, vous devrez peut-être appuyer sur **...** pour afficher des éléments de menu supplémentaires.

3.  Sélectionnez **Nouveau tableau de bord** sur l’invite **Épingler au tableau de bord**.

4.  Entrez **Gestion du campus** comme un **Nom du tableau de bord** puis appuyez sur **Épingler un élément dynamique**.

5.  Sélectionnez **Mon espace de travail** en haut, puis le tableau de bord [**Votre nom] Gestion du campus**.

6.  Une fenêtre contextuelle vous indique que le tableau de bord a été créé. Sélectionnez **Accéder au tableau de bord**.

7.  Testez l’interactivité des graphiques en secteurs et à barres affichés.

## <a name="task-2-add-visualizations-using-natural-language"></a>Tâche \#2 : Ajouter des visualisations à l’aide du langage naturel

1.  Au sein de votre tableau de bord **Gestion du campus**, sélectionnez la barre **Poser une question sur vos données**.

2.  Entrez **bâtiments par nombre de visites** dans la zone Questions et réponses. Un graphique à barres s’affiche.

3.  Sélectionnez **Épingler un élément visuel**.

4.  Sélectionnez **Tableau de bord existant**, sélectionnez votre tableau de bord **Gestion du campus**, puis appuyez sur **Épingler**.

5.  Cliquez sur **Quitter les Q/R**.

Votre tableau de bord **Gestion du campus** doit s’afficher avec trois visuels. Vous devrez peut-être faire défiler vers le bas pour voir le nouveau visuel de questions et réponses.

Votre tableau de bord doit ressembler à ce qui suit :

![](media/5-powerbi-result.png)
