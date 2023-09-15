# Documentation de documentation

## Fonctionnement de la page
Cette page est utile afin de pouvoir créer des pages de documentations propres et agréable à lire.   
Chaque fonctionnalité de mise en page sera listée ci-dessous. On retrouve le rendu, puis à la suite, le code permettant de réaliser celui-ci.

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

!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla.
```md
!!! note

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla.
```
<br>
  
!!! question "Est-ce que c'est bon pour vouuuuus ?"

    Une phrase qu'aurait prononcé Gandhi lors d'une conférence environnementale en Normandie.
```md
!!! question "Est-ce que c'est bon pour vouuuuus ?"

    Une phrase qu'aurait prononcé Gandhi lors d'une conférence environnementale en Normandie.
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