# Create Hello Wolrd Function

lien du problème et énoncé : https://leetcode.com/problems/create-hello-world-function/description/?envType=study-plan-v2&envId=30-days-of-javascript

## Voici la solution :


**Hello World function :**
```js
/**
 * @return {Function}
 */
var createHelloWorld = function() {
    
    return function(...args) {
        return "Hello World";
    }
};

/**
 * const f = createHelloWorld();
 * f(); // "Hello World"
 */ 
```

## Ce qu'il faut retenir

En JavaScript, la syntaxe ...args utilisée en tant que paramètre de fonction s’appelle le paramètre rest (ou « rest parameter » en anglais). Cela signifie que args va représenter un tableau contenant tous les arguments supplémentaires passés à la fonction, au-delà des paramètres nommés (s’il y en a).

Par exemple :

```js
function exemple(param1, ...args) {
  console.log(param1); // Affiche la valeur du premier argument
  console.log(args);   // Affiche un tableau contenant tous les autres arguments
}

exemple(1, 2, 3, 4);
// param1 = 1
// args = [2, 3, 4]
```


