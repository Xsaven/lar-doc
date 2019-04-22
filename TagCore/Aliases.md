# Aliases class

Aliases tag.
 
### List of standard aliases:
| Prototype | Value | View |
|--|--|--|
| :js | javascript:void(0); | |
| :space, :nbsp | &amp;nbsp; | &nbsp; |
| :copy | &amp;copy; | &copy; |
| :reg | &amp;reg; | &reg; |  
| :euro | &amp;euro; | &euro; |
| :trade | &amp;trade; | &trade; |
| :larr | &amp;larr; | &larr; |
| :uarr | &amp;uarr; | &uarr; |
| :rarr | &amp;rarr; | &rarr; |
| :darr | &amp;darr; | &darr; |
| :spades | &amp;spades; | &spades; |
| :clubs | &amp;clubs; | &clubs; |
| :hearts | &amp;hearts; | &hearts; |
| :diams | &amp;diams; | &diams; |

## init
`public static`: Initialization library.
```php
$tag->init();
```
## getAliases
`public static`: Library aliases getter method.
```php
/**
 * @return Collection
 */
$tag->getAliases();
```
## makeAlias
`public`: Make alias.
```php
/**
 * @param $proto
 * @param $value
 * @return Collection
 */
$tag->makeAlias($proto, $value);
```

