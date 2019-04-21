# Tag Core Methods

## hide
Add to tag `style="display: none;"`.
```php
/**  
 * @param bool $eq You can pass a boolean value as a switch when rendering.
 * @return $this  
 */
$tag->hide($eq = true);
```

## haveAndGetSelector
Get the identifier attribute if there is, if not, create a unique attribute and return the `JS Query` selector.
```php
/**  
 * @return string  
 * @throws \Exception  
 */
$tag->haveAndGetSelector();
```

## getSelector
Alias `haveAndGetSelectorID`

## haveAndGetSelectorID
Get the value of the identifier attribute if there is one, if not create a unique one and return the `JS Query` selector.
```php
/**  
 * @return string  
 * @throws \Exception  
 */
$tag->haveAndGetSelectorID();
```


## hasParent
Check if there is a parent object.
```php
/**  
 * @return bool  
 */
 $tag->hasParent();
```

## name
Set the internal name for easy access through the `_s` helper.
```php
/**  
 * @param string $name  
 * @return $this  
 */
$tag->name(string $name);
...
_s($name)->text("Hello");
```

## getObjName
Name getter
```php
/**  
 * @return string  
 */
 $tag->getObjName();
```

## getElement
Element getter
```php
/**  
 * @return string  
 */
 $tag->getElement();
```

## isElement
Checks if an item has an element.
```php
/**  
 * @return bool  
 */
 $tag->isElement();
```

## getParent
Get element parent.
```php
/**  
 * @return Tag  
 */
$tag->getParent();
```

## root
Root wrapper.
```php
/**  
 * @param \Closure $closure  
 * @return Tag 
 */
 $tag->root(\Closure $closure);
```
> Returns himself and not the parent.

## getRoot
Get the very first parent.
