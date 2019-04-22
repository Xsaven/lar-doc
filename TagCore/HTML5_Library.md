# HTML5 Library class
This extensible library is the main collection of HTML data.

## init
`public static`: Initialization library.
```php
$tag->init();
```
## getTags
`public static`: Library tags getter method.
```php
/**
 * @return Collection
 */
$tag->getTags();
```
## getAttributes
`public static`: Library tag attribute getter method.
```php
/**
 * @return Collection
 */
$tag->getAttributes();
```
## getEvents
`public static`: Library tag event getter method.
```php
/**
 * @return Collection
 */
$tag->getEvents();
```
## addTag
`public static`:  Add tag in to default HTML5 list.
```php
/**
 * @param $name
 * @param int $closed
 * @return Collection
 */
$tag->addTag($name, $closed = 1);
```
## addAttribute
`public static`: Add attribute in to default HTML5 list.
```php
/**
 * @param $name
 * @param array $belongs_to
 * @return Collection
 */
$tag->addAttribute($name, $belongs_to = ["*"]);
```
## addEvent
`public static`: Add event name in to default HTML5 list.
```php
/**
 * @param $name
 * @return Collection
 */
$tag->addEvent($name);
```

