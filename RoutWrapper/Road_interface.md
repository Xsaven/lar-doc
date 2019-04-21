# Road interface

The class `Lar\Roads\Road` is the so-called collection of global routes.

## add
Add an object to the collection.
```php
/**  
 * @param string $road  
 * @return bool  
 */
 add(string $road);
```
Returns `true` if there was already a similar object in the collection,` false` if not.
### Example
```php
use Lar\Roads\Road;

Road::add(\Routes\UserPanel::class);
```
