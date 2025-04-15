# Allow One Function Call

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

## Ce qu'il faut retenir :

- on peut return undefined.
' on regarde simplement si la fonction a déjà été appelée avec une variable boolean.