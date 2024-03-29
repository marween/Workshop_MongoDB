# Exercices MongoDB:

*  Exercice 1: 

Crée une base de donnée workshop et la collection intitulée 'musique' dans cette dernière db, on retrouvera:

- les données de l'albums (titre, score et genre)
- les données de l'auteur (nom, score, label)
- les données du genre (nom)
- les données de la musique évidemment (titre, année, durée)

*Ecrivez le json de la structure de la collection. Vérifier avec notre solution et si vous avez des questions appelez-nous.*

<details>

<summary>Solution:</summary>
<pre><code>use workshop
db.createCollection('musique')
</code></pre>
<pre><code>{ 
  "titre" : "Deathgrip",
  "année" : "2016",
  "durée" : "4 : 24",
  "genre" : [ 
    { 
      "nom" : "Metalcore"
    }
  ],
  "auteurs": [ 
    {
      "nom": "Fit For A King",
      "score": 8,
      "label": "Solid State"
    }
  ],
  "albums": [
    {
      "titre" : "Deathgrip",
      "score" : 8,
      "genre" : [
        { 
          "nom" : "Metalcore"
        }
      ]
    }
  ]
}
</code></pre>

</details>

* Exercice 2: 

Nous allons faire une base de données avec plusieurs musiques. Donc il se serait préférable de l'appeler 'musiques'.
Renomme la base de données.

<details>

<summary>Solution:</summary>
<pre><code>db.musique.renameCollection("musiques", true)
</code></pre>

</details>

* Exercice 3: 

[Voici](./database.json) une DB déjà remplie, 
 
  * Importe la collection via compas 
  * Ajoute une entrée dans la collection 
 
<details>
<summary>Solution:</summary>
<pre><code>db.musiques.insert({ 
  titre : "Title",
  année : "2016",
  durée : "4 : 24",
  genre : [ 
    { 
      nom : "Genre"
    }
  ],
  auteurs: [ 
    {
      nom: "Artist Name",
      score: 8,
      label: "Label"
    }
  ],
  albums: [
    {
      titre : "Album Title",
      score : 8,
      genre : [
        { 
          nom :"Genre"
        }
      ]
    }
  ]
})
</code></pre>
</details>

* Exercice 4:

Un troll est passé dans notre db et a rajouté 'La Danse des Canards'. Supprimons cette chose avant d'avoir l'envie de la danser.

<details>
<summary>Solution :</summary>

` db.musiques.remove( {"titre": "La Danse Des Canards"} ) `

</details>

* Exercice 5: 

Trouves les musiques dont le score de l'auteur est d'au moins de 6 et dont l'album a recu un score de 5

<details>
<summary>Solution:</summary>

` db.musiques.find({ $and: [ { "auteurs.score": {$gte:6} }, { "albums.score":5 } ] } ).pretty()`

</details>

* Exercice 6: 

Calcul la moyenne des albums de 'Fit For A King'

<details>
<summary>Solution:</summary>

<pre><code> 
varMatch = {$match : {"auteurs.nom":"Fit For A King"}};
varUnwind = { $unwind : {path : "$albums"}};
varAvg = {$avg : "$albums.score"};
varGroup = { $group : {"_id" : "Fit For A King albums", "moyenne" : varAvg } };
db.musiques.aggregate([ varMatch, varUnwind, varGroup ]);
</code></pre>

</details>

* Exercice 7: 

Nous voudrions comparer le score de l'auteur 'Fit For A King' avec l'ensemble de ses albums. Affichez le score à l'écran. Si vous êtes motivé tenter avec le comparateur. 

<details>
<summary>Solution:</summary>

<pre><code> 
varMatch = {$match : {"auteurs.nom":"Fit For A King"}};
varUnwind = { $unwind : {path : "$albums"}};
varAvg = {$avg : "$albums.score"};
varGroup = { $group : {"_id" : "Fit For A King albums", "moyenne" : varAvg } };

varAgg1 = db.musiques.aggregate([ varMatch, varUnwind, varGroup ]).toArray()[0]["moyenne"];
varAgg2 = db.musiques.aggregate([varMatch]).toArray()[0]["auteurs"][0]["score"];


varCmp = { $cmp : [ varAgg1, varAgg2]};
db.musiques.aggregate( [ { $project: { cmpToArt: varCmp } } ] );
</code></pre>

</details>

