# Filter Elements from Array

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

## Ce qu'il faut retenir

Il est important lorsqu'on fait le foreach de respecter la signature de la fonction fn. Comme celle-ci prend l'item + l'index alors on boucle sur l'item + l'index sinon certains tests peuvent ne pas passer.