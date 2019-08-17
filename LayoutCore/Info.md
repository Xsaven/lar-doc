# Дополнительные возможности

### Расширение класса компонента док генератором.

Добавить в `ServiceProvider` следующий код:
```php
...
use Lar\Layout\Commands\GeneratorCore\EntitiesClass\ObjectDocument;
use Lar\Layout\Commands\Dump\GenerateHelper;
...
/**  
 * Bootstrap services. 
 *
 * @return void  
 * @throws \Exception  
 */
public function boot()  
{
	...
	GenerateHelper::onGenerateDoc(function (ObjectDocument $doc) {  
		  $doc->addTrait(\UIKit::class);  
	});
	...
}
...
```

### Расширение класса респонда `Respond` док генератором

Добавить в `ServiceProvider` следующий код:
```php
...
use Lar\Layout\Commands\GeneratorCore\EntitiesClass\ObjectDocument;
use Lar\Layout\Commands\Dump\GenerateRespondHelper;
...
/**  
 * Bootstrap services. 
 * 
 * @return void  
 * @throws \Exception  
 */
public function boot()  
{
	...
	GenerateRespondHelper::onGenerateDoc(function (ObjectDocument $doc) {  
		  $doc->addTrait(\UIKit::class);  
	});
	...
}
...
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU4MTUxMjE5MV19
-->