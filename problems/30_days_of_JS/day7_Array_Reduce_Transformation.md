# Array Reduce Transformation

[Voir sur LeetCode](https://leetcode.com/problems/array-reduce-transformation/description/?envType=study-plan-v2&envId=30-days-of-javascript)

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

- On initialise une variable val avec la valeur init, qui représente l'accumulateur de notre réduction.
- Ensuite, on parcourt le tableau nums avec forEach.
- Pour chaque élément num du tableau, on applique la fonction fn avec en paramètres l'accumulateur courant val et la valeur num, et on met à jour val.
- À la fin de la boucle, val contient le résultat final de la réduction, qu'on retourne.

Ce comportement imite celui de la méthode native Array.prototype.reduce.

### Remarque
- Il est également juste d'utiliser un for classique pour garder plus de contrôle sur l'itération.
- Pour chaque élément **num** dans **nums** on met à jour val avec fn(val, num)

  ## Ce qu'il faut retenir :

- Utilisation d'une valeur initiale : Dans un processus de réduction, il est essentiel de commencer avec une valeur initiale (ici init) qui sert de point de départ pour l'accumulation ou la transformation des valeurs successives du tableau.
- Application d'une fonction à chaque élément : La méthode reduce permet d'appliquer une fonction de réduction sur tous les éléments d'un tableau. Ici, nous utilisons une logique similaire en appliquant la fonction fn à chaque élément du tableau pour accumuler le résultat.
- Fonction forEach comme alternative :
    - forEach est une méthode qui permet de parcourir chaque élément d'un tableau et d'appliquer une fonction pour chaque    élément.
    - Contrairement à d'autres méthodes comme map ou filter, forEach ne retourne rien mais effectue une opération à chaque itération.

- Détails du fonctionnement de forEach :
    - La méthode prend une fonction de callback comme argument.
    - Cette fonction est exécutée pour chaque élément du tableau, où l'élément actuel est passé en argument, ainsi que l'index et le tableau d'origine.
- Elle ne modifie pas le tableau d'origine et ne retourne rien (c'est pourquoi nous utilisons val comme accumulateur ici).
- Comment forEach aide à la réduction : Bien que forEach ne retourne pas de valeur, il nous permet d'itérer facilement sur le tableau et de modifier l'état externe (comme l'accumulateur val dans notre solution). C'est une façon simple et lisible de réaliser des opérations sur chaque élément, bien que reduce soit une méthode plus adaptée pour des réductions complexes, car elle retourne directement la valeur finale.
