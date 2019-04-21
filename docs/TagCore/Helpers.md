# Package Helpers

## is_tag
Check whether the text is a true HTML tag.
```php
/**
 * @param string $tag
 * @return bool  
 */
is_tag($tag);
```
### Example
```php
var_dump(
	is_tag("a"), 
	is_tag("test")
);
//true, false
```

## is_tag_closing
Check is closing tag or whole.
```php
/**
 * @param string $tag
 * @return bool  
 */
is_tag_closing($tag);
```
### Example
```php
var_dump(
	is_tag_closing("a"), 
	is_tag_closing("test"), 
	is_tag_closing("img")
);
//true, false, false
```
## tag
Access to the object tag.
```php
/**  
 * @param $element  
 * @param $attributes  
 * @return \Lar\Tagable\Tag  
 * @throws Exception  
 */
tag("a", ["href" => "http://google.com"])->text("Go to Google");
```

## _s
Select the created tag.
```php
/**  
 * @param mixed|string  
 * @return \Lar\Tagable\Core\FindCollection|\Lar\Layout\LarDoc  
 * @throws Exception  
 */
 _s("name"); //Find by internal component name (Recommended for use).
 _s("body"); //Find by tag name.
 _s(".class"); //Find by class name.
 _s("#my_id"); //Find by id.
 _s("[href]"); //Find all tags with the "href" attribute.
 _s("[href=http://google.com]"); //Find all the tags with the attribute "href". which matches the text with the desired one.
 _s("[href**google]"); //Find all the tags with the attribute "href" which in the value has the same word with the desired one. Symbol aliases: "~=", "=~", "*=", "=*", "**".
 _s("[href>>http://]"); //Find all tags with the "href" attribute, which in the value begins with the search text. Symbol aliases: "|=", "=|", "^=", "=^", ">>".
 _s("[href<<.com]"); //Find all the tags with the "href" attribute, which in value ends with the desired text. Symbol aliases: "$=", "=$", "<<".
 _s("[href@=^[a-z]$]"); //Find all tags with the "shref" attribute in which the value is validated by regular degeneration.
```

## var_export_array
Convert array to `PHP` entity.
```php
/**  
 * @param array $data Convertible array
 * @param bool $compress 
 * @param int $max_val  
 * @param int $level  
 * @return string  
 */
 var_export_array([]);
```

### Example
```php
$etity = var_export_array([
	"id" => 1,
	"name" => "User"
]);

file_put_contents("file.php", "<?php\n\nreturn {$etity};");
```
file.php:
```php
<?php

return [
	"id" => 1,
	"name" => "User"
];
```

## i_code
Light text PHP scripting.
```php
i_code("...");
```

### Example
```php
$text = "{trans:date.today} {date:Y-m-d H:i:s}."
echo i_code($text);
```
output:
```
Today a 2019-04-19 23:10:57
```

## sslEnc
Encrypt data with SSL.
```php
/**  
 * @param $data  
 * @param null $pass  
 * @return string  
 */
sslEnc($data, $pass = null);
```

## sslDec
Decrypt data using SSL.
```php
/**  
 * @param $data  
 * @param null $pass  
 * @return string  
 */
 sslDec($data, $pass = null);
```

## ssl_encrypt
Encrypt data with SSL key application key. Encryption takes place in several stages. Returns Base64.
```php
/**  
 * @param $data  
 * @return string  
 */
 ssl_encrypt($data);
```

## ssl_decrypt
Decrypt data with SSL key application key.
```php
/**  
 * @param $data  
 * @return bool|string  
 */
 ssl_decrypt($data);
```

## is_json
```php
/**  
 * @param $string  
 * @param bool $return_data  
 * @return bool|mixed  
 */
 is_json($string, $return_data = false);
```
