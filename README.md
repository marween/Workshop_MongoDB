# Workshop_MongoDB

## Installation de l'environnement
### Installation de MongoDB:
 ```
 sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 68818C72E52529D4
 sudo echo "deb http://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
 sudo apt-get update
 sudo apt-get install -y mongodb-org 
 ```
 
 ## Lancer/ Fermer MongoDB:
 `sudo service mongodb start`
 `sudo service mongodb stop`
 
 
 ## lancer le shell:
 `mongo`
 
 ### Installation de Compas:
 [Compas](https://www.mongodb.com/download-center/compass?jmp=docs)
 (version community)
 
 ### Connection:
 hostname:localhost 
 
 port: 27017
 
 ## Initialisation de la DB:
 ### Verification de la DB courante:
  ` db `
 ### Switch sur la DB et créé cette dernière si celle-ci n'existe pas:
 ` use [nom de la DB] `
### Créer une collection
`db.createCollection("[name]")`

### Montrer toutes les collections de la DB:
 `show collections `
 
### Supprimer la collection:
`db.user.drop()`

### lien vers la doc
[doc MongoDB](https://docs.mongodb.com/manual/reference/mongo-shell/)

 ### Quelques commandes utiles:
 Voir notre [cheatsheet](./cheatsheet.md)
