# Road interface

Класс `Lar\Roads\Road` эта так называемая коллекция глобальных маршрутов.

## add
Добавить объект в коллекцию.
```php
/**  
 * @param string $road  
 * @return bool  
 */
 add(string $road);
```
Возвращает `true` если в коллекции уже был подобный объект, `false` если нет.
### Example
```php
use Lar\Roads\Road;

Road::add(\Routes\UserPanel::class);
```
