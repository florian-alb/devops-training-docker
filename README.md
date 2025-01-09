### 3️⃣

- 3.a : `docker pull nginx`

- 3.b : commande : `docker image` et regarder si l'image 'nging' est bien présente

- 3.d : commande : `docker run -d -p 8080:80 -v /Users/flo/Desktop/ynov/Dev-Ops/tp1/devops-training-docker/html:/usr/share/nginx/html nginx`

- 3.e supprimer le container :

  - trouver l'id du conteneur avec la commande `docker ps`
  - stopper le conteneur `docker stop <CONTAINER_ID>`
  - supprimer le conteneur `docker rm <CONTAINER_ID>`

- 3.f : commande : `docker cp /Users/flo/Desktop/ynov/Dev-Ops/tp1/devops-training-docker/html/index.html <CONTAINER_ID>:/usr/share/nginx/html`

## 4️⃣

- 4.b :

  - j'ai build l'image docker avec la commande : `docker build -t custom-nginx`. J'ai utilisé le paramètre t pour lui donner un nom.
  - J'ai lancé cette image avec la commande `docker run -d -p 8080:80 custom-nginx`

- 4.c :

##### Volume Mount (-v)

**Avantages** :

- Idéal pour le développement.
- Pas besoin de reconstruire l'image.
- Permet de tester facilement des changements dans les fichiers locaux.

**Inconvénients** :

- Moins portable : nécessite des fichiers locaux.

##### Copy (Dockerfile)

**Avantages** :

- Image autonome et immuable, parfaite pour la production.
- Plus facile à partager et distribuer (aucune dépendance externe).

**Inconvénients** :

- Requiert une reconstruction à chaque modification de fichier.
- Moins flexible pour le développement rapide.

## 5️⃣

- 5.a: commandes :

  - mysql `docker pull mysql`
  - phpmyadmin `docker pull phpmyadmin`

- 5.b: commandes:

  - creation d'un network : `docker network create my-network`
  - mysql: `docker run -d --name mysql-container --network my-network -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=mydb -p 3306:3306 mysql`
  - phpmyadmin : `docker run -d --name phpmyadmin-container --network my-network -e PMA_HOST=mysql-container -e PMA_HOST=mysql-container -p 8080:80 phpmyadmin`

  Arguments :

  - `--name` : nom du container
  - `-e` : varialbes d'environnement
  - `--network`: nom du network crée

## 6️⃣

- 6.a :
  - `docker run` : Permet de lancer un conteneur à la fois, avec des options en ligne de commande pour définir les configurations (ports, volumes, réseaux, variables d'environnement, etc.).
  - **Docker compose** :
    - Outil qui permet de définir et de gérer des applications multi-conteneurs avec un fichier docker-compose.yml.
    - Centralise la configuration des conteneurs (réseaux, volumes, dépendances, etc.).
    - Avec une seule commande (docker-compose up), tous les conteneurs définis dans le fichier YML sont lancés.
