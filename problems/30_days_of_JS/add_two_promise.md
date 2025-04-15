# Add two promise

## Voici la solution :

``` js
/**
 * @param {Promise} promise1
 * @param {Promise} promise2
 * @return {Promise}
 */
var addTwoPromises = async function(promise1, promise2) {
    let promise1V, promise2V;
    promise1V = await promise1;
    promise2V = await promise2;
    return promise1V + promise2V;
 };

/**
 * addTwoPromises(Promise.resolve(2), Promise.resolve(2))
 *   .then(console.log); // 4
 */

## Ce qu'il faut retenir

### Pourquoi cela fonctionne

- Une fonction avec le mot clef **async** retourne une promesse (promise)
- le mot clef **await** permet d'attendre que les promesses soit résolue

### Définition rapide des concepts

#### Promise
Une promesse est un objet en JavaScript qui représente une valeur qui peut être disponible maintenant, plus tard ou jamais. Elle a trois états :

- pending (en attente)
- fulfilled (résolue avec une valeur)
- rejected (échouée avec une erreur)

#### async
Une fonction marquée async retourne automatiquement une promesse. Cela permet d'utiliser await à l'intérieur.

####await
await suspend l'exécution de la fonction async jusqu'à ce que la promesse soit résolue, puis retourne la valeur résolue. Il permet d’écrire du code asynchrone de manière synchronisée et plus lisible.




