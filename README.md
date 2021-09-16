# docker-user-test

Test des utilisateurs dans un conteneur.

```shell
env $UID=$(id -u):$(id -g) docker-compose build
env $UID=$(id -u):$(id -g) docker-compose run --rm docker-user-test
```

Remarque: `Dockerfile` n'a pas besoin des variables d'environnement. La première commande affichera un avertissement.

Une solution alternative serait de ne pas définir `user` dans `docker-compose.yaml`, et de le passer en paramètre du `docker-compose run` ainsi :

```shell
docker-compose build
docker-compose run --user=$(id -u):$(id -g) --rm docker-user-test
```
