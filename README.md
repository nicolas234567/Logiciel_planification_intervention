# Logiciel de gestion des intervention des techniciens sur les machines

## A quoi sert ce logiciel

Ce logiciel permet une gestion claire des interventions (dates, prix, clients et produit concerné) leur création, historique et planification des futures interventions.
La modification, ajout ou supression de clients et produits.
Et une gestion des comptes des techniciens.

## Installation & lancement

- Installer visual studio 2022
- Installer SQL Maganer Server Studio (SMSS)
- Copier le contenu de fixit.sql et exécuté une requête dans SMSS pour générer la base de données
- démarrer la base de données
- Ouvrir WindowsApp.sln dans visual studio 
- Exécuter WindowApp.sln

## Stack technique
- **C#** Composant de visual studio plus fonctionnalité coder en C#
- **SQL** Pour la base de données et les requêtes 
- **SHA-256** Hashage des mot de lors de l'inscription et déhashage lors de la connexion 

## Structure des fichiers

```
-WindowsApp.sln
-Fixit.sql
```
## Structure de l'application

```
login/
|- Page d'acceuil qui permet d'ajouter une internvention/
   |- Menu Gestion intervention/
       - Client (modifier ajouter des clients)
       - Produit (modifier ou ajouter des produits)
       - Historique (voir les interventions passé)
    |- Menu Gestion des comptes
       - Création d'un compte (créer un compte)
       - Changer mot de passe (permet de changer le mot de passe en renseignant le nom d'utilisateur et l'ancien mdp)
       - Bannir un utilisateur (supprimer un utilisateur de la base de données pour enlever l'accès a l'application)
```

## Controle automatique 

- Création de date préventive d'intervention selon la durée de cie moyenne d'un composant en utilisant la date depuis la dernière intervention dessus
- Refus de créer une intervention a une date future

## Gestion des accès 

- Page de login forcer pour accéder a l'application ou toute tentative d'évitement cause la fermeture du programme
- Compte administrateur seul l'administrateur a accés au menu créer un compte et bannir un utilisateur sinon inactif et grisé

