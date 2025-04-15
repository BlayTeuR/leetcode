# Return Length of Arguments

## Description du problèmes

``` js
/**
 * @param {...(null|boolean|number|string|Array|Object)} args
 * @return {number}
 */
var argumentsLength = function(...args) {
    return args.length;
};

/**
 * argumentsLength(1, 2, 3); // 3
 */
```

## Ce qu'il faut retenir :

La fonction en elle même n'est pas intéressant, ce qui est intéressant ici est (...args). Ce param veut dire **rest parameters** et représente un tableau contenant tous les arguments passés à la fonction.

### Voici différents exemples d'utilisations :

``` js
function sum(...numbers) {
    return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
console.log(sum(5, 10)); // 15
console.log(sum()); // 0

```

``` js
function greet(greeting, ...names) {
    return `${greeting} ${names.join(', ')}`;
}

console.log(greet("Hello", "Alice", "Bob", "Charlie"));
// "Hello Alice, Bob, Charlie"

```