Для этого достаточно перезаписать две битриксовые функции:
```js
BX.showWait = function(node, msg) {
	// своя кастомная функция
};
BX.closeWait = function(node, obMsg) {
	// своя кастомная функция
};
```

Также можно глобально повесить свои функции на все AJAX-запросы, вызванные через Jquery (только через jquery!!!).
```js
$( document ).ajaxSend(function() {
	// своя кастомная функция
});
$( document ).ajaxStop(function() {
	// своя кастомная функция
});
```