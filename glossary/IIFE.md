# IIFE

IIFE (pour *Immediately Invoked Function Expression* ou *Fonction Appelée Immédiatement*) est une fonction qui est appelée immédiatement après sa déclaration. Cela est très souvent utilisé pour englober le contexte (un contexte dans lequel toutes les variables et fonctions sont englobées)

Une IIFE peut être écrite avec des parenthèses d'appel (`()`) à l'intérieur de parenthèses englobantes :

```js
(function foo () {
  // [body]
}());
```

Ou avec les parenthèses d'appel à l'extérieur :

```js
(function foo () {
  // [body]
})();
```

Les exemples ci dessus sont toutes les deux appelées IIFE de (), mais il est commun de les écrire de façon anonyme (sans nom de fonction).
