# To Be Or Not To Be

[🔗 Voir sur LeetCode](https://leetcode.com/problems/to-be-or-not-to-be/description/?envType=study-plan-v2&envId=30-days-of-javascript)

## Enoncé : 

Write a function expect that helps developers test their code. It should take in any value val and return an object with the following two functions.

- toBe(val) accepts another value and returns true if the two values === each other. If they are not equal, it should throw an error "Not Equal".
- notToBe(val) accepts another value and returns true if the two values !== each other. If they are equal, it should throw an error "Equal".

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

## Explication :

La fonction expect(val) retourne un objet contenant deux méthodes :
- toBe(test) vérifie si val === test. Si c'est vrai, elle retourne true, sinon elle lève une erreur avec le message "Not Equal".
- notToBe(test) vérifie si val !== test. Si c'est vrai, elle retourne true, sinon elle lève une erreur avec le message "Equal".
Cela imite le comportement de certaines fonctions d’assertion dans les frameworks de test, comme expect en Jest.

## Ce qu'il faut retenir :

En JavaScript si on veut que des fonctions à l'intérieur d'autres fonctions soient accessibles depuis l'extérieur, il faut les **encapsuler dans un objet** (ou autre structure comme un tableau) et **retourner l'objet**.
