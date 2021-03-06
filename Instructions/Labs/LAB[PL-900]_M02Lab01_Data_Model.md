---
lab:
  title: 'Labo 1 : Modélisation de données'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9edefbdf214d5a0f2e0693ffdf024dfc05c032c5
ms.sourcegitcommit: dbffa13e13419f5b9aadc894eb95fd16215b2ebf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2022
ms.locfileid: "146458360"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Module 2 : introduction à Microsoft Dataverse

# <a name="scenario"></a>Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visites sur le campus sont actuellement enregistrées dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Tout au long de ce cours, vous créerez des applications et effectuerez une automatisation pour permettre au personnel administratif et de sécurité du Bellows College de gérer et de contrôler l’accès aux bâtiments du campus.

Dans ce labo, vous accéderez à votre environnement et créerez une base de données Microsoft Dataverse ainsi qu’une solution pour effectuer le suivi de vos modifications. Vous allez également créer un modèle de données pour prendre en charge les exigences suivantes :

-   R1 – Suivre les informations pour les visites planifiées sur le campus

-   R2 - Enregistrer des informations de base pour identifier et suivre les visiteurs

-   R3 - Planifier, enregistrer et gérer les visites

Enfin, vous importerez des échantillons de données dans Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Étapes de labo de haut niveau

Pour préparer vos environnements d’apprentissage, vous devez :

* Créer une solution et un éditeur
* Ajouter les composants, nouveaux et existants, nécessaires pour répondre aux exigences de l’application Vous référer au [document de modèle de données](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) pour la description des métadonnées (tables et relations) Vous pouvez maintenir appuyée la touche CTRL et cliquer ou faire un clic droit sur le lien pour ouvrir le document de modèle de données dans une nouvelle fenêtre.
* créer une table Visite
* Importer les données de Visite avec une feuille de calcul Excel

## <a name="prerequisites"></a>Prérequis :

-   Participation au **Module 0 - Labo 0 : Valider l’environnement de labo**

## <a name="things-to-consider-before-you-begin"></a>Éléments à considérer avant de commencer :

-   Conventions de nommage : tapez les noms sans aucune erreur.

# <a name="exercise-1-create-new-table"></a>Exercice \#1 : Créer une table

**Objectif** : Dans cet exercice, vous allez créer une table personnalisée pour Visites. 

## <a name="task--1-create-visit-table-and-columns"></a>Tâche \#1 : Créer des tables et des colonnes Visite

La table **Visite** contient des informations sur les visites du campus, y compris le visiteur, les heures prévues et les heures réelles de chaque visite.

Nous aimerions attribuer à chaque visite un numéro unique qui peut être facilement saisi et interprété par un visiteur lorsque cela lui est demandé pendant le processus d’enregistrement de la visite.

>   Nous utilisons un comportement **indépendant du fuseau horaire** pour enregistrer les informations de date et d’heure, car l’heure d’une visite est toujours locale par rapport à l’emplacement du bâtiment et ne doit pas changer lorsqu’elle est vue depuis un autre fuseau horaire.

1. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) (si ce n’est déjà fait).

2. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

3. Dans le volet de navigation de gauche, développez Dataverse, puis sélectionnez Tables.

4. Cliquez sur **Nouvelle table**.

5. Entrez **Visite** comme **Nom d’affichage**.

6. Cliquez sur **Enregistrer**. Cette action commence l’approvisionnement de la table en arrière-plan, tandis que vous pouvez commencer à ajouter d’autres colonnes.

7. Une fois la table créée, sous la section **Schéma**, sélectionnez **Colonnes**. 

8. Sélectionnez **Nouvelle colonne** et configurez comme suit : 

    - Entrez **Début prévu** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans **Obligatoire**, sélectionnez **Contrainte obligatoire**.

    - Développez la section **Options avancées**.

    - Dans le champ **Comportement**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

9. Créer une colonne Fin prévue 

    - Cliquez sur **Ajouter une colonne**.

    - Entrez **Fin prévue** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans **Obligatoire**, sélectionnez **Contrainte obligatoire**.

    - Développez la section **Options avancées**.

    - Dans le champ **Comportement**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

