# Content Collection class

## add
`public`: Add data in to collection.
```php
/**
 * @param $value
 * @param bool $prepend
 * @return mixed
 */
$tag->add($value, $prepend = "");
```
## toTag
`public`: To tag data.
```php
/**
 * @param string $impl_simbol
 * @return string
 */
$tag->toTag($impl_simbol = "");
```
## setTag
`public`: Parent tag setter.
```php
/**
 * @param Tag|null $tag
 * @return ContentCollectionArea
 */
$tag->setTag(\Lar\Tagable\Tag $tag = "");
```

> And all the other methods that are present in [Laravel Collection](https://laravel.com/docs/5.8/collections)
