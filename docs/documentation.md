# Documentation de documentation

## Fonctionnement de la page
Cette page vous montera les différentes fonctionnalités afin de créer des pages de documentations propres et agréable à lire.   
Chaque fonctionnalité de mise en page sera listée ci-dessous. Chaque élément sera suivi par le code permettant de le générer.

## Tooltips

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

## Encadrements

Encadrement simple :   

!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla.
```md
!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla.
```
<br>

avec un titre :    

!!! question "Est-ce que c'est bon pour vouuuuus ?"

    Une phrase qu'aurait prononcé Gandhi lors d'une conférence environnementale en Normandie.
```md
!!! question "Est-ce que c'est bon pour vouuuuus ?"

    Une phrase qu'aurait prononcé Gandhi lors d'une conférence environnementale en Normandie.
```
<br>

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


```md
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



```md
```
<br>
