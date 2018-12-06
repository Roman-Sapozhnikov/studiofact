Значение bxajaxid динамическое – оно формируется для каждого компонента, и поэтому его надо узнать, перед тем как использовать. В классе CAjax есть для этого функция GetComponentID, первым параметром задаётся имя компонента, вторым – имя шаблона. Если имя шаблона не задано используется значение ".default". И в начале шаблона пишется:

    <?
    $bxajaxid = CAjax::GetComponentID('bitrix:system.auth .form', 'personal');
    ?>

После чего используется во всех нужных местах.

UPD: будет полезным использовать следующую универсальную запись:

    $bxajaxid = CAjax::GetComponentID($component->__name, $component->__template->__name);

После переезда сайта на php7 запись выше будет выглядеть:

    $bxajaxid = CAjax::GetComponentID($component->__name, $component->__template->__name, $component->arParams['AJAX_OPTION_ADDITIONAL']);