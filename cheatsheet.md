##Interroger sa base de données:
`db.[dbname].findOne()`
`db.[dbname].find()`

 1. aggregate()
 
`db.[dbname].aggregate([])`
 
`{$match : {} }` : C’est le plus simple, il correspond au premier paramètre de la requête find.Il permet donc de filtrer le contenu d’une collection.

`{$project : {} }` : C’est le second paramètre du find. Il donne le format de sortie des documents (projection). Il peut par ailleurs être utilisé pour changer le format d’origine.

`{$sort : {} }` : Trier le résultat final sur les valeurs d’une clé choisi.

`{$group : {} }` : C’est l’opération d’agrégation. Il va permettre de grouper les documents par valeur, et appliquer des fonctions d’agrégat. La sortie est une nouvelle collection avec les résultats de l’agrégation.

`{$unwind : {} }` : Cet opérateur prend une liste de valeur et produit pour chaque élément de la liste un nouveau document en sortie avec cet élément. Il pourrait correspondre à une jointure, à ceci près que celle-ci ne filtre pas les données d’origine, juste un complément qui est imbriqué dans le document. On pourrait le comparer à une jointure externe avec imbrication et listes.

 * variables 

``` varMatch = { $match : { "grades.0.grade":"C"} };
varProject = { $project : {"name":1, "borough":1, "_id":0}};
db.restaurants.aggregate( [ varMatch, varProject ] );
```

 * Groupements simples:
  
 Celui-ci doit contenir obligatoirement une clé de groupement (_id), puis une clé (total) à laquelle on associe la fonction d'agrégation ($sum) :



 * Groupement par valeur:
 
  lors de l’exécution on va indiquer qu'il faut utiliser la valeur de la clé pour l'agrégation.



2. Unwind

l'opérateur $unwind va retirer chaque élémént de la liste. 
exemple: pour faire la moyenne



## Mettre à jour les données
* update
```db.restaurants.update (
   {"grades.grade" : {$not : {$eq : "C"}}},
   {$set : {"comment" : "acceptable"}}
);

WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
```
* remove
```
db.restaurants.remove(
   {"note":0},
   {"multi" : true}
);
```
* save
```db.restaurants.save({"_id" : 1, "test" : 1});```