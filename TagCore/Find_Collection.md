# Find Collection class
The collection you get in the search result. And also you can independently create and fill a collection with components.

## find
`public`: Find tags in in result collection.
```php
/**
 * @param string $selector
 * @return $this|FindCollection
 * @throws \Exception
 */
$tag->find(string $selector);
```
## cover
`public`: A wrapper over all components of the collection.
```php
/**
 * .
 * @param $data
 * @return $this
 */
$tag->cover($data);
```
## render
`public`: Get the evaluated contents of the object.
```php
/**
 * .
 * @return string
 */
$tag->render();
```
And all the other methods that are present in [Laravel Collection]([https://laravel.com/docs/5.8/collections](https://laravel.com/docs/5.8/collections))
