# Browserify

[Browserify](http://browserify.org/) est un outil vous permettant d'utiliser la fonction [require](https://nodejs.org/api/modules.html) de [Node.js](NODEJS.md) côté navigateur en rassemblant toutes les dépendences requises.

L'idée derrière Browserify est de rendre possible l'utilisation de librairies existantes de [npm](NPM.md) même en écrivant du code pour le côté client. Pour ce faire, il parcours le code, appelle les dépendences requises, et crée un seul et même fichier contenant tout : les dépendences ainsi que le code qui les utilise.