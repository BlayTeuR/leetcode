# Counter II

## Description du probl�mes :

Write a function createCounter. It should accept an initial integer init. It should return an object with three functions.

The three functions are:

- increment() increases the current value by 1 and then returns it.
- decrement() reduces the current value by 1 and then returns it.
- reset() sets the current value to init and then returns it.

## Solution :

```
js
/**
 * @param {integer} init
 * @return { increment: Function, decrement: Function, reset: Function }
 */
var createCounter = function(init) {
    let base = init;
    return {
        increment: function() {
            return init += 1
        },
        decrement: function() {
            return init -= 1
        },
        reset: function(){
            init = base;
            return base;
        }
    }
};

/**
 * const counter = createCounter(5)
 * counter.increment(); // 6
 * counter.reset(); // 5
 * counter.decrement(); // 4
 */
```

Pas de chose sp�cial � retenir ici
