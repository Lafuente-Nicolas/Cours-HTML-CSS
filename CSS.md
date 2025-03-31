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

### 5. Pseudo-éléments (::)

Les pseudo-éléments permettent de styliser une partie spécifique d'un élément.

Exemples :

```css
p::first-letter {
    font-size: 2em;
    color: red;
}
```
Cela stylise uniquement la première lettre de chaque <p>.

```css
p::before {
    content: "🔥 ";
}
```
Cela ajoute un emoji 🔥 avant chaque <p>.

✔ Utilité : Ajouter des styles avancés sans modifier le HTML.

❌ Inconvénient : Moins compatible sur les anciens navigateurs.

### 6. Le Sélecteur Universel (*)

Le sélecteur universel (*) cible tous les éléments d'une page.
Exemple :
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
Cela permet souvent de réinitialiser les styles par défaut.

✔ Utilité : Utile pour des reset CSS globaux.

❌ Inconvénient : Peut affecter tous les éléments, donc doit être utilisé avec précaution.

| **Type de Sélecteur**  | **Syntaxe** | **Description** | **Exemple** |
|----------------------|-------------|-----------------|-------------|
| **Classe** | `.nom-classe` | Réutilisable, appliqué à plusieurs éléments | `.important { color: red; }` |
| **ID** | `#nom-id` | Unique, appliqué à un seul élément | `#main-title { text-align: center; }` |
| **Élément** | `balise` | Appliqué à toutes les occurrences de l'élément | `p { font-size: 16px; }` |
| **Pseudo-classe** | `:nom` | Sélectionne un état spécifique d'un élément | `a:hover { color: blue; }` |
| **Pseudo-élément** | `::nom` | Cible une partie spécifique d'un élément | `p::first-letter { color: red; }` |
| **Sélecteur Universel** | `*` | Sélectionne **tous** les éléments | `* { margin: 0; }` |

## Le box model

