exercices MongoDB:

1 Crée une base de donnée intitulée 'musiques' dans laquelle on retrouvera:
- les donnéees de l'albums (titre, score et genre)
- les donnéees de l'auteur (nom, score, label)
- les données du genre (nom)
- les données de la musique évidemment (titre, année, durée)

*Ecriver le json de la structure de la base de données. Vérifier avec notre solution et si questions appelez-nous.*

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

2. Voici une DB déjà remplie, 
 a. crée une nouvelles DB workshop_musique
 b. exporte la collection via compas
 c. ajoute une entrée dans la collection
 

3. Trouves les musiques dont le score est plus grand que 5 et donc l'albums a recu plus de 8

4. calcul de moyenne des album de tel 'machin'

5. Compare la moyenne de l'auteur 'machin' avec l'ensemble de ses albums. 