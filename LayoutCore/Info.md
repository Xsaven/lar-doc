## Дополнительные возможности

Расширение класса компонента док генератором.

Добавить в `ServiceProvider` следующий код:
```php
...
use Lar\Layout\Commands\GeneratorCore\EntitiesClass\ObjectDocument;
use Lar\Layout\Commands\Dump\GenerateHelper;
...
/**  
 * Bootstrap services. * * @return void  
 * @throws \Exception  
 */
public function boot()  
{

	GenerateHelper::onGenerateDoc(function (ObjectDocument $doc) {  
		  $doc->addTrait(\UIKit::class);  
	});

}
...
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMDIzMzA1NzFdfQ==
-->