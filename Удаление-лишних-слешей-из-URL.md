```php
$subject = $_SERVER["REQUEST_URI"];
$pattern = '/\/\/+/';
$countReplace = 0;
$replaced_url = preg_replace($pattern, '/', $subject, -1, $countReplace);
if ($countReplace > 0)
	LocalRedirect($replaced_url, false, '301 Moved Permanently');
```