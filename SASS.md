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