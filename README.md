### 3

- 3.a : `docker pull nginx`

- 3.b : commande : `docker image` et regarder si l'image 'nging' est bien présente

- 3.d : commande : `docker run -d -p 8080:80 -v /Users/flo/Desktop/ynov/Dev-Ops/tp1/devops-training-docker/html:/usr/share/nginx/html nginx`

- 3.e supprimer le container :

  - trouver l'id du conteneur avec la commande `docker ps`
  - stopper le conteneur `docker stop <CONTAINER_ID>`
  - supprimer le conteneur `docker rm <CONTAINER_ID>`

- 3.f : commande : `docker cp /Users/flo/Desktop/ynov/Dev-Ops/tp1/devops-training-docker/html/index.html <CONTAINER_ID>:/usr/share/nginx/html`

## 4

- 4.b :
  - j'ai build l'image docker avec la commande : `docker build -t custom-nginx`. J'ai utilisé le paramètre t pour lui donner un nom.
  - J'ai lancé cette image avec la commande `docker run -d -p 8080:80 custom-nginx`
