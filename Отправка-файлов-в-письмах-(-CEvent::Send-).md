В главном модуле 15.0.7 в функции CEvent::Send появился шестой параметр - список файлов.

    function Send($event, $lid, $arFields, $Duplicate = "Y", $message_id="", $files=array())

В $files можно указать массив, например: 

    array( "/.my_hiiden_file.txt", "/favicon.ico", "/.htaccess", "/index.php"  )

Внутри функция CFile::SaveFile проверяет имя файла на адекватность. "/.htaccess" не присылается.