# Apply Transform Over Each Element in Array

[🔗 Voir sur LeetCode](https://leetcode.com/problems/apply-transform-over-each-element-in-array/description/?envType=study-plan-v2&envId=30-days-of-javascript)

## Enoncé :

Given an integer array arr and a mapping function fn, return a new array with a transformation applied to each element.
The returned array should be created such that returnedArray[i] = fn(arr[i], i).
Please solve it without the built-in Array.map method.

## Voici la solution :

``` js
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var map = function(arr, fn) {
    let res = [];
    for(let i = 0; i < arr.length; i++){
        let val = fn(arr[i]);
        if(typeof val === "number") res.push(val);
    }
    return res;
};
```

## Explication :

- La fonction map prend en entrée :
   - un tableau arr
   - une fonction fn à appliquer à chaque élément du tableau.
- On parcourt le tableau avec une boucle for.
- Pour chaque élément, on applique fn à l'élément courant (fn(arr[i])).
- Si le résultat est un nombre (typeof val === "number"), on l'ajoute au tableau res.
- À la fin, on retourne le tableau res.

## Ce qu'il faut retenir :

- Cette fonction reproduit le comportement de Array.prototype.map() en JavaScript.
- Ajoute une vérification de type pour ne conserver que les résultats numériques.
- Pratique pour s'assurer que la fonction fn ne retourne pas de valeurs inattendues (comme undefined, null, ou string).

