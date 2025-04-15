# Counter

[🔗 Voir sur LeetCode](https://leetcode.com/problems/counter/?envType=study-plan-v2&envId=30-days-of-javascript)

## Enoncé

Given an integer n, return a counter function. This counter function initially returns n and then returns 1 more than the previous value every subsequent time it is called (n, n + 1, n + 2, etc).

## Voici la solution :

``` js
 /**
 * @param {number} n
 * @return {Function} counter
 */
var createCounter = function(n) {
    return function() {
        return n++;
    };
};

/** 
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */ 
```
## Ce qu'il faut retenir :

Il est important dans cette exercice ce comprendre le principe de closure, dans ce cas la fonction **inner** à accès au paramètres et déclaration de la fonction *outer*.

Aussi on note que **n++** return n puis incrémente, **++n ou n += 1** incrémente puis return n.
