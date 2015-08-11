Проблема:
ломается верстка в IE, т.к. он открывает сайт в режиме совместимости.

Решение:
```php
<?php header('X-UA-Compatible: IE=edge'); ?>
```

Подробнее тут:
> http://ru.stackoverflow.com/questions/302401/%D0%A1%D0%B0%D0%B9%D1%82-%D0%B2-ie-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D1%8B%D0%B2%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B2-%D1%80%D0%B5%D0%B6%D0%B8%D0%BC%D0%B5-%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D0%B8