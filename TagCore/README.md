# About TagCore
Multifunctional core for creating and manipulating HTML tags.

## Example 1
```php
echo tag("a")->setHref("https://google.com")->setTarget("_blanck")->text("Go to Google")->render();
```
Output:
```html
<a href="https://google.com" target="_blanck">Go to Google</a>
```

## Example 2
```php
echo tag("a", ["href" => "https://google.com", "target" => "_blanck"])->text("Go to Google");
```
Output:
```html
<a href="https://google.com" target="_blanck">Go to Google</a>
```

## Example 3
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
