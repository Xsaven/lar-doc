# Package Helpers

## last_namespace_element
Get last namespace part by level.
```php
/**  
 * @param string $namespace  
 * @param int $level  
 * @param string $delimiter  
 * @return string  
 */
last_namespace_element(string $namespace, int $level = 1, string $delimiter = "\\")
```
### Example
```php
echo last_namespace_element("\\App\\MyNamespace\\MyClass"); //MyClass
echo last_namespace_element("\\App\\MyNamespace\\MyClass", 2); //MyNamespace
echo last_namespace_element("\\App\\MyNamespace\\MyClass", 3); //App
```

## body_namespace_element
Get only namespace body.
```php
/**  
 * @param string $namespace  
 * @param int $level  
 * @param string $delimiter  
 * @return string  
 */
body_namespace_element(string $namespace, int $level = 1, string $delimiter = "\\")
```
### Example
```php
echo body_namespace_element("\\App\\MyNamespace\\MyClass"); // \App\MyNamespace
echo body_namespace_element("\\App\\MyNamespace\\MyClass", 2); // \App
```
