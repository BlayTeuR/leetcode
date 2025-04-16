# Filter Elements from Array

[🔗 Voir sur LeetCode](https://leetcode.com/problems/apply-transform-over-each-element-in-array/description/?envType=study-plan-v2&envId=30-days-of-javascript)

## Description du problèmes :

Given an integer array arr and a filtering function fn, return a filtered array filteredArr.

The fn function takes one or two arguments:

- arr[i] - number from the arr
- i - index of arr[i]

filteredArr should only contain the elements from the arr for which the expression fn(arr[i], i) evaluates to a truthy value. A truthy value is a value where Boolean(value) returns true.

Please solve it without the built-in Array.filter method.

## Voici la solution :

``` js
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var filter = function(arr, fn) {
    let res = [];
    arr.forEach((item, i) => {
        if(fn(item, i)) res.push(item);
    });
    return res;
};
```

## Explication de la solution

- on parcourt le tableau de nombre arr
- pour chaque valeur du tableau arr on crée une variable val égale à la sortie de la fonction fn ayant comme paramètre la valeur arr[i] soit la valeur courante du tableau arr
- si la varirable est bien du type number alors on ajoute la variable val au tableau résultat res

