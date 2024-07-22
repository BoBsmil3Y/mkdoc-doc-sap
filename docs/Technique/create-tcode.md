---
title: Création d'un code transaction (tcode)
description: Création d'un tcode étape par étape
---

# TCODE
## Description
Les codes transactions sont les suites de caractères que l'on entre dans la zone de recherche de SAP. Elle renvoi vers l'écran de sélection d'un *REPORT*.   

???+ info

    Sans cela, un programme n'est qu'accessible que depuis les transactions d'édition (SE38, SE80).

## Création
1. Direction la transaction **SE93**
1. Entrer le nom de la transaction à créer, puis "Create"

<center>
  <img src="/.img/create-tcode/create-tcode-1.png" alt="enter tcode name" style="width:65vw;"/>
</center>

1. Entrer une description pour ce tcode, et sélectionner "Program and selection screen". Puis, valider. 

<center>
  <img src="/.img/create-tcode/create-tcode-2.png" alt="enter tcode description" style="width:65vw;"/>
</center>

1. Entrer le nom du programme, avec l'écran adéquat. Sélectionner tous les supports par défaut. Enfin, valider la création.

<center>
  <img src="/.img/create-tcode/create-tcode-3.png" alt="enter prog name" style="width:65vw;"/>
</center>

:octicons-link-16:{ title="Source" } [Source de la page](https://www.saphub.com/reports/how-to-create-a-tcode-for-an-abap-report-program/){:target="_blank"}