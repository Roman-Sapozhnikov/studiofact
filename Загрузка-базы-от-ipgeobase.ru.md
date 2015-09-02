Используем файл: https://github.com/studiofact/commonwiki/blob/master/geoip_rucenter.php

Если не отрабатывает, пробуем вручную создать файл лога: $_SERVER["DOCUMENT_ROOT"].'/upload/ipgeobase/log/wget.log'

В таблице rucenter_ranges типы полей IP_INT_FROM и IP_INT_TO должны быть BIGINT

`ALTER TABLE rucenter_ranges MODIFY IP_INT_FROM BIGINT`

`ALTER TABLE rucenter_ranges MODIFY IP_INT_TO BIGINT`

Для определения города и записи его в сессию + показа текущего города используем компоненты:
