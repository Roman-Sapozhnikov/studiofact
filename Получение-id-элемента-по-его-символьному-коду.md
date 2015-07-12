    CIBlockFindTools::GetElementID($element_id, $element_code, $section_id, $section_code, $arFilter)
    // $element_id - видимо для дураков :), но у битрикса такого хватает...
    // $element_code - символьный код элемента, например "super_element"
    // $section_id - ID секции в которой лежит элемент
    // $section_code - символьный код секции в которой лежит элемент
    // $arFilter - массив дополнительных свойств для фильтрации

    <? // пример использования
    $objFindTools = new CIBlockFindTools();
    $elementID = $objFindTools->GetElementID(false, "super_element", false, "super_section", array("IBLOCK_ID" => 1));
    // метод возвращает ID элемента, если найдет его, и 0, если элемент не будет найден.
    ?>