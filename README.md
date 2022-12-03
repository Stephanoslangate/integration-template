# IntegrationTemplate

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.1.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
## ng build --aot --build-optimizer --common-chunk --vendor-chunk --named-chunks
Cette commande permet de Compiler une application ou une bibliothèque Angular dans un répertoire de sortie nommé dist/ au niveau du chemin de sortie donné. Générez à l’aide de la compilation Ahead of Time, Active des optimisations de build avancées lors de l’utilisation de l’option 'aot' et aussi Générez un bundle distinct contenant le code utilisé sur plusieurs bundles..
## mdkir Dockerfile.
Créez un fichier vide nommé.Dockerfile à la racine
du projet, dans lequel nous allons ajouter des configurations
À l’aide d’un éditeur de texte ou d’un éditeur de code, ajoutez le contenu suivant au fichier Dockerfile :

FROM nginx:1.17.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY /dist/integration-template /usr/share/nginx/html


## mdkir nginx.conf
Créez un fichier vide nommé nginx.conf à la racine
du projet, dans lequel nous allons ajouter des configurations liées à nginx
À l’aide d’un éditeur de texte ou d’un éditeur de code, ajoutez le contenu suivant au fichier 
nginx.conf :

 events {}
          http {
              include /etc/nginx/mime.types;
          
              server {
                  listen 80;
                  server_name localhost;
                  root /usr/share/nginx/html;
                  index index.html;
          
                  location / {
                      try_files $uri $uri/ /index.html;
                  }
              }
          }
##  docker  build -t integration-template

La commande utilise le Dockerfile pour créer une nouvelle image de conteneur. Vous avez peut-être remarqué que Docker a téléchargé beaucoup de « couches ». C’est parce que vous avez indiqué au constructeur que vous vouliez partir de l’image. Mais, comme vous ne l’aviez pas sur votre machine, Docker devait télécharger l’image.docker buildnode:18-alpine

Une fois que Docker a téléchargé l’image, les instructions du fichier Docker ont été copiées dans votre application et utilisées pour installer les dépendances de votre application. La directive spécifie la commande par défaut à exécuter lors du démarrage d’un conteneur à partir de cette image.yarnCMD

Enfin, theflag marque votre image. Considérez cela simplement comme un nom lisible par l’homme pour l’image finale. Puisque vous avez nommé l’image, vous pouvez faire référence à cette image lorsque vous exécutez un conteneur.-t integration-template

Theà la fin de la commande indique à Docker qu’il doit rechercher ledans le répertoire courant..docker buildDockerfile

## docker run --name angular-app-container -d -p 80:80 integration-template

Executer cette commande pour builder l'image et demarer afin de pouvoir voir notre conteneur en marche et accéder au résultat