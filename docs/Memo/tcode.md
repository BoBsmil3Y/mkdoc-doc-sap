---
title: Liste des code transactions
description: Trop de transactions existent. Ici, on donne les principales !

hide:
  - navigation
  - toc
---

# TCODE
## Technique
| TCODE      | Description                          | Catégorie |
| ----------- | ------------------------------------ | ---- |
| `SE80`       | Permet d'afficher et modifier n'importe quel type de fichier de code (classe, module fonction (MF), report, ...).  | Développement |
| `SE38`       | Permet d'afficher et modifier des reports. | Développement |
| `SE37`    | Permet d'afficher et modifier des MF. | Développement |
| `SE24`    | Permet d'afficher et modifier des classes. | Développement |
| `SE11`    | Permet d'afficher et modifier des types, domaines et structures. Utile pour voir la composition de table en BDD, ou pour trouver des champs utiles comme des ranges d'un certain type. | Développement |
| `SE18`    | Permet d'afficher et modifier des BADI. | Développement |
| `SE16N`    | Permet d'afficher les structures des tables et leurs contenus. Des fonctions sont disponibles pour exclure des données ou réaliser des recherches par range. | Base de données |
| `SE10`    | Permet d'afficher et modifier les ordres de transport (OT). Les OT permettent d'envoyer un code d'une machine à une autre. Souvent pour passer le code en test, recette / qualité, puis production. | Ordre de transport |
| `DB02` (SQL editor)    | Permet de réaliser des requêtes SQL natives sur les tables SAP. Transaction qui n'est pas souvent autorisé, et qui est très dangereuse. Aucun rollback possible. | Base de données |
| `ST22`    | Permet de visualiser les dumps (crash de programme). | Analyse |
| `ST12`    | Permet d'exécuter des analyses sur les programmes lancés par un utilisateur. Les fonctions, requêtes, ... afin d'obtenir par exemple des informations sur des optimisations possibles. | Analyse |
| `STAD`    | A peu près les mêmes fonctionnalités que la `ST12`. Permet en plus d'avoir une analyse sur une transaction particulière. | Analyse |
| `SAT`    | Permet de réaliser une analyse de performance (utilisation de processeur et base de donneés sur un programme avec une variante donnée. | Analyse |
| `SM37`    | Permet de visualiser les programmes qui ont tourné en arrière plan (jobs). | Analyse |

## Fonctionnel
| TCODE      | Description                          | Catégorie |
| ----------- | ------------------------------------ | ---- |
| `CG3Z`       | Transfert d'un fichier local à un serveur distant.  | Fichier |
| `CG3Y`       | Téléchargement d'un fichier serveur sur son PC.  | Fichier |
| `AL11`       | Voir la liste des fichiers sur le serveur.  | Fichier |