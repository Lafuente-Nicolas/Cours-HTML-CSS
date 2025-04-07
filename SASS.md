## Préprocesseur 

 C'est un programme permettant de générer du code css à partir de sa propre syntaxe.

Pourquoi l'utiliser ?

  - La compilation de feuilles de style CSS (qui peut se faire encore plus facilement avec le framework Compass) ;

  - La création de variables, pour stocker des valeurs qui puissent être réutilisables, comme pour des couleurs, des tailles de typo, des marges... ;

  - La création d'un mixin qui définit un ensemble de règles CSS qui pourraient, par exemple, être appelées à différents endroits dans le CSS. L'intérêt est alors de faciliter la réutilisation de ces règles.

  - La création de fonctions pour manipuler des valeurs CSS. Par exemple, vous pouvez facilement convertir une valeur initialement exprimée en pixels en pourcentage ou en REM.

  - La création de conditions et de boucles, qui permettent de créer des règles dynamiques, qui seraient utilisables sur certaines pages et pas d'autres.

__conclusion :__

- Gagne du temps : Moins de répétition, plus d’automatisation.
-  Facilite la maintenance : Modifications rapides grâce aux variables et mixins.
- Améliore la structure : Code plus propre et organisé.
- Plus de puissance : Ajoute des fonctionnalités que CSS seul ne propose pas.

### Le Mécanisme du Preprocessing en CSS (Input ➡️ Output)

Un préprocesseur CSS (comme Sass ou Less) agit comme un compilateur qui transforme un code CSS enrichi en CSS standard utilisable par les navigateurs.

- __Étapes du Preprocessing__ :

1. Écriture du code avec un préprocesseur (Input)

    Utilisation de variables, mixins, imbrication, etc.

2. Compilation par le préprocesseur

    Transformation du code en CSS standard

3. Génération du fichier CSS final (Output)

    Ce fichier est chargé par le navigateur

          🎨 Code avec préprocesseur (Input)
          ┌───────────────────────────────┐
          │ $primary-color: #3498db;      │  (SCSS/Less)
          │                               │
          │ button {                      │
          │   background-color: $primary-color; │
          │   color: white;               │
          │ }                             │
          └───────────────────────────────┘
                    ⬇  (Compilation)

          ⚙️ Le préprocesseur (Sass/Less)
          ┌───────────────────────────────┐
          │ Transforme le code en CSS pur │
          └───────────────────────────────┘
                    ⬇  

          ✅ Code CSS standard (Output)
          ┌───────────────────────────────┐
          │ button {                      │
          │   background-color: #3498db;  │
          │   color: white;               │
          │ }                             │
          └───────────────────────────────┘
                    ⬇  

          🌍 Chargé par le navigateur ! 🚀

### Compiler le SCSS et le css

Noter dans le terminal :
``` 
sass --watch style.scss:style.css
```
## Variable SASS

Une variable permet de stocker une valeur qu’on pourra réutiliser plusieurs fois dans le fichier .scss.
C’est comme une petite boîte dans laquelle on mets quelque chose (une couleur, une taille, une police…), et qu'on peux ouvrir à chaque fois qu'on en as besoin.

Les variables en SASS __commencent toujours par un $.__

exemple:

```scss
$ma-couleur: #ff5733;
$taille-texte: 18px;
$ma-police: 'Roboto', sans-serif;
```
```scss
body {
  color: $ma-couleur;
  font-size: $taille-texte;
}
```
### Ou mettre les variables :

En général, tu les mets tout en haut de ton fichier .scss, ou mieux encore : Tu crées un fichier spécial juste pour elles, par exemple : variables.scss

## L'imbrication 

 L’imbrication (ou nesting) est une des fonctionnalités les plus pratiques de SASS, et elle permet d’écrire ton CSS de façon plus claire et structurée, surtout quand tu travailles avec des éléments HTML imbriqués (comme dans un menu, un formulaire, etc.).

```scss
 .card {
  background: white;

  h2 {
    font-size: 24px;
  }

  p {
    color: grey;
  }
}
```

### Utiliser le & 

Le symbole `&` sert à réutiliser le nom du parent dans les sous-sélecteurs. C’est super utile pour les pseudo-classes, les états (:hover, :active, etc.)

```scss
.button {
  background: blue;
  color: white;

  &:hover {
    background: darkblue;
  }
}
```
Il vaut mieux limiter __l’imbrication à 2 ou 3 niveaux max__.

exemple complet: 

```scss
.navbar {
  background-color: #333;

  ul {
    list-style: none;

    li {
      display: inline-block;

      a {
        color: white;
        text-decoration: none;

        &:hover {
          color: #f39c12;
        }
      }
    }
  }
}
```

## L'héritage 

Le mot-clé `@extend` permet de partager les propriétés d'une règle CSS avec une autre règle. Lorsque tu utilises `@extend`, la règle qui reçoit l'extension hérite de toutes les propriétés de la règle source, sans dupliquer le code.

Exemple simple :

Imaginons que tu as une classe `.base` avec des propriétés communes :

```scss
.base {
  font-family: Arial, sans-serif;
  color: #333;
  line-height: 1.5;
}
```
Tu veux qu’une autre classe hérite de ces propriétés sans répéter le même code. Tu peux utiliser `@extend` :

```scss
.button {
  @extend .base;
  background-color: #3498db;
  padding: 10px 20px;
}
```