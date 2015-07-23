1. Информация сохраняется в таблице b_sale_basket. В поле SUBSCRIBE устанавливается флаг подписки на товар.
2. Если товар появится в наличии, то будет отправлено уведомление. За отправку уведомления отвечает функция CAllSaleBasket::ProductSubscribe, она вызывается по событию OnProductUpdate или OnBeforeProductUpdate.

Класс здесь /bitrix/modules/sale/general/basket.php:class CAllSaleBasket