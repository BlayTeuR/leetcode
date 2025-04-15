# Array Reduce Transformation

## Description du problèmes :

Given an integer array nums, a reducer function fn, and an initial value init, return the final result obtained by executing the fn function on each element of the array, sequentially, passing in the return value from the calculation on the preceding element.

This result is achieved through the following operations: val = fn(init, nums[0]), val = fn(val, nums[1]), val = fn(val, nums[2]), ... until every element in the array has been processed. The ultimate value of val is then returned.

If the length of the array is 0, the function should return init.

Please solve it without using the built-in Array.reduce method.

## Voici la solution :

``` js
/**
 * @param {number[]} nums
 * @param {Function} fn
 * @param {number} init
 * @return {number}
 */
var reduce = function(nums, fn, init) {
    let val = init;
    nums.forEach(num => {
        val = fn(val, num);
    });
    return val;
};
```

## Explication de la solution :

- Il est également d'utiliser un for classique pour garder plus de contrôle sur l'itération.
- Pour chaque élément **num** dans **nums** on met à jour val avec fn(val, num)