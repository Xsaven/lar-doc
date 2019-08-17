## Дополнительные возможности

Расширение класса компонента
```php
use Lar\Layout\Commands\GeneratorCore\EntitiesClass\ObjectDocument;

...

GenerateHelper::onGenerateDoc(function (ObjectDocument $doc) {  
  $doc->addTrait(\UIKit::class);  
});
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU1NjkyMzg0Ml19
-->