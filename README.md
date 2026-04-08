# FixIT

Application de bureau Windows pour la gestion des interventions informatiques. Developpee en C# avec Windows Forms et SQL Server Express.

## Fonctionnalites

- **Authentification** : connexion securisee avec mot de passe hache en SHA-256
- **Gestion des interventions** : saisie, validation et enregistrement des interventions sur le materiel
- **Historique** : consultation des interventions sur une periode donnee
- **Gestion du referentiel** : produits, categories, clients
- **Comptes utilisateurs** : creation de comptes, changement de mot de passe, bannissement (reserve au compte `root`)

## Prerequis

- Windows 10 / 11
- .NET Framework 4.8
- SQL Server Express 2019 ou superieur (instance `.\SQLEXPRESS`)
- Visual Studio 2019 ou superieur

## Installation

1. Cloner le depot.
2. Importer le script `Fixit.sql` dans SQL Server Management Studio pour creer et alimenter la base de donnees.
3. Ouvrir `WindowsFormsAppFixIT.sln` dans Visual Studio.
4. Compiler et executer le projet.

## Configuration

La chaine de connexion est definie directement dans les fichiers source :

```
Server=.\SQLEXPRESS;Database=Fixit;Trusted_Connection=True;
```

Modifier cette valeur dans les formulaires concernes si l'instance SQL Server est differente.

## Structure du projet

```
WindowsFormsAppFixIT/
├── Form1.cs                    # Fenetre principale (saisie d'intervention)
├── FormLogin.cs                # Authentification
├── FormHistorique.cs           # Historique des interventions
├── FormProduit.cs              # Gestion des produits
├── FormCategorie.cs            # Gestion des categories
├── FormClient.cs               # Gestion des clients
├── FormCreationCompte.cs       # Creation de compte utilisateur
├── FormChangerMDP.cs           # Changement de mot de passe
├── FormBannirUtilisateur.cs    # Bannissement d'utilisateur
├── ClassItem.cs                # Classe utilitaire pour les listes
└── Fixit.sql                   # Script de creation de la base de donnees
```

## Compte par defaut

| Utilisateur | Role          |
|-------------|---------------|
| `root`      | Administrateur |

Le compte `root` dispose des droits de gestion des utilisateurs (creation et bannissement).
