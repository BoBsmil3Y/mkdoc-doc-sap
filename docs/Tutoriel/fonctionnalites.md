---
title: Documentation de documentation 
description: Cette page liste les fonctionnalités possibles pour créer une page de documentation.
---

# Documentation de documentation

## **Fonctionnement de la page**
Cette page vous montera les différentes fonctionnalités afin de créer des pages de documentations propres et agréable à lire.   
Chaque fonctionnalité de mise en page sera listée ci-dessous. Chaque élément sera suivi par le code permettant de le générer.

## **Entête de page**
Afin de changer le titre ou la description de la page, il est possible de l'indiquer en entête du fichier MD. 
```md
---
title: 
description: 
---
```

## **Tooltips**

Phrase avec un [tooltip](https://example.com "I'm a tooltip!") (avec lien).

```md
Phrase avec un [tooltip](https://example.com "I'm a tooltip!") (avec lien).

```
<br>

Phrase avec un [tooltip]("I'm a tooltip!") (sans lien). 
```md
[Tooltip sans lien]("I'm a tooltip!")
```   
<br>

:material-information-outline:{ title="Important information" } Une information qui devrait être importante.
```md
:material-information-outline:{ title="Important information" }
```
<br>

## **Encadrements**

### Encadrement simple :   

!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla.
```md
!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla.
```
<br>

### Titre    

!!! question "Est-ce que c'est bon pour vouuuuus ?"

    Une phrase qu'aurait prononcé Gandhi lors d'une conférence environnementale en Normandie.
```md
!!! question "Est-ce que c'est bon pour vouuuuus ?"

    Une phrase qu'aurait prononcé Gandhi lors d'une conférence environnementale en Normandie.
```
<br>

### Ouvert / fermé

ajoute la possibilité de réduire l'encadrement (en remplaçant les '!!!' par '???') :   
??? note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```md
??? note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.
```
<br>

l'ouvrir par défaut (en ajoutant '+'):    

???+ note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

```md
???+ note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.
```
<br>

### Placement

Il les possible de les placer sur les côtés grace aux mots-clés 'inline end' (droite) et 'inline' (gauche) :   
!!! info inline end "Lorem ipsum"

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.
```md
!!! info inline end "Lorem ipsum"

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.
```
<br>

!!! info inline "Lorem ipsum"

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.
```md
!!! info inline "Lorem ipsum"

    Lorem ipsum dolor sit amet, consectetur
    adipiscing elit. Nulla et euismod nulla.
    Curabitur feugiat, tortor non consequat
    finibus, justo purus auctor massa, nec
    semper lorem quam in massa.
```
<br>

### Liste des types d'encadré   
!!! note "note"
!!! abstract "abstract"
!!! info "info"
!!! tip "tip"
!!! success "success"
!!! question "question"
!!! warning "warning"
!!! failure "failure"
!!! danger "danger"
!!! bug "bug"
!!! example "example"
!!! quote "quote"


## **Annotations**

Des annotations sont intégrés dans la documentation. Elles peuvent être pratique pour expliquer des abbréviations fonctionnelles par exemple.   

Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be expressed in Markdown.

```md
Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be expressed in Markdown.

```
<br>

## **Boutons**
[Exemple](#){ .md-button }
```md
[Exemple](#){ .md-button }
```
<br>

[Superbe site](#){ .md-button .md-button--primary }
```md
[Superbe site](#){ .md-button .md-button--primary }
```
<br>

Il est possible d'y ajouter une icône :   
[Vroum l'avion :fontawesome-solid-paper-plane:](https://www.ouaismaisbon.ch/){ .md-button }
```md
[Vroum l'avion :fontawesome-solid-paper-plane:](#){ .md-button }
```
<br>


## **Bloc de code**
Afin d'avoir une documentation présentable, les blocs de code sont très importants. Aussi personnalisable que les autres éléments, voici la liste des possibilités.   

### Titre
Mettre un titre avec l'option 'title="bubble_sort.py"'' :

````md
``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````
``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

<br>

### Numéro de ligne
Ajouter le numéro de ligne avec l'option 'linenums="1"' :

````md
``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````
``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
<br>

### Highlight
Mettre en valeur une, plusieurs ou un range de ligne avec 'hl_lines="2 4"' :   
````md
``` py hl_lines="2 4"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````

``` py hl_lines="2 4"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
<br>

ou 'hl_lines="3-5"' :   
````md
``` py hl_lines="3-5"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````

``` py hl_lines="3-5"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
<br>

### Inline block
Il est possible de spécifier sur un simple bloc de code le langage pour ajouter la coloration, ici \`#!python range()\`:

- The `#!python range()` function is used to generate a sequence of numbers.


La bonne nouvelle étant que ABAP est détecté et coloré syntaxiquement !
```abap linenums="1"
LOOP AT lt_table INTO DATA(ls_struct).
    WRITE: ls_struct-test.
ENDLOOP.
```
<br>

## **Onglets**

Afin de pouvoir afficher plusieurs versions de texte, code ... ou même créer des exercices avec une correction "cachée" par défaut, des onglets sont disponibles.

=== "C"

    ``` c linenums="1"
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++ linenums="1"
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

````md
=== "C"

    ``` c linenums="1"
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++ linenums="1"
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
````
<br>

## **Tableau**

Il est possible de choisir la disposition du contenu dans un tableau. Cela se fait grâce à l'emplacement des ':' sur la deuxième ligne. La colonne 'Method' est aligné à gauche, 'Description' au milieu, et 'Commit' à droite.

| Method      | Description                          | Commit  |
| :---------- | :----------------------------------: | ------: |
| `GET`       | :material-check:     Fetch resource  | 2gs9h4  |
| `PUT`       | :material-check-all: Update resource | gl0n2w  |
| `DELETE`    | :material-close:     Delete resource | 7hxb4e  |

```md hl_lines="2" linenums="1"
| Method      | Description                          | Commit  |
| :---------- | :----------------------------------: | ------: |
| `GET`       | :material-check:     Fetch resource  | 2gs9h4  |
| `PUT`       | :material-check-all: Update resource | gl0n2w  |
| `DELETE`    | :material-close:     Delete resource | 7hxb4e  |
```

## Diagrammes
### Diagramme de flux
Diagramme sous forme de [Flowcharts](https://mermaid-js.github.io/mermaid/#/flowchart "documentation officielle") pour représenter des flux.
````md
``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```
````

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

<br>

### Diagramme de séquence
Les [Sequence diagrams](https://mermaid-js.github.io/mermaid/#/flowchart "documentation officielle") pour définir des scénarios.
```` markdown title="Sequence diagram"
``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```
````

``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```
<br>

### Diagramme de classe

Les [Class diagrams](https://mermaid-js.github.io/mermaid/#/classDiagram "documentation officielle") sont idéals pour créer des schémas de programme orienté objet (POO).

```` markdown title="Class diagram"
``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```
````

``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```
<br>

Pour plus de documentation sur le langage `mermaid`, la documentation officielle est [disponible ici](https://mermaid-js.github.io/mermaid/ "documentation officielle").