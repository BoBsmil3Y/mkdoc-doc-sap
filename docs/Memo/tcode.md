---
title: Liste des code transactions
description: Trop de transactions existent. Ici, on donne les principales !

hide:
  - navigation
  - toc
---

# TCODE
## Technique
| TCODE    | Description                          | Catégorie |
| ---------| ------------------------------------ | --------- |
| `SAT`    | Permet de réaliser une analyse de performance (utilisation de processeur et base de donneés) sur un programme avec une variante donnée. | Analyse |
| `SM12`   | Liste les locks posés sur des programmes par des développeurs en train d'éditer ces derniers. Possibilité de les supprimer à la main. | Analyse |
| `SM37`   | Permet de visualiser les programmes qui ont tourné en arrière plan (jobs). | Analyse |
| `ST05`    | Permet de réaliser une analyse de performance (SQL, Buffer, Enqueue, RFC, HTTP, APC, AMC) sur un programme. | Analyse |
| `ST12`   | Permet d'exécuter des analyses sur les programmes lancés par un utilisateur. Les fonctions, requêtes, ... afin d'obtenir par exemple des informations sur des optimisations possibles. | Analyse |
| `ST22`   | Permet de visualiser les dumps (crash de programme). | Analyse |
| `STAD`   | A peu près les mêmes fonctionnalités que la `ST12`. Permet en plus d'avoir une analyse sur une transaction particulière. | Analyse |
| `DB02`   | (SQL editor) Permet de réaliser des requêtes SQL natives sur les tables SAP. Transaction qui n'est pas souvent autorisé, et qui est très dangereuse. Aucun rollback possible. | Base de données |
| `SE16N`  | Permet d'afficher les structures des tables et leurs contenus. Des fonctions sont disponibles pour exclure des données ou réaliser des recherches par range. | Base de données |
| `DWDM`   | Template de code ABAP. Performance, objet, ALV, ... | Développement |
| `SAAB`   | Créer un point d'arrêt activable. | Développement |
| `SE11`   | Permet d'afficher et modifier des types, domaines et structures. Utile pour voir la composition de table en BDD, ou pour trouver des champs utiles comme des ranges d'un certain type. | Développement |
| `SE18`   | Permet d'afficher et modifier des BADI. Créer des Badi. | Développement |
| `SE24`   | Permet d'afficher et modifier des classes. | Développement |
| `SE37`   | Permet d'afficher et modifier des modules fonctions (MF). | Développement |
| `SE38`   | Permet d'afficher et modifier des reports. | Développement |
| `SE80`   | Permet d'afficher et modifier n'importe quel type de fichier de code (classe, module fonction, report, ...).  | Développement |
| `SE01`   | Modification et lecture des OT. | Ordre de transport |
| `SE10`   | Permet d'afficher et modifier les ordres de transport (OT). Les OT permettent d'envoyer un code d'une machine à une autre. Souvent pour passer le code en test, recette / qualité, puis production. | Ordre de transport |
| `SE93`   | Création d'un code de transaction pour un programme | Transaction |


## Fonctionnel
| TCODE    | Description                          | Catégorie |
| ---------| ------------------------------------ | --------- |
| `ME23N`   | Lire les informations de commandes. | Commande |
| `CG3Z`   | Transfert d'un fichier local à un serveur distant.  | Fichier |
| `CG3Y`   | Téléchargement d'un fichier serveur sur son PC.  | Fichier |
| `AL11`   | Voir la liste des fichiers sur le serveur.  | Fichier |
| `WE19`   | Copier des IDOCs. | IDOC |
| `WE20`   | Créer des Partner Profil pour les IDOCs. | IDOC |
| `BD87`   | Analyser des IDOCs. | IDOC |
| `SLG1`   | Visualiser les logs de programmes. | Log |
| `SM50`   | Ressource dispo sur la machine actuelle. Débug Prog en cours: ProgMode->Prog->debug | Ressource machine |
| `SM51`   | Ressource dispo sur toutes les machines. | Ressource machine |
| `SU01`   | Changer et unlock les sessions.  | Utilisateur |
| `SU53`   | Permet de voir les logs de refus d'autorisation. | Utilisateur |