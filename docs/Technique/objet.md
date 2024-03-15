---
title: Documentation OO
description: Développer en OO sur ABAP.
---

# Programmation OO sur ABAP
## Pourquoi s'embêter ?
Pour vous convaincre d'utiliser l'objet, voici quelques points à retenir :

- Permet de réduire le code duppliqué grace au polymorphisme ;
- Même s'ils peuvent paraitre chiants, les tests unitaires sont très utile pour confirmer le bon fonctionnement de vos algorithmes. L'objet simplifie ces tests ;
- Optimisation de code en passant par des références plutôt que par valeur ;
- Les classes sont des bons conteneurs pour les données, afin de ne changer qu'une pqrtie d'entre elles à chaque méthode (e.g: archiver tous les idocs d'un même type, là ou un idoc sera représenté par un objet) ;
- Grâce aux polymorphisme, il sera aussi possible d'imposer vos structures pour des méthodes. N'autoriser qu'une interface, ou qu'une classe abstraite par exemple ;
- Pouvoir récupérer les variables, types, constantes et méthodes d'autres classes facilement ;
- Créer des classes statiques permet d'avoir des "librairies" de code utilisable facilement, en ayant une confiance quant au résultat de cette méthode.

## Points communs avec le monde extérieur
ABAP OO n'est pas très différent que d'autres langages. On retrouve juste, comme à notre habitudes en tant que développeur sur SAP, une implémentation et des normes bizarres.

## Classe

En `SE24`, vous pouvez créer des classes, et interfaces. En utilisant le "Form Based Class Builder", il est possible d'indiquer sans trop d'effort les interfaces à implémenter, les `Friends`, les attributs ...   
En passant en édition _Source Code-Based_, on pourra définir la base d'une classe comme ceci :   

### Création
=== "Classe basique"
    ```ABAP
    CLASS zcl_example DEFINITION PUBLIC FINAL CREATE PUBLIC .

      PUBLIC SECTION.
      PRIVATE SECTION.
      PROTECTED SECTION.

    ENDCLASS.


    CLASS zcl_example IMPLEMENTATION.

    ENDCLASS.
    ```
=== "Classe avec données"
    ```ABAP
    CLASS zcl_example DEFINITION PUBLIC FINAL CREATE PUBLIC .

      PUBLIC SECTION.
        INTERFACES zif_interface_example.

        METHODS:
          constructor IMPORTING
                        iv_container_display_name TYPE string OPTIONAL.

      PRIVATE SECTION.
        TYPES: BEGIN OF ty_useful_type,
                    count TYPE i,
                    matnr TYPE matnr,
               END OF ty_desadv_ecc.

        CONSTANTS:
          gc_zero_value TYPE i VALUE 0.

        DATA:
          mv_example_char TYPE char.

    ENDCLASS.


    CLASS zcl_example IMPLEMENTATION.
        METHOD constructor.
            mv_exemple_char = 'A'.
        ENDMETHOD.
    ENDCLASS.
    ```

Même si nous sommes sur SAP, il faut respecter les principes du paradigme de la Programmation Orientée Objet. C'est à dire :

- Les variables doivent être privées sauf exceptions,
- Elles doivent notamment être instanciées via le constructeur de la classe,
- Une classe doit avoir un but précis, 
- ...

### Nomenclature
Voici quelques nomenclatures permettant d'avoir un code avec des repères universels :

| Nomenclature fichier | Description |
|----------------------|-------------|
| `ZCL_*` | Nommage d'une classe |
| `ZIF_*` | Nommage d'une interface |

| Nomenclature des variables de classe | Description |
|--------------------------------------|-------------|
| `MV_*` | Variable dîtes "membre" de la classe. Ce sont les attributs liés à une classe, ou plus précisément à une instance de classe (un objet donc). |
| `MC_*` | Variation pour les constantes. |
| `MR_*` | Variation pour les ranges. |
| `MO_*` | Variation pour les objets. |
| `MS_*` | Variation pour les structures. |
| `MT_*` | Variation pour les tables. |

### Méthode
On n'utilisera pas de `FORM` (ou subroutines) ici, mais des méthodes. Elles permettent plus de souplesse que les `FORM`. On y retrouve comme "classe" de paramètres :

| Type | Description |
|------|-------------|
| `CHANGING`   | Indique que l'on va modifier la variable dans la méthode. |
| `EXCEPTIONS` | On va pouvoir déclarer des exceptions (créées localement, appelées `non-class-based exception`) que la méthode peut lever. C'est grossièrement une modification du `sy-subrc`. On utilisera le mot clé `RAISE <excp_name>`. |
| `EXPORTING`  | Indique qu'on va renvoyer ces paramètres en sortie de méthode. |
| `IMPORTING`  | Indique qu'on ne modifie pas les valeurs de ces paramètres dans la méthode. |
| `RAISING`    | Déclaration des classes d'exceptions que la méthode peut lever. Elles sont déclarées globalement sur le système, standard ou spécifique. On utilisera le mot clé `RAISE EXCEPTION TYPE <class_excp>`. |
| `RETURNING VALUE` | Indique le type de variable qui sera retourné par le programme. |

??? tip "Lever une exception créée dans la méthode"
    Raising a non-class-based exception in a method.
    ```ABAP
    CLASS cls DEFINITION.
      PUBLIC SECTION.
        CLASS-METHODS meth EXCEPTIONS exc.
    ENDCLASS.

    CLASS cls IMPLEMENTATION.
      METHOD meth.
        ...
        RAISE exc.
        ...
      ENDMETHOD.
    ENDCLASS.

    START-OF-SELECTION.
      cls=>meth( EXCEPTIONS exc = 4 ).
      CASE sy-subrc.
        WHEN 4.
          cl_demo_output=>display( 'Exception' ).
        WHEN OTHERS.
          ...
      ENDCASE. 
    ```

    [Documentation](https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-us/abapraise_exception.htm){ .md-button }

??? tip "Lever une exception venant d'une classe d'exception"
    Raising an exception cx_demo in a method.
    ```ABAP
    CLASS cx_demo DEFINITION INHERITING FROM cx_static_check.
    ENDCLASS.

    CLASS cls DEFINITION.
      PUBLIC SECTION.
        CLASS-METHODS meth RAISING cx_demo.
    ENDCLASS.

    CLASS cls IMPLEMENTATION.
      METHOD meth.
        ...
        RAISE EXCEPTION TYPE cx_demo.
        ...
      ENDMETHOD.
    ENDCLASS.

    START-OF-SELECTION.
      TRY.
          cls=>meth( ).
        CATCH cx_demo.
          cl_demo_output=>display( 'Catching exception' ).
      ENDTRY. 
    ```
    [Documentation](https://help.sap.com/doc/abapdocu_751_index_htm/7.51/en-us/abapraise_exception_class.htm){ .md-button }


## Interface
Les interfaces servent à définir un "patron" a respecter pour les classes qui l'implémenteront. Il est uniquement possible de définir des signatures de méthodes dans ces dernières. Cela impose donc les paramètres, et types.

On pourra créer des interfaces :

=== "Definition"
    Définir les attributs, signatures de méthodes et événements.
    ```ABAP
    INTERFACE <if_name> PUBLIC.
        <methods>.
        <events>.
    ENDINTERFACE.
    ```
=== "Implementing it"
    Déclarer l'interface, puis implémenter les méthodes de celle-ci.
    ```ABAP
    CLASS zcl_example DEFINITION.
        PUBLIC SECTION.
            INTERFACE <if_name>.
        ...
    ENDCLASS.
    
    CLASS zcl_example IMPLEMENTATION.
        METHOD <if_name>~<method_name>.
            ...
        ENDMETHOD.
    ENDCLASS.
    ```

!!! info "Caractère spécial"
    On utilisera le caractère tilde `~` pour informer le compilateur que nous implémentons la méthode d'une interface.

