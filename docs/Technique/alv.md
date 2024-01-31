---
title: Documentation ALV
description: Présentation et utilisation des ALV en général.
---

# ALV Table
## Qu'est-ce ?
Une ALV est une fonctionnalité d'affichage sous forme de tableau proposant différentes fonctions : tri croissant / décroissant, filtre, ... L'ALV permet de consulter le contenu d'une table interne de façon optimisée (comparé à des `#!abap WRITE`).   

Les fonctions standards mises à disposition avec les ALV sont utilisées afin de pouvoir rapidement analyser les données, trier par type, filtrer par numéro de commande ou autre. Il est possible d'en créer manuellement.

## Créer une ALV
__Objectif:__ Pouvoir afficher une table interne nommée `lt_table`. On utilisera une ALV.   

La méthode statique `factory` de la classe `cl_salv_table` va permettre de créer une ALV. On sait que la méthode est statique grâce à son opérateur d'appel. On utilise `=>` au lieu de `->` pour une méthode classique.

=== "Objet local"
	```abap
	DATA lo_alv TYPE REF TO cl_salv_table.

	cl_salv_table=>factory( 
			IMPORTING r_salv_table = lo_alv
			CHANGING  t_table   = lt_table 
	).
	```

=== "Objet local défini sur le tas"
	```abap
	cl_salv_table=>factory( 
			IMPORTING r_salv_table = DATA(lo_alv)
			CHANGING  t_table   = lt_table 
	).
	```


On lui fourni la table interne à affichée, et notre objet de type `cl_salv_table`.   
La méthode va instancier notre objet lo_alv, et lui fournir comme données à afficher `lt_table`.


Il est normal que rien ne soit affiché lors de la création d'une ALV. On utilisera la méthode `display( )` pour afficher l'ALV :
```abap
lo_alv->display( ).
```

:octicons-alert-16: Attention de ne pas oublier l'espace entre les parenthèses !

## Types d'ALV
Il existe différent types d'ALV. On retrouve :

* l'ALV Tree
* l'ALV Table
* l'ALV Grid 

## Paramétrer son ALV
### Ajouter un titre
Pour ajouter un titre à son ALV, il est possible d'utiliser une fonction sur les paramètres.   
```ABAP
DATA lv_title TYPE LVC_TITLE.

lo_alv->get_display_settings( )->set_list_header( lv_title ).
```

### Sélection
Il existe plusieurs modes de sélection sur une ALV. 

Liste des modes :

* `SINGLE` -> 
* `MULTIPLE` -> 
* `CELL` -> 
* `ROW_COLUMN` -> 
* `NONE` -> Il sera impossible de sélectionner des célulles d'ALV.

```ABAP
lo_alv->get_selections( )->set_selection_mode( value = if_salv_c_selection_mode=>cell ).
```

### Adapter la taille des cellules
Il est possible d'adapter la taille des cellules automatiquement selon la taille des données qu'elles contiennent. Plus la donnée sera longue, plus la cellule le sera. 
```ABAP
lo_alv->get_columns( )->set_optimize( abap_true ).
```

### Ajouter les fonctions
Pour activer les fonctions fournies par les ALV, il faut l'activer avec la méthode suivante :
```ABAP
lo_alv->get_functions( )->set_all( abap_true ).
```

Cela comprend les fonctions de tris, de recherche, de filtre, etc.

### Evénements

## Créer sa propre fonction
!!! warning "Prérequis" 
	Afin de pouvoir ajouter des fonctions personnalisées, il est nécessaire d'ajouter l'ALV dans un *container* via le *screen painter*. Sans ça, un *dump* sera lancé.

Pour ajouter l'ALV dans un `container`, il faut le préciser dans la méthode `cl_salv_table=>factory()`.
```ABAP
DATA:
	lv_container_display_name TYPE STRING,
	lv_title TYPE LVC_TITLE,
	lv_container TYPE CL_GUI_CUSTOM_CONTAINER.

cl_salv_table=>factory(
        EXPORTING
          container_name = lv_container_display_name
          r_container = lo_container
        IMPORTING
          r_salv_table   = lo_alv
        CHANGING
          t_table        = lt_alv_data " itab de données quelconque
      ).
```

//TODO

## Affichage en couleur