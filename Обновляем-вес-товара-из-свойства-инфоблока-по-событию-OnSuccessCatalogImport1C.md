OnSuccessCatalogImport1C - Вызывается после успешного импорта товаров из 1с. Событие компонента catalog.import.1c

    AddEventHandler("catalog", "OnSuccessCatalogImport1C", "upDateWiegth");
    function upDateWiegth()
    {
  	if (CModule::IncludeModule("catalog")) {
		$db_res = CCatalogProduct::GetList(array(),array(),false, false);
		while ($ar_res = $db_res->GetNext())
		{
			$arSelect = Array("ID", "PROPERTY_VES_KG"); //получаем вес товара из свойства
			$arFilter = Array("ID"=>$ar_res["ID"]);
			$res = CIBlockElement::GetList(Array(), $arFilter, false, false, $arSelect);
				while($ob = $res->GetNext())
					{
						if ($ob['PROPERTY_VES_KG_VALUE']) {
							$wightResult = $ob['PROPERTY_VES_KG_VALUE']*1000;
							if	(CCatalogProduct::Update($ar_res["ID"], array ("WEIGHT" => $wightResult)) == true) {
							echo "Вес товара ".$ar_res["ID"]." обновлен";
							} else {
							echo "Произошла ошибка при обновление веса товара";
							}
						}
					}


		}
	}
    }