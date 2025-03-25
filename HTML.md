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

__Explication__ :

    <form> : Définit le formulaire.

    action="traitement.php" : Page où les données seront envoyées.

    method="POST" : Méthode d'envoi (POST pour sécuriser les données).

    (Autre méthode) La méthode GET envoie les données du formulaire dans l'URL

    <label> sert à associer un texte à un champ de formulaire.

## Dropdwowns, Boutons radio, Checkbox

### Dropdown 

Un __dropdown__ est une liste déroulante qui permet à l'utilisateur de choisir une option parmi plusieurs. Il est créé avec les balises select et option (mettre en<>).

__Exemple__ :


```
<label for="pays">Pays :</label>
<select id="pays" name="pays" required>
    <option value="">-- Sélectionnez un pays --</option>
    <option value="france">France</option>
    <option value="belgique">Belgique</option>
    <option value="canada">Canada</option>
</select>
```

__Explications__ :

    <select> : Crée la liste déroulante.

    <option> : Définit chaque option dans la liste. L’attribut value définit la valeur envoyée lorsque l'utilisateur fait un choix.

    required : Indique que l'utilisateur doit faire un choix avant d'envoyer le formulaire.

### Boutons radio 

Les __boutons radio__ permettent à l'utilisateur de choisir une seule option parmi plusieurs. Ils sont utilisés lorsque __un seul choix__ est permis dans un groupe d'options.

__Exemple__:

```
<label>Genre :</label>
<input type="radio" name="genre" value="homme" required> Homme
<input type="radio" name="genre" value="femme"> Femme
<input type="radio" name="genre" value="autre"> Autre
```

```
<input type="radio"> : Crée un bouton radio.
```
name="genre" : Tous les boutons radio du même groupe doivent avoir le même nom. Cela garantit que l'utilisateur peut choisir une seule option parmi plusieurs.

### Checkbox

Les __checkboxes__ permettent à l'utilisateur de sélectionner __plusieurs options__ parmi plusieurs. Contrairement aux boutons radio, plusieurs cases peuvent être sélectionnées à la fois.

__Exemple__:

```
<label>Centres d'intérêt :</label>
<input type="checkbox" name="interet" value="sport"> Sport
<input type="checkbox" name="interet" value="musique"> Musique
<input type="checkbox" name="interet" value="lecture"> Lecture
```

__Explications__ :

    <input type="checkbox"> : Crée une case à cocher.

    name="interet" : Le nom peut être le même pour plusieurs cases à cocher, ce qui permet de les envoyer ensemble dans les données du formulaire.

    value="sport" : La valeur envoyée lorsque l'utilisateur coche cette case.

__Important__ :

    L'utilisateur peut cocher plusieurs cases en même temps, et la valeur envoyée pour chaque case est le value associé à chaque <input>.

__Résumé__ :

__Dropdown__ :

- Permet de choisir une seule option dans une liste déroulante.

- L'utilisateur clique pour afficher les options et choisit une seule option.

__Boutons radio__ :

- Permet de choisir une seule option parmi plusieurs.

- Seul un bouton radio d’un même groupe (name) peut être sélectionné.

__Checkboxes__ :

- Permet de sélectionner plusieurs options.

- L'utilisateur peut cocher plusieurs cases.


## Insérer une vidéo

### Vidéo youtube

Pour insérer une vidéo YouTube, on utilise la balise```<iframe>```

__Étapes__ :

1. Aller sur Youtube
2. Clique sur __Partager__ et ensuite sur __Intégrer__
3. Copier le lien 

__exemple__: 

```
<iframe width="560" height="315" src="lien de la vidéo" frameborder="0" allowfullscreen></iframe>
```

__width et height__ : Définit la taille de la vidéo (tu peux ajuster ces valeurs).

__frameborder="0"__ : Retire la bordure autour de l'iframe.

__allowfullscreen__ : Permet à l'utilisateur de regarder la vidéo en plein écran.

### Insérer une vidéo locale

Pour insérer une vidéo locale, on utilise la balise ```<video>```

__Exemple__ :
```
<video width="720" height="480" controls>
    <source src="source-de-la-vidéo.mp4" type="video/mp4">
    <source src="source-de-la-vidéo.ogg" type="video/ogg">
    Votre navigateur ne supporte pas la balise vidéo.
</video>
```
__Explications__ :

    <video> : C'est la balise principale pour inclure une vidéo.

        controls : Ajoute des contrôles (play, pause, volume, etc.) pour l'utilisateur.

    <source> : Permet de définir différents formats vidéo pour une meilleure compatibilité avec les navigateurs.

        Ici, tu peux proposer deux formats : .mp4 (très répandu) et .ogg (utile pour les navigateurs ne supportant pas le MP4).

    Texte alternatif : Si le navigateur ne prend pas en charge la balise vidéo, ce texte sera affiché.


