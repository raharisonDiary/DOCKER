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
