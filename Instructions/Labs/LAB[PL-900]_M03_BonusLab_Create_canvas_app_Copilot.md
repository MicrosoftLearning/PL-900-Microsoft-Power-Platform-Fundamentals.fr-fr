---
lab:
  title: 'Labo en bonus : Créer une application canevas en utilisant Copilot'
  module: 'Module 3: Get started with Power Apps'
---

# Labo en bonus : Créer une application canevas en utilisant Copilot

**Locataires WWL - Conditions d’utilisation** Si un locataire est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation. Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder. Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment. 

## Scénario

Bellows College est une organisation éducative disposant de plusieurs bâtiments sur le campus. Les visiteurs du campus sont actuellement enregistrés dans des journaux papier. Les informations ne sont pas saisies de manière cohérente et il n’y a aucun moyen de collecter ni d’analyser les données concernant les visites sur l’ensemble du campus.

L’administration du campus souhaite moderniser son système d’inscription des visiteurs où l’accès aux bâtiments est contrôlé par le personnel de sécurité et toutes les visites doivent être pré-enregistrées et enregistrées par leurs hôtes.

Dans ce labo, vous allez utiliser Copilot pour créer une application canevas pour enregistrer des visites. 

## Étapes de labo de haut niveau

Nous allons suivre le plan ci-dessous pour concevoir l’application canevas :

- Décrire l’application que vous voulez créer

- Utiliser Copilot pour modifier la structure des tables sous-jacentes

 ## Prérequis

- Participation au **Module 1 Labo 0 – Valider l’environnement de labo**

## Exercice 1 : Utilisez Copilot pour créer une application de visites d’une université.

**Objectif** : Dans cet exercice, vous allez créer une application canevas en vous connectant à une table Expense Reports (Rapports de dépenses).

### Tâche \#1 : Créer la structure initiale

1. Accédez à https://make.powerapps.com.

2. Vous devrez peut-être vous réauthentifier. Sélectionnez **Se connecter** et suivez les instructions si nécessaire.

3. Sélectionnez l’environnement **Dev One** en haut à droite, si ce n’est pas déjà fait.

4. Dans la zone **Décrire l’application que vous voulez créer**, entrez le texte suivant. Créer une application qui enregistre les visites sur un campus universitaire. 

5. Sélectionnez le bouton **Aller**.

Copilot va commencer à créer une structure de tables pour servir de base à votre application. 

> **IMPORTANT :** Lors de l’utilisation de l’IA générative, vous n’obtiendrez pas toujours exactement les mêmes résultats. Il est possible que votre table ne corresponde pas exactement à la table créée pour un autre étudiant. 

6. Dans la zone **Décrire ce qu’il faut changer**, entrez le texte : Ajouter deux colonnes, Heure d’entrée et Heure de sortie. Les deux doivent être des champs de date et d’heure.  

7. Sélectionnez l’icône **OK** ou appuyez sur **Entrée**. 

8. Faites défiler jusqu’à l’extrémité de la table et vérifiez que les colonnes **Heure d’entrée** et **Heure de sortie** ont été créées. 

Comme nous enregistrons les heures d’entrée et de sortie des visiteurs, nous n’avons plus besoin d’autres champs de date de visite. 

9. Recherchez le champ **Date de visite** (ou un champ équivalent) puis, dans la zone **Décrire ce qu’il faut changer**, entrez le texte Supprimer le champ Date de visite. 

10. Sélectionnez le bouton **Aller**. 

11. Supprimez les autres champs de date qui peuvent être présents, autres que **Heure d’entrée** et **Heure de sortie**. 

Initialement, un champ comme **Objectif** a été ajouté et mis en forme avec un type de données texte. Nous allons demander à Copilot de le transformer en menu déroulant (Choix). 

12. Dans la zone **Décrire ce qu’il faut changer**, entrez le texte suivant : Remplacer le champ Objectif par un menu de choix avec les options suivantes : Visite du campus, Salon de l’emploi, Rencontre avec un professeur, Conseils aux étudiants, Autres. 

13. Sélectionnez le bouton **Aller**. 

14. Comme nous voulons également capturer le numéro de bâtiment, dans la zone **Décrire ce qu’il faut changer**, entrez : Ajoutez une colonne Bâtiment. 

15. Sélectionnez le bouton **Aller**. 

16. Une fois que vous êtes satisfait de votre table, sélectionnez le bouton **Créer une application**. 

17. Si nécessaire, dans l’écran **Bienvenue dans Power Apps Studio**, sélectionnez **Ne plus me le montrer**, puis cliquez sur le bouton **Ignorer**. 

![](media/bonus-lab-copilot-01.png)

Félicitations, vous avez utilisé Copilot pour créer une application. 
