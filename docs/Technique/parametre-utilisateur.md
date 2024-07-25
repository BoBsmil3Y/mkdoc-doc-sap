---
title: Paramètres utilisateur
description: Fonctionnement, adaptation en ABAP, et modification fonctionnelle en SU3.
---

# Paramètre utilisateur
## Qu'est ce ?
Les paramètres utilisateurs sont des options propres à chaque utilisateur, qu'ils peuvent modifier. En SU3, on peut voir les différents paramètres de son compte. Pour en ajouter des nouveaux à la main, il faut que ces derniers soient définis dans SAP. On ne peut pas ajouter de paramètres spécifiques sans qu'ils ne soient répertoriés.

On peut voir la liste des paramètres définis en faisant un **F4** sur la colonne "*SET/GET Parameter ID*".
<center>
  <img src="/.img/parametre-utilisateur/param-1.png" alt="param list" style="width:20vw;"/>
</center>

???+ tip "En passant par les MF"
	En passant par les modules fonctions cités ci-dessous, il est possible de voir, et d'éditer des paramètres d'utilisateur en ABAP.


## Créer un paramètre
### Sur tout le système
Afin de pouvoir utiliser des paramètres spécifiques, il y a deux manières d'en créer :

- En modifiant la table TPARA (via la **SM30** évidemment),
- Ou, avec le module fonction : ```RS_PARAMETER_ADD```.

Cette création est *system-wide*, c'est à dire que chaque utilisateur peut maintenant paramétrer son compte en SU3 avec cette dernière.

### Par utilisateur 
L'on peut ajouter, supprimer et modifier des paramètres à l'utilisateur. Ces derniers non pas besoin d'être reconnu par SAP. Ils sont en quelques sortes "forcés" par le MF.

Ici, on indique notre paramètre `ZTEST_ADUPO` via une constante.

#### Récupérer les paramètres utilisateurs
```ABAP
CONSTANTS: cv_param_id TYPE usr05-parid VALUE 'ZTEST_ADUPO'.

DATA: lv_value TYPE usr05-parva,
      lv_subrc TYPE sy-subrc.

CALL FUNCTION 'RHP0_GET_USER_PARAMETER'
  EXPORTING
    parameter_id    = cv_param_id
  IMPORTING
    parameter_value = lv_value
    rc              = lv_subrc.

IF sy-subrc <> 0.
  MESSAGE 'Parameter not found' TYPE 'I'.
ENDIF.

MESSAGE |Parameter value: { lv_value }| TYPE 'S'.
```

#### Changer le paramètre d'un utilisateur
```ABAP 
CONSTANTS: cv_param_id TYPE usr05-parid VALUE 'ZTEST_ADUPO'.

DATA: lv_value TYPE usr05-parva VALUE 'TEST OUI'.

CALL FUNCTION 'RHP0_SET_USER_PARAMETER'
  EXPORTING
    parameter_id    = cv_param_id
    parameter_value = lv_value
  EXCEPTIONS
    does_not_exist  = 1
    OTHERS          = 2.
IF sy-subrc <> 0.
  MESSAGE 'Parameter failed to be updated' TYPE 'I'.
ENDIF.
```

## Tables en lien
| Nom | Utilité |
| --- | ------- |
| TPARA | Liste les paramètres définis dans SAP. |
| USR05 | Liste les paramètres par utilisateur. |