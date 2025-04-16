# Function Composition

[Voir sur Leetcode](https://leetcode.com/problems/function-composition/?envType=study-plan-v2&envId=30-days-of-javascript)

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

## Explication de la solution :

- Le but est d'effectuer les opérations des fonctions du tableau functions successivement sur l'argument x passer dans la fonction de return
- D'après l'énoncé on voit que la première fonction du tableau sera la dernière opération effectuée sur x
- Pour résoudre le problème il suffit donc de :
    - parcourir le tableau de la fin au début
    - pour chaque fonction du tableau l'appliquer sur la valeur courante de x

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

## Ce qu'il faut retenir :

rien de spécial si ce n'est l'utilitée des fonctions slice(), reverse()