10. Créer une colonne Début réel

    - Cliquez sur **Ajouter une colonne**.

    - Entrez **Début réel** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans le champ **Obligatoire**, laissez comme **Facultatif**.

    - Développez la section **Options avancées**.

    - Dans le champ **Comportement**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

11. Créer une colonne Fin réelle

    - Cliquez sur **Ajouter une colonne**.

    - Entrez **Fin réelle** comme **Nom d’affichage**.

    - Sélectionnez **Date et heure** comme **Type de données**.

    - Dans le champ **Obligatoire**, laissez ceci comme **Optionnel**.

    - Développez la section **Options avancées**.

    - Dans le champ **Comportement**, sélectionnez **Indépendant du fuseau horaire**.

    - Cliquez sur **Enregistrer**.

12. Créer une colonne Code

    - Cliquez sur **Ajouter une colonne**.

    - Entrez **Code** comme **Nom d’affichage**.

    - Sélectionnez **Numérotation automatique** comme **Type de données**.

    - Sélectionnez **Nombre préfixé de date** pour **Type de numérotation automatique**.

    - Cliquez sur **Enregistrer**.

13. Créer une colonne de recherche Visiteur

    - Cliquez sur **Ajouter une colonne**.

    - Entrez **Visiteur** comme **Nom d’affichage**.

    - Sélectionnez **Recherche** comme **Type de données**.

    - Sélectionnez **Contact** comme **Table associée**.

    - Développez la section **Options avancées**.

    - Entrez **visitor_id** dans **nom de la relation**.

    - Cliquez sur **Enregistrer**.

 

Exercice n° 2 : Importer des données

**Objectif** : Au cours de cet exercice, vous apprendrez à importer des échantillons de données dans la base de données Dataverse.

Tâche n°1 : Importez le fichier Visits.xls.

Dans cette tâche, vous allez importer des données Visite à partir d’un fichier Excel.

1. Le fichier **Visits.xls** doit être stocké sur votre bureau. Si ce n’est pas le cas, téléchargez [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx).

2. Connectez-vous à [https://make.powerapps.com](https://make.powerapps.com/) si ce n’est déjà fait.

3. Sélectionnez votre environnement **Exercices pratiques [mes initiales]** en haut à droite, si ce n’est déjà fait.

4. Dans le volet de navigation de gauche, développez **Dataverse**, puis sélectionnez Tables.

Ces éléments peuvent apparaître comme Données > Tables sur votre écran.

5. Recherchez et ouvrez la table **Visite** que vous avez créée dans l’exercice précédent.

6. Dans le menu en haut, sélectionnez la flèche déroulante à côté de **Importer**, puis sélectionnez **Importer les données à partir d’Excel**.

7. Dans le menu qui s’affiche, sélectionnez le bouton **Charger**.

8. Recherchez et sélectionnez le fichier **Visits.xls** que vous avez téléchargé précédemment. (Notez que le chargement du fichier peut prendre une minute ou deux. Ne vous inquiétez pas si vous recevez un message indiquant des erreurs de mappage. Nous les corrigerons juste après ceci.)

9. Sélectionnez **Mapper des colonnes**.

10. Mappez les colonnes comme indiqué ci-dessous :

| Colonnes de la base de données Visite| Valeurs sources |
| - |
| Fin réelle| Fin réelle |
| Début réel| Début réel |
| Code| Code |
| Nom| Nom |
| Fin prévue| Fin planifiée |
| Scheduled Start| Début planifié |


11. Laissez tous les autres champs sur **Non défini**.

12. Dans le coin supérieur droit de l’écran, sélectionnez **Enregistrer les modifications**.

13. Dans l’écran **Importer des données**, vérifiez que l’état du mappage indique « Le mappage a réussi ».

14. Sélectionnez **Importer** en haut à droite pour terminer l’importation de données.

**Remarque :** L’importation de vos données dans votre table peut prendre plusieurs minutes. Ne vous inquiétez pas si vous recevez des erreurs, c’est normal et cela n’aura aucun impact sur le reste du cours.

Tâche n° 2 : Vérifier une importation de données

1. Une fois vos données importées, utilisez le volet de navigation à gauche de l’écran pour resélectionner la table **Visite**.

2. Vérifiez que vous voyez les données importées sous la section **Visiter les colonnes et les données**. 

Félicitations, vous avez créé une table et importé des données.
