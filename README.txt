Supprimer tous les containers : 

`docker rm -vf $(docker ps -aq)` 

Supprimer toutes les images : 

`docker rmi -f $(docker images -aq)`

Se connecter dans un container en SSH :

`docker exec -it <CONTAINER_NAME> /bin/bash`

Voir en temps réel les logs de tous les container en cours pour un compose défini :

`docker-compose logs -f `

Lancer un container flask en daemon avec exposition des ports :

`docker run -d -p 8080:5000 --name flask flask:latest`


* Dozzle : permet d'avoir des métriques basiques sur les container (les logs en temps réel, mémoire, charge)
* Dockprom : stack de monitoring avec plusieurs outils (graphana, prometheus, ...)
* Buildx : permet de stocker du cache sur un registry renseigné. Permet d'accélérer les build partagés.
* hugo : permet de générer un site en statique à partir de code sources en yaml etc.
* minio : eg. bucket dans le cloud like


Ressources : 

* https://github.com/docker/docker-bench-security
* https://github.com/valentin2105/VagrantLab
* https://github.com/valentin2105/docker-niveau2

Swarm :

initialiser le swarm master : 

`docker swarm init`

Rejoindre un swarm : copier coller la commande fournie par l'init

Rendre un noeud du swarm indisponible : 

`docker node update --availability drain $HOST`

Vérifier le status des noeuds dans le swarm : 

`docker node ls`

fzf : recherche dans l'historique
tmux powerline : pour la barre sympa en bas
vimium : https://github.com/philc/vimium/blob/master/README.md
hulk : https://github.com/grafov/hulk/tree/master