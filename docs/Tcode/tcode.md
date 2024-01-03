---
title: Liste des code transactions
description: Trop de transactions existent. Ici, on donne les principales !
---

# TCODE

| TCODE      | Description                          | Catégorie |
| ----------- | ------------------------------------ | ---- |
| `SE80`       | Permet d'afficher et modifier n'importe quel type de fichier de code (classe, module fonction (MF), report, ...).  | Technique |
| `SE38`       | Permet d'afficher et modifier des reports. | Technique |
| `SE37`    | Permet d'afficher et modifier des MF. | Technique |
| `SE24`    | Permet d'afficher et modifier des classes. | Technique |
| `SE11`    | Permet d'afficher et modifier des types, domaines et structures. Utile pour voir la composition de table en BDD, ou pour trouver des champs utiles comme des ranges d'un certain type. | Technique |
| `SE16N`    | Permet d'afficher les structures des tables et leurs contenus. Des fonctions sont disponibles pour exclure des données ou réaliser des recherches par range. | Technique |
| `SE10`    | Permet d'afficher et modifier les ordres de transport (OT). Les OT permettent d'envoyer un code d'une machine à une autre. Souvent pour passer le code en test, recette / qualité, puis production. | Technique |
| `DB02` (SQL editor)    | Permet de réaliser des requêtes SQL natives sur les tables SAP. Transaction qui n'est pas souvent autorisé, et qui est très dangereuse. Aucun rollback possible. | Technique |
| `ST22`    | Permet de visualiser les dumps (crash de programme). | Technique |
| `ST12`    | Permet d'exécuter des analyses sur les programmes lancés par un utilisateur. Les fonctions, requêtes, ... afin d'obtenir par exemple des informations sur des optimisations possibles. | Technique |