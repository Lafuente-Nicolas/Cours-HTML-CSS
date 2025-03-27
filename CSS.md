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

### Il existe 4 manières:

#### 1. __CSS en ligne (inline CSS)__ : 

Le CSS en ligne consiste à appliquer des styles directement dans l'élément HTML via l'attribut style. Cela permet de cibler un seul élément spécifique sur la page.

Quand l'utiliser ?

- Utile pour appliquer rapidement un style à un élément précis.

- Moins conseillé pour des projets à grande échelle car il peut rendre le code moins lisible et difficile à maintenir.

```CSS
<p style="color: red; font-size: 20px;">Ce texte est rouge et en taille 20px.</p>
```
Dans cet exemple, l'élément ```<p>``` aura une couleur rouge et une taille de police de 20px.

#### 2. __CSS interne (internal CSS)__:

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

#### 3. __CSS externe (external CSS)__ :


Le __CSS externe__ consiste à placer les styles dans un fichier séparé, puis à lier ce fichier CSS à la page HTML avec la balise ```<link>``` dans l'en-tête. Cette méthode est la plus courante, surtout pour des projets plus complexes, car elle permet de séparer la structure du contenu (HTML) et la présentation (CSS).

Quand l'utiliser ?

   - Pour des projets de grande envergure où tu veux appliquer les mêmes styles à plusieurs pages.

- Cela permet de garder le code HTML propre et facile à maintenir.

```css
<link rel="stylesheet" href="style.css">
```
#### 4. __CSS via @import dans une feuille de style__: 


La règle ```@import``` est utilisée dans un fichier CSS pour importer un autre fichier CSS. Cela permet de diviser les styles en plusieurs fichiers CSS et de les organiser de manière plus logique.

Quand l'utiliser ?

- Lorsque tu veux organiser ton CSS en plusieurs fichiers.

- Utile si tu veux importer des feuilles de style communes dans d'autres feuilles de style.

Exemple :

- Fichier CSS principal (main.css) : 
```css
@import url('style.css');

body {
    font-family: Arial, sans-serif;
}
```
- Fichier CSS importé (style.css):
```css
h1 {
    color: red;
}
```
Dans cet exemple, le fichier main.css importe le fichier style.css, et le style contenu dans ce dernier s'appliquera à la page web. Cependant, l'utilisation de @import peut affecter la performance du chargement de la page, car les fichiers sont chargés séquentiellement.


| Méthode              | Description | Cas d’utilisation |
|----------------------|-------------|-------------------|
| **Inline CSS**        | Styles ajoutés directement dans l'élément via l'attribut `style`. | Petits changements rapides à un seul élément. |
| **Internal CSS**      | Styles ajoutés dans la balise `<style>` dans l’en-tête de la page HTML. | Utilisé pour des pages simples ou un projet spécifique. |
| **External CSS**      | Styles définis dans un fichier séparé et reliés via `<link>`. | Idéal pour des projets à grande échelle et réutilisables. |
| **`@import`**         | Permet d'importer un fichier CSS dans un autre fichier CSS. | Organiser et modulariser les styles dans de nombreux fichiers. |

## classes, pseudo-classes, éléments, pseudo-éléments, IDs et le selecteur universel



### 1. Classes (.) :

Les classes permettent d'appliquer un même style à plusieurs éléments. Elles sont définies avec un . suivi du nom de la classe.

Exemple :
```
<p class="important">Texte important</p>
<p class="important">Autre texte important</p>
```
```css
.important {
    color: red;
    font-weight: bold;
}
```

✔ Utilité : Réutilisation du style sur plusieurs éléments.

❌ Inconvénient : Ne doit pas être utilisée pour des éléments uniques (préférer id dans ce cas).

### 2. IDs (#)

Les IDs sont uniques et doivent être utilisés pour un seul élément par page. Ils sont définis avec # suivi du nom de l'ID.
Exemple :
```html
<h1 id="main-title">Titre Principal</h1>
```
```css
#main-title {
    font-size: 24px;
    text-align: center;
}
```
✔ Utilité : Identifier un élément unique pour lui appliquer un style spécifique.

❌ Inconvénient : Non réutilisable et moins flexible que les classes.

⚠ Bonne pratique : Utiliser les classes (.) pour le styling et les IDs (#) uniquement pour des interactions avec JavaScript ou des ancres HTML.

### 3. Sélecteurs d'éléments (ou de balises)

Les sélecteurs d'éléments ciblent directement une balise HTML sans utiliser de classe ou d’ID.
Exemple :
```css
p {
    color: blue;
}
```

__Ce style s'applique à tous les ```<p>``` de la page.__

✔ Utilité : Rapide et simple à appliquer à tous les éléments d’un même type.

❌ Inconvénient : Pas assez spécifique si on veut styliser certains éléments seulement.

### 4. Pseudo-classes (:)

Les pseudo-classes permettent de sélectionner un état particulier d’un élément sans modifier le HTML.
Exemples courants :
```css
a:hover {
    color: red;
} 
```
```
    :hover → S'applique quand la souris survole un élément.

    :focus → Quand un champ de formulaire est sélectionné.

    :nth-child(odd) → Sélectionne les enfants impairs d'un parent.

    :first-child → Sélectionne le premier enfant d'un élément parent.
```

✔ Utilité : Permet d’ajouter des interactions et effets dynamiques.

❌ Inconvénient : Dépend du comportement de l’utilisateur