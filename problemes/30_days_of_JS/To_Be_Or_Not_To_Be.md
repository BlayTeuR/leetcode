# To Be Or Not To Be

## Voici la solution :

``` js
/**
 * @param {string} val
 * @return {Object}
 */
var expect = function(val) {
    return { // return {...} -> on return un obj
        toBe: function(test) {
            let res = true;
            if(val === test){
                return res;
            } else {
                throw new Error("Not Equal");
            }
        }, // virgule pour séparer les deux fonction dans l'objet (deux parties distinctes de l'objet return)
         notToBe: function(test) {
            let res = true;
            if(val !== test){
                return res;
            } else {
                throw new Error("Equal");
            }
        }
    } 
};

/**
 * expect(5).toBe(5); // true
 * expect(5).notToBe(5); // throws "Equal"
 */
```

## Ce qu'il faut retenir :

En JavaScript si on veut que des fonctions à l'intérieur d'autres fonctions soient accessibles depuis l'extérieur, il faut les **encapsuler dans un objet** (ou autre structure comme un tableau) et **retourner l'objet**.
