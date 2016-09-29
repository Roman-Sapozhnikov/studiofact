В .htaccess меняем/добавляем строки:
```php
#RewriteCond %{REQUEST_FILENAME} !/bitrix/urlrewrite.php$
#RewriteRule ^(.*)$ /bitrix/urlrewrite.php [L]
RewriteRule ^(.*)$ /filterRewrite.php [L]
```

В файле /filterRewrite.php пишем:
```php
<?php
include_once("rewriter.php");
include("bitrix/urlrewrite.php");
```

В файле /rewriter.php пишем:
```php
    <?php
    if ($_SERVER['REQUEST_URI']=='/урл для адресной строки браузера/'){
	    $str = 'строка GET параметров, например, для умного фильтра';
	    $_SERVER['REQUEST_URI'] = 'урл страницы, с которой берем содержимое/?'.$str;
	    parse_str($str, $_GET);
    }
```

Пример для каталога и умного фильтра:
```php
    <?php
    if ($_SERVER['REQUEST_URI']=='/megakotly/'){
	    $str = 'arrFilter_19_MIN=4&arrFilter_19_MAX=1850&arrFilter_P1_MIN=25972&arrFilter_P1_MAX=1535345&set_filter=%CF%EE%EA%E0%E7%E0%F2%FC&arrFilter_18_1184046869=Y&arrFilter_20_1584466506=Y&arrFilter_21_1825697644=Y&arrFilter_23_41440068=Y&arrFilter_26_851713956=Y';
	    $_SERVER['REQUEST_URI'] = '/catalog/kotly/?'.$str;
	    parse_str($str, $_GET);
    }
```