# Allow One Function Call

[Voir sur Leetcode](https://leetcode.com/problems/allow-one-function-call/description/?envType=study-plan-v2&envId=30-days-of-javascript)

## Description du problème

Given a function fn, return a new function that is identical to the original function except that it ensures fn is called at most once.

- The first time the returned function is called, it should return the same result as fn.
- Every subsequent time it is called, it should return undefined.

## Solution :

``` js 
/**
 * @param {Function} fn
 * @return {Function}
 */
var once = function(fn) {
    let calls = false;
    return function(...args){
        if(!calls) {
            calls = true;
            return fn(...args);
        } else {
            return undefined;
        }
    }
};

/**
 * let fn = (a,b,c) => (a + b + c)
 * let onceFn = once(fn)
 *
 * onceFn(1,2,3); // 6
 * onceFn(2,3,6); // returns undefined without calling fn
 */

```

## Explication de la solution

- Le but de cet exercice est de créer une fonction once s'assurant que la fonction fn passer en argument de celle-ci ne puisse être appelé qu'une seule fois
- pour cela on initialise donc une variable boolean **calls** à false
- on retourne ensuite une fonction ayant comme argument la liste des arguments qui seront passé à fn ex : 1, 2, 3 ou a, b, c
- Si calls est false (premier appel) -> on retourne fn de la liste d'argument
- sinon undifined

## Ce qu'il faut retenir :

- on peut return undefined.
' on regarde simplement si la fonction a déjà été appelée avec une variable boolean.