![Shéma du box model](https://www.devenir-webmaster.com/tuto/html-css/le-modele-de-boite/img/le-modele-de-boite.gif)

- __Le Contenu (content)__ : L’intérieur de la boîte où le texte ou les images apparaissent.

- __Le Remplissage (padding)__ : L’espace entre le contenu et la bordure.

- __La Bordure (border)__ : L’encadrement autour du contenu et du padding.

- __La Marge (margin)__ : L’espace extérieur qui sépare l’élément des autres éléments.

le Box Model est essentiel pour :

- Maîtriser l’espace entre les éléments.

- Aligner correctement les éléments sur une page.

- Éviter les bugs d’affichage causés par des tailles qui dépassent.

En résumé : 

✅ Tous les éléments HTML sont des boîtes.

✅ Ces boîtes suivent une structure (content, padding, border, margin).

✅ box-sizing: border-box; permet de mieux gérer la taille des éléments.

## Le positionnement en CSS

Le positionnement en CSS permet de contrôler l’endroit où un élément apparaît sur la page. 

__Il existe 5 types de positionnement principaux:__

### 1. Position static (par défaut):

- Comportement : Les éléments apparaissent dans l’ordre du flux normal du document.

-  Quand l’utiliser ? : C’est le comportement par défaut, pas besoin de le spécifier.
```css
.box {
    position: static; /* Par défaut */
}
```
 Effet : L’élément reste empilé normalement les uns en dessous des autres.

 ### 2. Position relative

- Comportement : L’élément reste dans le flux normal mais peut être déplacé avec top, bottom, left, right.
-  Quand l’utiliser ? : Pour décaler légèrement un élément tout en conservant son espace d’origine.
```css
.box {
    position: relative;
    top: 20px; /* Descend de 20px */
    left: 10px; /* Se décale vers la droite de 10px */
}
```
Effet : L’élément est décalé, mais son espace d’origine reste vide.
### 3.Position absolute

- Comportement : L’élément quitte le flux normal et est positionné par rapport à son ancêtre position: relative; le plus proche (sinon, c'est le ```<html>``` qui sert de référence).

- Quand l’utiliser ? : Pour placer précisément un élément sans affecter les autres.
```css
.container {
    position: relative; /* Référence */
}

.box {
    position: absolute;
    top: 20px; /* 20px du haut du .container */
    right: 50px; /* 50px de la droite du .container */
}
```
 Effet : L’élément se place exactement par rapport à .container, sans impacter les autres.

 ### 4.Position fixed

- Comportement : L’élément est fixé par rapport à la fenêtre du navigateur.

- Quand l’utiliser ? : Pour créer des menus fixes ou des boutons "Retour en haut".
```css
.box {
    position: fixed;
    bottom: 10px;
    right: 10px;
}
```

 Effet : L’élément reste visible même en scrollant.

### 5. Position sticky

- Comportement : L’élément est comme relative au départ, puis devient fixed lorsqu’on scroll.
- Quand l’utiliser ? : Pour un menu collant qui reste visible quand on fait défiler.

```css
.box {
    position: sticky;
    top: 0; /* Reste collé en haut */
    background-color: yellow;
}
```
Effet : L’élément reste en haut de la page lorsqu'on scrolle.

| Position   | Effet |
|------------|----------------------------------------------------------------|
| **static**  | Position normale (par défaut), l'élément suit le flux du document. |
| **relative** | L'élément peut être déplacé par rapport à sa position normale. |
| **absolute** | L'élément est retiré du flux normal et se positionne par rapport à son premier parent avec `position: relative;`. |
| **fixed**    | L'élément est fixé par rapport à la fenêtre du navigateur et ne bouge pas en scrollant. |
| **sticky**   | L'élément agit comme `relative` au départ, puis devient `fixed` en scrollant. |

## La spécificité en css

La spécificité CSS permet de savoir quelle règle CSS s'applique lorsqu'il y a des conflits entre plusieurs styles. C’est un système de points qui donne plus d’importance à certaines règles qu’à d’autres.

### Règles de base de la spécificité

- L’ordre d’application → Si deux règles ont la même spécificité, la dernière écrite (plus bas dans le CSS) est appliquée.

- Les sélecteurs les plus précis sont prioritaires sur les sélecteurs plus généraux.

-  !important > Inline styles > ID > Classe / Attributs / Pseudo-classes > Éléments

### Pourquoi cet ordre ?

- Plus un sélecteur est précis et ciblé, plus il a de poids.
- Un ID est unique, une classe est réutilisable, un élément est générique.
- Le style en ligne est appliqué directement, donc il est prioritaire.
- Le sélecteur universel (*) est trop large, donc il n'a aucun poids.

### L’ordre exact de spécificité CSS est :

- !important (priorité absolue, mais ne fait pas partie du calcul de la spécificité).

- Style en ligne (style="") → 1000 points

- ID (#monID) → 100 points

- Classes, attributs et pseudo-classes (.maClasse, [type="text"], :hover) → 10 points

- Éléments et pseudo-éléments (div, p, h1, ::before) → 1 point

- Sélecteur universel (*) → 0 point (aucune spécificité)


## Manipuler les polices 


| Propriété      | Description                                      | Exemple                                      |
|----------------|--------------------------------------------------|----------------------------------------------|
| `font-family`  | Définit la police à utiliser.                    | `font-family: "Arial", sans-serif;`          |
| `font-size`    | Définit la taille de la police.                  | `font-size: 16px;`                           |
| `font-weight`  | Définit l'épaisseur du texte.                    | `font-weight: bold;`                         |
| `font-style`   | Définit le style de la police (normal, italique).| `font-style: italic;`                        |
| `line-height`  | Définit l'espacement entre les lignes de texte.  | `line-height: 1.5;`                          |
| `letter-spacing`| Définit l'espacement entre les lettres.         | `letter-spacing: 2px;`                       |
| `@font-face`   | Permet d'importer une police externe.            | `@font-face { font-family: 'MaPolice'; src: url('chemin'); }` |
| `font-variant` | Permet d'utiliser des variantes typographiques.  | `font-variant: small-caps;`                  |

## Google fonts

Google Fonts est un service qui permet d'intégrer facilement des polices web gratuites et ouvertes dans des projets.

## Intégrer des polices extérieurs 

### importer une police depuis Google Fonts
C'est la méthode la plus facile. Elle consiste à importer une police __depuis Google Fonts__ en ajoutant un lien dans le ```<head>``` du fichier HTML.

Étapes :

- Aller sur Google Fonts.

- Choisir une police et copier le lien fourni.

- L’ajouter dans le ```<head>``` du fichier HTML.

### @font-face pour importer une police personnalisée

Si vous avez un fichier de __police (.woff, .woff2, .ttf)__, vous pouvez l’intégrer avec __@font-face__.

Étapes :

- Télécharger la police et placer les fichiers dans votre projet.

- Déclarer la police avec @font-face en CSS.

- Utiliser la police dans les styles.

  Exemple :

Si la police est MaPolice.woff2 et est stockée dans un dossier fonts/ :
```css
@font-face {
  font-family: 'MaPolice';
  src: url('fonts/MaPolice.woff2') format('woff2'),
       url('fonts/MaPolice.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}

body {
  font-family: 'MaPolice', sans-serif;
}
```

 Avantages : Fonctionne sans dépendre d'un service externe.

 Inconvénient : Augmente le poids du site si la police est trop lourde.

 ### Importer une police via un CDN

 Certaines polices sont hébergées sur des CDNs (Content Delivery Network), ce qui évite de stocker le fichier localement.

 Exemple avec Fontsource (équivalent à Google Fonts en local) :

Ajoutez cette ligne dans votre CSS :
```css
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;700&display=swap');
```
## la notion de cascade en CSS

En CSS, la cascade est un concept fondamental qui détermine quelle règle CSS s'applique lorsqu'il y a plusieurs déclarations qui ciblent le même élément. La cascade suit un ensemble de règles de priorité qui permettent de trancher en cas de conflit.

| Principe                     | Description                                                                 | Exemple                                       |
|------------------------------|-----------------------------------------------------------------------------|-----------------------------------------------|
| **L’origine des styles**      | Détermine d'où vient la règle CSS : navigateur, feuille CSS de l'utilisateur, CSS de l'auteur (vous). | Les styles du navigateur sont par défaut (`<h1>` en gras). |
| **La spécificité des sélecteurs** | Plus un sélecteur est précis, plus il a de poids.                        | `#id` > `.classe` > `balise`                 |
| **L’ordre d’apparition**      | En cas d’égalité, la dernière règle déclarée l’emporte.                    | Si deux règles ont la même spécificité, celle qui vient en dernier s’applique. |

- La cascade permet de gérer les conflits entre plusieurs règles CSS.
- La spécificité joue un rôle clé pour déterminer quelle règle s’applique.
- L’ordre d’apparition influence le style si les règles ont la même spécificité.
- !important peut écraser toutes les règles, mais doit être utilisé avec précaution.

## L'heritage 

L'héritage en CSS est le mécanisme qui permet aux éléments enfants de récupérer automatiquement certaines propriétés définies pour leur parent, notamment les styles liés au texte comme `color` et `font-family`. Il peut être forcé avec `inherit` ou annulé avec `initial` et `unset`.

| Mot-clé    | Comportement |
|------------|-------------|
| **`inherit`** | Fait hériter la valeur du parent, même si la propriété ne s'hérite pas naturellement. |
| **`initial`** | Réinitialise la propriété à sa **valeur par défaut** du navigateur. |
| **`unset`** | Se comporte comme `inherit` pour les propriétés héritables, et comme `initial` pour les autres. |


| Concept | Définition | Exemple |
|---------|------------|---------|
| Héritage | Les enfants récupèrent certaines propriétés du parent (ex: `color`, `font-family`). | `<p>` hérite la couleur définie dans `<body>`. |
| Cascade | Priorité entre plusieurs styles en fonction de leur spécificité et ordre d'apparition. | Un `h1` rouge peut être écrasé par un `h1 { color: blue; }` ajouté après. |

- L'héritage s'applique surtout aux propriétés textuelles (comme color).
- On peut forcer l’héritage avec inherit, ou le bloquer avec initial.
- L'héritage simplifie le CSS, mais doit être compris pour éviter les erreurs.

## Flexox

Flexbox (Flexible Box) est un modèle de mise en page CSS qui facilite l'alignement et la distribution des éléments dans un conteneur, même si la taille des éléments est inconnue ou dynamique. Il est particulièrement utile pour créer des mises en page réactives.

### Activer Flexbox

Pour utiliser Flexbox, on applique `display: flex;` sur un élément parent.

### Aligner les éléments

🔸 Sur l'axe principal `justify-content`

Gère __l’alignement horizontal__ des éléments.
```css
.container {
  justify-content: center; /* Centre les boîtes */
}
```

Autres valeurs utiles :

__flex-start__ ➝ Aligné à gauche.

__flex-end__ ➝ Aligné à droite.

__space-between__ ➝ Espacement maximal.

__space-around__ ➝ Espacement équilibré.

__space-evenly__ ➝ Espacement uniforme.

### align-items

Gère __l’alignement vertical__ des éléments.
```css
.container {
  align-items: center; /* Centre verticalement */
}
```
Autres valeurs utiles :

__flex-start__ ➝ Aligné en haut.

__flex-end__ ➝ Aligné en bas.

__stretch__ ➝ Étire les éléments.

__baseline__ ➝ Aligne sur la ligne de base du texte.

![Image du flexbox](flexbox.jpg)

![Image du flex-wrap](flew-wrap.png)

# 🎯 Introduction à CSS Grid

**CSS Grid** est un système de mise en page en deux dimensions qui permet d'organiser des éléments sous forme de grille, avec des colonnes et des lignes.

##  1. Activer CSS Grid
Pour utiliser **CSS Grid**, appliquez `display: grid;` à un conteneur :  

```css
.container {
  display: grid;
}
```

Tout élément **enfant** de ce conteneur sera positionné dans la grille.

---

## 📏 2. Définir une grille

###  a) Définir les colonnes et les lignes
Utilisez `grid-template-columns` et `grid-template-rows` :  

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px 100px; /* 3 colonnes */
  grid-template-rows: 150px 150px; /* 2 lignes */
}
```

- Ici, la grille a **3 colonnes** (100px, 200px, 100px) et **2 lignes** (150px, 150px).

📌 **Astuce :** Utilisez `fr` (fraction) pour un partage équitable de l’espace :  

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr; /* La 2e colonne est deux fois plus large */
}
```

---

## 3. Positionner les éléments

Par défaut, les éléments se placent automatiquement. Mais vous pouvez les positionner précisément avec `grid-column` et `grid-row` :

```css
.item {
  grid-column: 1 / 3; /* Occupe de la colonne 1 à 3 */
  grid-row: 1 / 2; /* Occupe la première ligne */
}
```

Ou plus simplement :

```css
.item {
  grid-column: span 2; /* Occupe 2 colonnes */
}
```

---

## 4. Espacement et alignement

###  a) Espacer les éléments
Utilisez `gap` pour ajouter un espace entre les cellules :

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px; /* 10px d’espace entre les éléments */
}
```