# DOCKER
      JOUR1
docker --version
# Vérifier la version installée de Docker

docker info
# Voir les informations générales de Docker

docker run -d -p 8080:80 --name nginx1 nginx
# Lancer un container Nginx sur le port 8080

docker ps
# Lister les containers en cours d’exécution

docker stop nginx1
# Arrêter un container

docker start nginx1
# Redémarrer un container

      JOUR2 commande essentielle
docker images
# Lister toutes les images disponibles localement

docker search redis
# Rechercher une image sur Docker Hub

docker pull mysql:8.0
# Télécharger une image sans l’exécuter

docker rmi mysql:8.0
# Supprimer une image

docker logs nginx1
# Voir les logs d’un container

docker exec -it nginx1 /bin/bash
# Exécuter un terminal interactif dans un container

docker run -d --name mysql1 -e MYSQL_ROOT_PASSWORD=pass -p 3306:3306 mysql:8.0
# Lancer un container MySQL avec mot de passe root

      Dockerfile et reseaux

docker build -t mon-nginx .
# Construire une image à partir d’un Dockerfile

docker run -d -p 8085:80 --name nginx-custom mon-nginx
# Lancer un container basé sur l’image créée

docker network create mon-reseau
# Créer un réseau Docker personnalisé

docker run -d --name redis1 --network mon-reseau redis
# Lancer Redis sur le réseau créé

docker run -d --name web1 --network mon-reseau nginx
# Lancer Nginx sur le même réseau

docker exec -it web1 ping redis1
# Tester la connectivité entre containers
