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

Voici une DB déjà remplie, 
 
  * Importe la collection via compas 
  * Ajoute une entrée dans la collection 
 
<details>
<summary>Solution:</summary>
<pre><code>db.musiques.insert({ 
  titre : "Deathgrip",
  année : "2016",
  durée : "4 : 24",
  genre : [ 
    { 
      nom : "Metalcore"
    }
  ],
  auteurs: [ 
    {
      nom: "Fit For A King",
      score: 8,
      label: "Solid State"
    }
  ],
  albums: [
    {
      titre : "Deathgrip",
      score : 8,
      genre : [
        { 
          nom :"Metalcore"
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

Trouves les musiques dont le score est plus grand que 6 et dont l'album a recu un score de 5

<details>
<summary>Solution:</summary>

` db.musiques.find({ $and: [ { "auteurs.score": {$gte:6} }, { "albums.score":5 } ] } ).pretty()`

</details>

* Exercice 6: 

Calcul la moyenne des albums de 'machin'

<details>
<summary>Solution:</summary>

` `

</details>

* Exercice 7: 

Compare la moyenne de l'auteur 'machin' avec l'ensemble de ses albums. 

<details>
<summary>Solution:</summary>

` `

</details>