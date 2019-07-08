## Lien vers la documentation shell pour MongoDb:
[Lien](https://docs.mongodb.com/manual/introduction/)

## Listes des opérateurs:
|Opérateur|Symbole|Signification|Exemple|
|:-------|-------|-------|-------|
| $gt , $gte | > , ≥ | Plus grand que | "a" : {"$gt" : 10} |
| $lt , $lte | < , ≤ | Plus petit que | "a" : {"$lt" : 10} | 
| $ne | ≠ | Différent de | "a" : {"$ne" : 10} |
| $in , $nin | ∈ , ∉ |  fait partie de | "a" : {"$in" : [10, 12 , 15, 18 ] } |
| $or | ∨ | OU logique | "a" : {"$or" : [ {"$lt" : 10}, {"$gt" : 10} ] } |
| $and | ∧ | ET logique | "a" : {"$and" : [ {"$lt" : 10}, {"$gt" : 10} ] } |
| $not | ¬ | Négation | "a" : {"$not" : {"$lt" : 10} } |
| $exists | Ǝ | existe | "a" : {"$exists" : 1} |
| $size | | test sur la taille | "a" : {"$size" : 5} |



## Insertion d'élément dans la base de données:
* Insertion (*insertOne(), insertMany(), insert()*):  
```
db.[dbname].insertMany (
   { <objet> },
   { <objet> }
);
```
Il existe aussi la fonction save() pour plus d'info aller voir la doc.

## Interroger sa base de données:
```
db.[dbname].findOne({<objet>})
db.[dbname].find({<objet>})
```

## aggregate()
 
`db.[dbname].aggregate([])`
 
`{$match : {} }` : C’est le plus simple, il correspond au premier paramètre de la requête find.Il permet donc de filtrer le contenu d’une collection.

`{$project : {} }` : C’est le second paramètre du find. Il donne le format de sortie des documents (projection). Il peut par ailleurs être utilisé pour changer le format d’origine.

`{$sort : {} }` : Trier le résultat final sur les valeurs d’une clé choisi.

`{$group : {} }` : C’est l’opération d’agrégation. Il va permettre de grouper les documents par valeur, et appliquer des fonctions d’agrégat. La sortie est une nouvelle collection avec les résultats de l’agrégation.

`{$unwind : {} }` : Cet opérateur prend une liste de valeur et produit pour chaque élément de la liste un nouveau document en sortie avec cet élément. Il pourrait correspondre à une jointure, à ceci près que celle-ci ne filtre pas les données d’origine, juste un complément qui est imbriqué dans le document. On pourrait le comparer à une jointure externe avec imbrication et listes.

[...]

Pour plus de fonction d'agrégation se réferrer à la doc.

### Les variables 
``` 
varMatch = { <aggregate function> };
varProject = { <aggregate function> };
db.[dbname].aggregate( [ varMatch, varProject ] );
```

## Mettre à jour les données
* Mise à jour (*updateOne(), updateMany(), replaceOne()*):  
```
db.[dbname].updateMany (
   { <champsDB: { <operator>: <valeur> } },
   {$set : {<champsDB> : <valeur>}}
);
```
* Suppression (*remove(), deleteOne(), deleteMany()*) 
```
db.[dbname].deleteMany(
   {<champsDB> : <valeur>}
);
```
