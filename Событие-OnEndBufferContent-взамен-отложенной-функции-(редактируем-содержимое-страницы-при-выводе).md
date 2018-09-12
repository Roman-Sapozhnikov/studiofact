    $GLOBALS['RENT_PARAMS'] = array('IBLOCK_ID' => 3);
    AddEventHandler('main', 'OnEndBufferContent', 'RentOrder');
    function RentOrder(&$buffer)
    {
    global $APPLICATION;
        
    if (preg_match('/#RENT_ORDER#/', $buffer)) {
        ob_start();
        $APPLICATION->IncludeComponent("studiofact:rent.order", "", 
            $GLOBALS['RENT_PARAMS'],
            false
        );

        $content = ob_get_contents();
        ob_clean();
        
        $buffer = str_replace('#RENT_ORDER#', $content, $buffer);
    }
    }

Код можно размещать как init.php так и в component_epilog.php (в зависимости от ситуации). В шаблоне ставим метку, в нашем случае #RENT_ORDER#. Она будет заменена нужным нам контентом.