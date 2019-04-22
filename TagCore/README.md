# About TagCore
Multifunctional core for creating and manipulating HTML tags.

## Create tag
```php
echo tag("a")->setHref("https://google.com")->setTarget("_blanck")->text("Go to Google")->render();
```
Output:
```html
<a href="https://google.com" target="_blanck">Go to Google</a>
```

## Create tag using parameters
```php
echo tag("a", ["href" => "https://google.com", "target" => "_blanck"])->text("Go to Google");
```
Output:
```html
<a href="https://google.com" target="_blanck">Go to Google</a>
```

## Create nested tag
```php
echo tag("body")->div(['container'])->a(["href" => "/"], "Go to Home")->render();
```
`div(['container'])` - If we in an array with attributes pass an attribute with a key, this property is confused with the `CSS` class.

You can also use this type of appointment:
 * `div(['.container'])` - Set CSS Class `container`
 * `div(['#my_id'])` - Set HTML ID `my_id`

Output:
```html
<body><div class="container"><a href="/">Go to Home</a></div></body>
```

## Create a component
`app/Shape/Users.php`:
```php
<?php

namespace App\Shape;

use Lar\Tagable\Tag;

class Users extends Tag
{
	/**  
	 * Tag element
	 * @var string  
	 */
	protected $element = "div";

	/**  
	 * Tag name from selector 
	 * @var string
	 */
	protected $name = "users";

	/**  
	 * Execute inner methods before render 
	 * @var array  
	 */
	public $execute = ["create_wrapper"];

	/**
	 * Execute method
	 */
	public function create_wrapper()
	{
		$this->classUserList();
		
		$users = [
			["id" => 1, "name" => "User 1"],
			["id" => 2, "name" => "User 2"],
		];
		$this->mapCollect($users, function ($row, $key, Tag $tag) {
			
			$tag->initTag("a")->setHref("/user/" + $row['id']);
			
			$tag->div(["user-number"])->text($key);
			$tag->div(["user-identifier"])->text($row['id']);
			$tag->div(["user-name"])->text($row['name']);
		});
	}
}

echo (new Users)->render();
```
Output:
```html
<div class="user-list">
	<a href="/user/1">
		<div class="user-number">0</div>
		<div class="user-identifier">1</div>
		<div class="user-name">User 1</div>
	</a>
	<a href="/user/2">
		<div class="user-number">1</div>
		<div class="user-identifier">2</div>
		<div class="user-name">User 2</div>
	</a>
</div>
```
