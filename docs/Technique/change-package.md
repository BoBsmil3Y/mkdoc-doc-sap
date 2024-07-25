---
title: Manipulation des packages
description: Description et manipulation des packages.
---

# Package
## Définition
Lorsqu'on sauvegarde un objet dans SAP (table, type, programme, ou autres), il faut préciser un dossier dans lequel l'attribuer. Ce dossier est nommé "package".

???+ info
	Un package spécial existe lorsqu'on ne veut pas transporter notre objet sur d'autre environnement : "$TMP". Il s'attribue automatiquement lorsqu'à l'enregistrement, on clique sur le bouton "Local".

## Changer le package d'une table

1. Aller en **SE11**
1. Cliquer sur "*Goto » Object Directory Entry*"
<center>
  <img src="/.img/package/packages-1.png" alt="Goto menu" style="width:30vw;"/>
</center>

1. Activer le mode édition
1. Changer le package pour celui voulu
1. Valider

## Changer le package d'un programme
1. Aller en SE38, ou SE80.
1. Afficher la liste des objets "Display Object list"
<center>
  <img src="/.img/package/package-report-1.png" alt="Object list button" style="width:65vw;"/>
</center>

1. Deux options sont possibles. 
Clique droit sur le nom du programme "Additional Functions » Change Package Assignment" ou "Additional Functions » Display Object Directory Entry" :
<center>
  <img src="/.img/package/package-report-2.png" alt="Menu to change package" style="width:35vw;"/>
</center>

1. Changer le package pour celui voulu
1. Valider