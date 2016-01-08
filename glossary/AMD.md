# AMD

[AMD] (https://github.com/amdjs/amdjs-api/wiki/AMD) représente Définition module asynchrone. Il est une alternative à [JS commune (CJS)] (CommonJS.md) spécification.

L'API spécifie un mécanisme permettant de définir des modules tels que le module et ses dépendances peuvent être chargées de manière asynchrone. Cela est particulièrement bien adapté pour l'environnement du navigateur où le chargement synchrone des modules encourt performances, convivialité, débogage, et les problèmes d'accès inter-domaines.

AMD bibliothèques exposer une define` fonction globale dont l'empreinte est `

`` `js
define (MODULENAME?, [dependencyA ?, dependencyB ?, ...], la fonction (objectA, objectB, ...) {
...
    var myExportedObj = function () {...}
    retourner myExportedObj;

});
`` `

Où

- `Modulename` est un paramètre de chaîne facultatif de déclarer explicitement l'id du module courant
- `DependencyA`,` dependencyB` et ainsi de suite, sont les dépendances pour le module courant
- `Fonction (objectA, objectB) {...}` est une usine dont les arguments sont les objets exportés de chaque dépendance.
- `MyExportedObj` une valeur de retour en option (depuis un module pourrait être simplement l'ajout de méthodes à un objet existant), mais, si elle est déclarée, il serait l'objet exporté de ce module, qui d'autres modules obtiendraient si ils énumèrent` modulename` parmi leurs dépendances.

Mis à part la fonction `define` mondiale, une bibliothèque compatible AMD doit avoir une propriété` define.amd` dont la valeur est un objet. Vérification de l'existence de deux `et` define.amd` define` dans la portée globale permet un script pour vérifier qu'il est appelé à partir d'un chargeur AMD.

Des exemples de bibliothèques offrant des capacités de chargement AMD sont:

- [Demander JS] (http://requirejs.org/docs/whyamd.html) écrit par [James Burke] de Mozilla (https://github.com/jrburke/). Un des premiers à devenir largement utilisé et toujours le plus populaire. Il fournit une interopérabilité limitée avec CommonJS modules trop.
- [CurlJS] (https://github.com/cujojs/curl) partie de la [cadre CujoJS] (http://cujojs.com/). CurlJS est moins populaire que RequireJS et reçoit seulement des mises à jour de maintenance, pas de nouvelles fonctionnalités depuis 2 014.
- [Alameda] (https://github.com/requirejs/alameda) également réalisé par James Burke, il est comme RequireJS mais en utilisant promesses pour gérer les événements d'achèvement.
- [Cajon] (https://github.com/requirejs/cajon) également réalisé par James Burke, il est comme un décorateur pour RequireJS qui remplace la méthode `load` chercher dépendances à travers des appels Ajax.
- [SystemJS] (https://github.com/systemjs/systemjs) par [Guy Bedford] (https://github.com/guybedford) qui, jusqu'à il ya quelques années, était l'un des développeurs les plus actifs du plugin pour RequireJS. SystemJS peuvent charger AMD, CommonJS et ES6 modules de façon transparente et est principalement utilisé en combinaison avec [jspm] (http://jspm.io/), qui agit en tant que gestionnaire de dépendance (un peu comme [Bower] (Bower.md)) exploitant dans Github et NPM.

Toutes ces bibliothèques permettent au développeur de prévisualiser un projet whithout toute étape de la construction, en demandant les dépendances de manière asynchrone. Il ya habituellement une étape facultative (mais reccomended) construire ou regroupement pour déploie de production, afin de rapetisser le code et de minimiser le nombre de demandes en vue d'améliorer les temps de chargement. Apparemment, la venue de [HTTP2] (https://http2.github.io/) soutien dans les navigateurs et les serveurs Web devrait éliminer la nécessité pour les demandes supplémentaires lors du chargement des dépendances de manière asynchrone, éliminant ainsi la nécessité d'une étape de construction.

Autres bibliothèques qui ne peut pas charger les dépendances de façon asynchrone, mais peuvent inclure des modules AMD dans leur flux de travail de construction, sont, par exemple:

- [Webpack] (WEBPACK.md)
- [Rollup] (http://rollupjs.org/)