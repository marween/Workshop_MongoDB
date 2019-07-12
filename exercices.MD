# Exercices MongoDB:

*  <u>Exercice 1</u>: Crée une base de donnée intitulée 'musiques' dans laquelle on retrouvera:

- les donnéees de l'albums (titre, score et genre)
- les donnéees de l'auteur (nom, score, label)
- les données du genre (nom)
- les données de la musique évidemment (titre, année, durée)

*Ecrivez le json de la structure de la base de données. Vérifier avec notre solution et si vous avez des questions appelez-nous.*

<details>
<summary>Solution:</summary>

```json
{ 
  "titre" : "Wow",
  "année" : "2011",
  "durée" : "3 : 40",
  "genre" : 
    [ 
      { 
		"nom" : "Pop"
	  }, 
      { 
		"nom" : "Rock" 
	  }
    ],
  "auteurs":
    [ 
      {
        "nom": "Michel",
        "score": 5,
		"label": "Epitaph Records"
      },
      {
        "nom":"Bob",
        "score": 6,
		"label": "SoloLearn"
      }
    ],
  "albums":
    [
		{
		  "titre" : "Super Album",
		  "score" : 5,
		  "genre" : ["Metalcore"]
		}
	]
}
```
</details>

* <u>Exercice 2</u>: Voici une DB déjà remplie, 
 
  * Crée une nouvelles DB workshop_musique 
  * Importe la collection via compas 
  * Ajoute une entrée dans la collection 
 
 
* <u>Exercice 3</u>: Trouves les musiques dont le score est plus grand que 5 et donc l'albums a recu plus de 8

* <u>Exercice 4</u>: Calcul de moyenne des album de tel 'machin'

* <u>Exercice 5</u>: Compare la moyenne de l'auteur 'machin' avec l'ensemble de ses albums. 