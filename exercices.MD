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
```
use workshop
db.createCollection('musique')
```
```json
{ 
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
```
</details>
* Exercice 2: 

Nous allons faire une base de données avec plusieurs musiques. Donc il se serait préférable de l'appeler 'musiques'.
Renomme la base de données.

<details>
<summary>Solution:</summary>
```
db.musique.renameCollection("musiques", true)
```
</details>
* Exercice 3: 

Voici une DB déjà remplie, 
 
  * Importe la collection via compas 
  * Ajoute une entrée dans la collection 
 
<details>
<summary>Solution:</summary>
```
db.musiques.insert({ 
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
```
</details>

* Exercice 4: 

Trouves les musiques dont le score est plus grand que 5 et donc l'albums a recu plus de 8

* Exercice 5: 

Calcul de moyenne des album de tel 'machin'

* Exercice 6: 

Compare la moyenne de l'auteur 'machin' avec l'ensemble de ses albums. 
