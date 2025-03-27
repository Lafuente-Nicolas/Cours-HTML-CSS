# CSS 

## La structure du css

![Structure du css](structure-css.jpg)

Chaque déclaration CSS est composée d’une propriété et d’une valeur. La propriété définit ce qui va être stylisé, et la valeur spécifie comment.

Voici quelques propriétés courantes :
```css
    color : définit la couleur du texte.

    background-color : définit la couleur de fond.

    font-size : définit la taille du texte.
```
## Insérer le CSS dans le HTML

### Il est existe 4 manières:

1. __CSS en ligne (inline CSS)__ : 

Le CSS en ligne consiste à appliquer des styles directement dans l'élément HTML via l'attribut style. Cela permet de cibler un seul élément spécifique sur la page.

Quand l'utiliser ?

- Utile pour appliquer rapidement un style à un élément précis.

- Moins conseillé pour des projets à grande échelle car il peut rendre le code moins lisible et difficile à maintenir.

```CSS
<p style="color: red; font-size: 20px;">Ce texte est rouge et en taille 20px.</p>
```
Dans cet exemple, l'élément ```<p>``` aura une couleur rouge et une taille de police de 20px.

2. __CSS interne (internal CSS)__:

Le CSS interne consiste à inclure les styles directement dans le document HTML à l'intérieur de la balise ```<style>```, qui se trouve dans l'en-tête ```<head>``` du fichier HTML. Cette méthode est idéale si tu souhaites appliquer des styles à une seule page web.

Quand l'utiliser ?

- Lorsque tu veux appliquer des styles à une seule page HTML sans avoir à créer un fichier CSS externe.

- Convient pour des pages relativement simples où le code ne devient pas trop lourd.
```html css
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exemple CSS interne</title>
    <style>
        body {
            background-color: lightblue;
        }
        h1 {
            color: green;
        }
    </style>
</head>
<body>
    <h1>Bonjour le monde !</h1>
</body>
</html>
```
Ici, les styles définis dans la balise ```<style>``` s'appliquent à toute la page HTML :

- Le fond de la page sera bleu clair.

-  Le titre ```<h1>``` sera en vert.

