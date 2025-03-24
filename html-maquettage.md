# Le maquattage

__Le maquettage d'interface graphique__ ou __wireframing__, consiste à créer une représentation visuelle simplifiée de l'interface d'une application avant le développement réel. Cela permet de définir la structure, l'ergonomie et les fonctionnalités de l'interface sans entrer dans les détails graphiques.

__Le zoning__ détermine la structure des pages clés du futur site web.

__Un mockup__ est une maquette détaillée de la future interface web ou mobile.

__Une maquette__ dans le domaine du design d'interface est une représentation visuelle plus détaillée d'une application ou d'un site web

| # | Concept      | Description                                                                 | Détail Principal                           |
|---|--------------|-----------------------------------------------------------------------------|--------------------------------------------|
| 1 | **Zoning**   | Organisation générale de l'interface en zones fonctionnelles               | Structure globale sans design graphique    |
| 2 | **Wireframe**| Représentation simple de la structure de l'interface (sans éléments visuels) | Hiérarchie et agencement des éléments     |
| 3 | **Mockup**   | Représentation visuelle détaillée de l'interface                            | Design graphique sans interactivité        |
| 4 | **Maquette** | Version avancée ou finale du design avec une présentation soignée          | Souvent interchangeable avec mockup, peut être interactif |

##  Choix d'un outil de maquettage

Pour des __wireframes rapides et simples__ : Balsamiq ou Marvel App.

Pour des __maquettes détaillées et un prototypage interactif__ : Figma, Adobe XD ou InVision.

Pour une __utilisation professionnelle avec des fonctionnalités avancées__ : Sketch ou Axure RP.

## Cadrer la demande d'un client

Cadrer la demande client permet d’assurer __une bonne compréhension du projet__ et d’éviter les imprévus. C’est __une étape clé__ pour garantir une conception efficace et alignée aux attentes du client. Un bon cadrage facilite aussi la communication entre les équipes et réduit le risque de modifications tardives qui peuvent impacter le budget et les délais.

##  les règles ergonomiques et d'expérience utilisateur

__Les règles ergonomiques__  améliorent l’expérience utilisateur en rendant une interface plus intuitive, efficace et agréable. Une bonne ergonomie réduit l'effort mental de l’utilisateur, minimise les erreurs et facilite l’accès aux informations essentielles. (voir les 10 heuristiques de Jakob Nielsen)

__L’expérience utilisateur ou UX__ est un élément clé du succès d’un produit ou d’un service numérique. Une bonne UX améliore la satisfaction des utilisateurs, réduit la frustration et favorise la fidélisation. En appliquant les principes UX dès la conception, on garantit une interface intuitive, efficace et agréable à utiliser.

# HTML

__MDN Web Docs__ est une ressource incontournable pour tout développeur web. Savoir se __documenter efficacement__ avec MDN permet de __gagner du temps__, d'éviter les erreurs et de se __tenir à jour avec les évolutions du web__.

## HTML, CSS , JS

| **Technologie** | **Rôle**         | **Que fait-elle ?**                              |
|-----------------|------------------|--------------------------------------------------|
| **HTML** (HyperText Markup Language) | Structure         | Définit la structure et le contenu d'une page web (titres, paragraphes, images, liens...). |
| **CSS** (Cascading Style Sheets) | Style            | Gère l'apparence visuelle de la page (couleurs, polices, mise en page, animations...). |
| **JavaScript** | Dynamisme        | Ajoute de l'interactivité et des fonctionnalités avancées (animations, événements, requêtes serveur, etc.). |



## Comprendre la structure de base HTML et la syntaxe

Explication des Éléments de la Structure :

    <!DOCTYPE html> :

        Cette déclaration informe le navigateur qu'il s'agit d'un document HTML5.

        Elle doit toujours être présente au début du document HTML.

    <html lang="fr"> :

        Balise racine de tout document HTML.

        L'attribut lang="fr" spécifie que la langue du contenu est le français.

    <head> :

        Contient les métadonnées du document (informations non visibles pour l’utilisateur, comme les liens vers des fichiers CSS, des icônes, etc.).

        Les éléments clés à l’intérieur de <head> :

            <meta charset="UTF-8"> : Spécifie le jeu de caractères utilisé pour que les caractères spéciaux s'affichent correctement.

            <meta name="viewport" content="width=device-width, initial-scale=1.0"> : Règle la mise en page pour les appareils mobiles.

            <title> : Définit le titre de la page qui apparaît dans l'onglet du navigateur.

    <body> :

        Contient tout le contenu visible de la page web (textes, images, liens, formulaires, etc.).


## Les attributs

Les attributs HTML sont essentiels pour personnaliser et enrichir le comportement des éléments HTML. En comprenant leur utilisation et en les utilisant correctement, vous pouvez contrôler l’apparence, la fonctionnalité et l’interaction d’un site web de manière efficace. (ex:href, img)

## Les commentaires 

Les __commentaires__ en HTML permettent d'insérer des notes ou des explications dans le code sans qu'elles soient affichées dans le navigateur. Ils sont utiles pour ajouter des annotations à votre code, expliquer une partie de la structure, ou désactiver temporairement une section de code sans la supprimer.


**Syntaxe** :

```
<!-- Ceci est un commentaire en HTML -->
```

## Principe de Parent/Enfant en HTML

Un **élément enfant** est un élément qui se trouve à l'intérieur d'un autre élément (le parent). L'enfant peut être un autre élément HTML ou du texte.

Un **élément parent** est un élément qui contient d'autres éléments à l'intérieur de lui. En d'autres termes, un parent est un élément qui **englobe** ou **contient** un ou plusieurs autres éléments.

### Exemple :

```html
<div>
    <p>Voici un paragraphe à l'intérieur d'un div.</p>
</div>

Ici, la balise <div> est l'élément parent, et la balise <p> est l'élément enfant.

Le <div> contient le <p>, ce qui fait du <div> un parent et du <p> un enfant.


