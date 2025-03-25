# HTML

## Les tableaux

![explication d'un tableau](<tableau html.png>)

Un tableau en HTML est défini avec la balise __table__. Il contient généralement :

    Ligne d'en-tête : <thead> (optionnel)

    Corps du tableau : <tbody> (obligatoire)

    Ligne de pied de page : <tfoot> (optionnel)

    Lignes et cellules :

        Lignes : <tr> (table row)

        Cellules d'en-tête : <th> (table header, en général dans <thead>)

        Cellules de données : <td> (table data, dans <tbody>)

## Les inpunts

En HTML, un __input__ est un élément de formulaire qui permet aux utilisateurs de saisir des données (texte, mdp, le nom, etc.). Il est défini avec la balise input (mettre autour de input <>) et peut prendre plusieurs types en fonction de son usage.

```html
<input type="email" placeholder="Votre email">
```

## Les formulaires

```html
<form action="traitement.php" method="POST">
    <!-- Champ texte -->
    <label for="nom">Nom :</label>
    <input type="text" id="nom" name="nom" required>

    <!-- Champ email -->
    <label for="email">Email :</label>
    <input type="email" id="email" name="email" required>

    <!-- Bouton d'envoi -->
    <input type="submit" value="Envoyer">
</form>
```

Explication :

    <form> : Définit le formulaire.

    action="traitement.php" : Page où les données seront envoyées.

    method="POST" : Méthode d'envoi (POST pour sécuriser les données).

    (Autre méthode) La méthode GET envoie les données du formulaire dans l'URL

    <label> sert à associer un texte à un champ de formulaire.




