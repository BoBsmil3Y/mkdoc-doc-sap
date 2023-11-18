---
title: Documentation OO
description: Développer en OO sur ABAP.
---

# Programmation OO sur ABAP
## Pourquoi s'embêter ?
Pour vous convaincre d'utiliser l'objet, voici quelques points à retenir :
- Permet de réduire le code duppliqué grace au polymorphisme.
- Même s'ils peuvent paraitre chiants, les tests unitaires sont très utile pour confirmer le bon fonctionnement de vos algorithmes. L'objet simplifie ces tests.
- Optimisation de code en passant par des références plut6ot que par valeur.
- Les classes sont des bons conteneurs pour les données, afin de ne changer qu'une pqrtie d'entre elles à chaque méthode (e.g: archiver tous les idocs d'un même type, là ou un idoc sera représenté par un objet).
- Grâce aux polymorphisme, il sera aussi possible d'imposer vos structures pour des méthodes. N'autoriser qu'une interface, ou qu'une classe abstraite par exemple.
- Pouvoir récupérer les variables, types, constantes et méthodes d'autres classes facilement.
- Créer des classes statiques permet d'avoir des "librairies" de code utilisable facilement, en ayant une confiance quant au résultat de cette méthode.

## Points communs avec le monde extérieur
ABAP OO n'est pas très différent du fonctionnement dans d'autres langages. On retrouve, comme à notre habitudes en tant que d2veloppeur sur SAP, une écriture et des normes bizarres.

On pourra créer des interfaces :

=== "Definition"
    Définir les attributs, signatures de méthodes et événements.
    ```ABAP
    INTERFACE <if_name>.
        <attributes>.
        <methods>.
        <events>.
    ENDINTERFACE.
    ```
=== "Implementing it"
    Déclarer l'interface, puis implémenter les méthodes de celle-ci.
    ```ABAP
    INTERFACE <if_name>.
    ...
    
    METHOD <if_name>~<method_name>.
        ...
    ENDMETHOD.
    ```

!!! info "Caractère spécial"
    On utilisera le caractère tilde `~` pour informer le compilateur que nous implémentons la méthode d'une interface.