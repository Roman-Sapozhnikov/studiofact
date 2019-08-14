Для корректной работы композита с содержимым, которое зависит от региона (например товары или типы цен), делаем следующее:

В файле init.php переопределяем метод, формирующий имя файла в композитном кэше.

    class CacheProvider extends Bitrix\Main\Data\StaticCacheProvider
    {
	public static function createKey()
	{
		global $USER;
		$page_name = "page";
		if(!empty($_SESSION["CITY_ID"]))
			$page_name .= "_region_".$_SESSION["CITY_ID"];

		return $page_name;
	}
	public function setUserPrivateKey(){}
	public function isCacheable()
	{
		return true;
	}
	public function getCachePrivateKey()
	{
		return self::createKey();
	}
	public function onBeforeEndBufferContent(){}
    }

В компоненте определения города (**например articul.geolocation.detect_ip/component.php**) записываем куку BITRIX_SM_PK:

    setcookie("BITRIX_SM_PK", 'page_region_'.$_SESSION["CITY_ID"], $cookie_life, "/", constant("COOKIE_DOMAIN"));

В файле **/local/php_interface/composite_first_start_cookie_fix.php** записываем куку BITRIX_SM_PK для того, чтобы при первом визите композит тоже отрабатывал (подключаем этот файл **ДО** header.php на страницах с композитом):

Пример файла с запросом в инфоблок справочника городов **[здесь](https://github.com/studiofact/commonwiki/blob/master/composite_first_start_cookie_fix.php)**

* Однако, данный метод не будет работать с отдачей файлов композитного кеша, через nginx.

