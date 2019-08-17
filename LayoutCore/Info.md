## Дополнительные возможности

Расширение класса компонента.

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
eyJoaXN0b3J5IjpbNTM4MTc2NzQ5XX0=
-->