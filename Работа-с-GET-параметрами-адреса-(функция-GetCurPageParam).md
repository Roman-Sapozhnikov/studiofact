    <?
    // текущая страница: /ru/?id=3&s=5&d=34
    $page = $APPLICATION->GetCurPageParam("id=45", array("id", "d")); 
    // результат - /ru/index.php?id=45&s=5
    ?>