Конструкция: 

     <?$this->SetViewTarget("catalog_position");?>
            <!-- каталог (bitrix:catalog) --> //   данный код будет перемещен в контейнер "catalog_position"
    <?$this->EndViewTarget();?>

используется, если нам нужно вывести какой-то блок выше относительно заданного кода. В данном случае $this - это объект класса CBitrixComponentTemplate. 

Но, если мы попробуем использовать данную конструкцию в файле component_epilog.php, то ничего не получится. Так как $this в данном случае - уже объект класса CBitrixComponent. Чтобы поправить этот момент, необходимо использовать следующую конструкцию: 

    <?$this->__template->SetViewTarget("catalog_position");?> 
       <!-- каталог (bitrix:catalog) --> // данный код будет перемещен в контейнер "catalog_position" 
    <?$this->__template->EndViewTarget();?> 

$this->__template - в данном случае и есть наш объект класса CBitrixComponentTemplate