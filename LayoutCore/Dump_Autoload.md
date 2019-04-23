# Dump Autoload
This class command is executed every time when calling the `composer update`,` composer install`, `composer dump-autoload` method.

By default, the team performs 3 artists:
| Исполнитель | Описание |
|--|--|
| GenerateHelper | Generates PHP doc for autocomplete. |
| GenerateBladeHelpers | Generates autocomplete for Blade (PhpStorm only) |
| InjectorClear | Checks all separately connected components to the Tag and Layout. |

## Create executor
`/app/Dump/MyDumper.php`:
```php
<?php

namespace App\Dump;

use Lar\Layout\Commands\Dump\DumpExecute;
use Illuminate\Console\Command;

class MyDumper implements DumpExecute
{
	/**  
	 * Handle call method
	 * @param Command $command  
	 * @return mixed  
	 */
	public function handle(Command $command)  
	{  
		... 
	}
}
```

## Add in to execute

```php
<?php

use Lar\Layout\Commands\HeaderDumpUpdate;
use App\Dump\MyDumper;

HeaderDumpUpdate::addToExecute(MyDumper::class);
```
