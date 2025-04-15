# Function Composition

## Description du problème :

Given an array of functions [f1, f2, f3, ..., fn], return a new function fn that is the function composition of the array of functions.

The function composition of [f(x), g(x), h(x)] is fn(x) = f(g(h(x))).

The function composition of an empty list of functions is the identity function f(x) = x.

You may assume each function in the array accepts one integer as input and returns one integer as output.

## Solution du problèmes :

``` js
/**
 * @param {Function[]} functions
 * @return {Function}
 */
var compose = function(functions) {
    
    return function(x) {
        for(let i = functions.length - 1; i >= 0; i--){
            x = functions[i](x);
        }
        return x;
    }
};

/**
 * const fn = compose([x => x + 1, x => 2 * x])
 * fn(4) // 9
 */
```

## Ce qu'il faut retenir :

Faire attention au fait qu'on évalue les fonctions de la droite vers la gauche on commence donc à i = function.length - 1.

### Implémentation avec le forEach

``` js
var compose = function(functions) {
    return function(x) {
        functions.slice().reverse().forEach(fn => {
            x = fn(x);
        });
        return x;
    };
};
```

- **slice()** crée une copie du tableau (évite de modifier l'original).
- **reverse()** inverse l'ordre des fonctions pour les appliquer du dernier au premier, elle joue donc le même rôle que la partie : **let i = functions.length - 1; i >= 0; i--** du premier code