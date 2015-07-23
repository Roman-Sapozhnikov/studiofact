В файле template.php пишем:

    <script>
	BX.message({
		TEMPLATE_PATH: '<? echo $this->GetFolder(); ?>'
	});
    </script>

И в файле script.js получаем этот путь:

     BX.message('TEMPLATE_PATH');