# Aliases class

Aliases tag.

### List of standard aliases:
| Prototype | Value | View |
|--|--|--|
| :js | javascript:void(0); | |
| :space, :nbsp | \&nbsp; | &nbsp; |
| :copy | \&copy; | &copy; |
| :reg | \&reg; | &reg; |  
| :euro | \&euro; | &euro; |
| :trade | \&trade; | &trade; |
| :larr | \&larr; | &larr; |
| :uarr | \&uarr; | &uarr; |
| :rarr | \&rarr; | &rarr; |
| :darr | \&darr; | &darr; |
| :spades | \&spades; | &spades; |
| :clubs | \&clubs; | &clubs; |
| :hearts | \&hearts; | &hearts; |
| :diams | \&diams; | &diams; |

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

