---
title: Documentation ALV
description: Présentation et utilisation des ALV en général.
---

# ALV Table
## Qu'est-ce ?
Une ALV est une fonctionnalité d'affichage sous forme de tableau proposant différentes fonctions : tri croissant / décroissant, filtre, ... L'ALV permet de consulter le contenu d'une table interne de façon optimisée (comparé à des `#!abap WRITE`).   

Les fonctions standards mises à disposition avec les ALV sont utilisées afin de pouvoir rapidement analyser les données, trier par type, filtrer par numéro de commande ou autre. Il est possible d'en créer manuellement.

## Créer une ALV
__Objectif:__ Pouvoir afficher une table interne nommée `lt_table`, on utilisera une ALV.   

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


Il est normal que rien ne soit affiché lors de la création d'une ALV. On utilisera la méthode `display( ).` :
```abap
lo_alv->display( ).
```

:octicons-alert-16: Attention de ne pas oublier l'espace entre les parenthèses !

### Types d'ALV

## Paramétrer son ALV

## Ajouter les fonctions

## Evénements

## Créer sa propre fonction
!!! warning "Prérequis" 
	Afin de pouvoir ajouter des fonctions personnalisées, il est nécessaire d'ajouter l'ALV dans un *container* via le *screen painter*. Sans ça, un *dump* sera lancé. 

## Affichage en couleur