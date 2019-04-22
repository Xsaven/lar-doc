# Attribute Collection class

## add
`public`: Add attribute in to collection.
```php
/**
 * @param $attribute
 * @param string $value
 * @return AttributeCollectionArea
 * @throws \Exception
 */
$tag->add($attribute, $value = "");
```
## remove
`public`: Remove attribute.
```php
/**
 * @param $name
 * @return $this
 */
$tag->remove($name);
```
## toTag
`public`: Get render string data for tag.
```php
/**
 * @return string
 */
$tag->toTag();
```
## setTag
`public`: Parent tag setter.
```php
/**
 * @param Tag|null $tag
 * @return AttributeCollectionArea
 */
$tag->setTag(\Lar\Tagable\Tag $tag = "");
```

> And all the other methods that are present in [Laravel Collection](https://laravel.com/docs/5.8/collections)
