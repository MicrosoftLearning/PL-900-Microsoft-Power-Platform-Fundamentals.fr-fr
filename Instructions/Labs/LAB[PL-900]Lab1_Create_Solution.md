---
lab:
  title: "Labo\_1\_: créer une solution"
  learning path: 'Learning Path: Manage the Microsoft Power Platform environment'
  module: 'Module 1: Describe Microsoft Dataverse'
---

## Objectif d’apprentissage

Dans cet exercice, vous allez créer une solution Power Platform pour stocker les différents composants que vous générez. Dans Power Platform, les solutions sont utilisées pour regrouper différents composants et fournir une transportabilité. La solution que vous créez dans cet exercice sera utilisée tout au long du cours.

### Scénario

Contoso Consulting est une organisation de services professionnels spécialisée dans les services de conseil en informatique et en IA Tout au long de l’année, Contoso Consulting propose de nombreux événements différents à leurs clients. Il s’agit notamment de salons professionnels au cours desquels de nombreux partenaires viennent fournir des informations sur les nouveaux produits, les tendances du marché et les services. D’autres ont lieu tout au long de l’année et sont des webinaires rapides qui servent à fournir des détails sur des produits individuels.

Contoso aimerait utiliser Power Platform pour créer une solution de gestion des événements qui lui permettrait de gérer les différents événements organisés tout au long de l’année.

Dans cet exercice, vous allez créer une solution qui sera utilisée pour la gestion du cycle de vie des applications et pour regrouper les différentes applications, sites et flux que nous créons afin qu'ils puissent être facilement gérés et transportés.

La durée de cet exercice est estimée entre **15 et 20** minutes.

À l’issue de cet exercice, vous pourrez :

- créer une solution de gestion des événements
- ajouter les tables Compte et Contact existantes à la solution
- créer une table appelée Événements à partir de la solution

## Tâche 1 : créer une solution de gestion des événements

1.  Ouvrez le [Power Apps Maker Portal](https://make.powerapps.com).
2.  Accédez à **Solutions**.
3.  Dans la barre de commandes, sélectionnez **Nouvelle solution**.
4.  Dans l’écran de la nouvelle solution, procédez à la configuration suivante :
    - **Nom d’affichage :** Gestion des événements
    - **Nom :** Gestion des événements
5.  Sous **Éditeur**, sélectionnez **+ Nouvel éditeur**
6.  Configurez le nouvel éditeur comme suit :
    - **Nom d'affichage :** EventMSLEventMSLearnarn
    - **Nom :** EverntMSLearn
    - **Préfixe :** mslearn
    - **Préfixe de valeur de choix :** Conservez la valeur par défaut

![Capture d’écran de l’écran Créer un nouvel éditeur.](media/61fa62c324d424f7c73c8291a0724130.png)

7.  Cliquez sur le bouton **Enregistrer** pour enregistrer l’éditeur.
8.  Dans le champ **Éditeur**, sélectionnez l’éditeur **EventMSlearn** que vous venez de créer.
9.  Sélectionnez **Définir comme solution préférée**.

![Capture d’écran de la solution terminée](media/f968526926661bfa401f10742e6f376f.png)

10.  Sélectionnez **Créer**.

## Tâche 2 : Ajoutez des composants existants à une solution.

Maintenant que nous avons créé une solution pour stocker nos composants, nous allons y ajouter certains tableaux existants. Nous allons ajouter les tableaux Compte et Contact afin qu’elles puissent être facilement utilisées dans nos différentes applications, flux et sites de Gestion d’événements. Tout d’abord, nous allons ajouter le tableau Account à la solution.

1.  Si nécessaire, accédez à la solution **Gestion des événements** que vous avez créée dans la tâche précédente.
2.  Dans la **barre de commandes**, sélectionnez **Ajouter**.
3.  Dans le menu qui s’affiche, sélectionnez **Tableau**.
4.  Sélectionnez le tableau **Compte**, puis sélectionnez **Suivant.**
5.  Dans l’écran **Sélectionner les tableaux**, puis sélectionnez **Inclure tous les objets.**
6.  Sélectionnez **Ajouter**

Maintenant que nous avons le tableau Compte, nous allons ajouter le tableau de contacts.

7.  Dans la **Barre de commandes**, sélectionnez à nouveau le bouton **Ajouter existant****.**
8.  Dans le menu qui s’affiche, sélectionnez **Tableau.**
9.  Sélectionnez le tableau **Contact**, puis sélectionnez **Suivant.**
10.  Dans l’écran **Sélectionner les tableaux**, sélectionnez **Inclure tous les objets**
11.  Sélectionnez **Ajouter**

![Capture d’écran montrant les tableaux Compte et Contact dans la solution.](media/a53817e242fca7371765583d9e565c36.png)

Félicitations, vous avez réussi à créer une nouvelle solution à l’aide de Microsoft Power Platform. Nous continuerons à utiliser la solution pour y ajouter des composants supplémentaires.
