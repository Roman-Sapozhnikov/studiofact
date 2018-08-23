`**CModule::IncludeModule("iblock");** //подключаем модуль инфоблока

**$arSelect = Array("ID", "IBLOCK_ID", "NAME");** // свойства которые необходимо достать<br>
**$arFilter = Array("IBLOCK_ID"=>17, "ID"=>256);**  //фильтр<br>
**$res = CIBlockElement::GetList(Array(), $arFilter, $arSelect);** //сам запрос<br>
**while ($ar_props=$res->Fetch ()){**<br>
    **$arElement['PROPERTY']['EVENT_TYPE'] = $ar_props;**<br>
**}**
`