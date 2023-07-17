Supprimer tous les containers : 

`docker rm -vf $(docker ps -aq)` 

Supprimer toutes les images : 

`docker rmi -f $(docker images -aq)`

Se connecter dans un container en SSH :

`docker exec -it <CONTAINER_NAME> /bin/bash`

Voir en temps réel les logs de tous les container en cours pour un compose défini :

`docker-compose logs -f `

* Dozzle : permet d'avoir des métriques basiques sur les container (les logs en temps réel, mémoire, charge)
* Dockprom : stack de monitoring avec plusieurs outils (graphana, prometheus, ...)
* Buildx : permet de stocker du cache sur un registry renseigné. Permet d'accélérer les build partagés.
* hugo : permet de générer un site en statique à partir de code sources en yaml etc.