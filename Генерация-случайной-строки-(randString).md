Возвращает строку указанной длины, состоящую из случайных символов. Символами могут быть буквы английского алфавита и цифры. Функция может использоваться например, для генерации пароля.

Параметры: длина строки, набор символов

    string
    randString(
     int pass_len = 10,
     pass_chars=false
    );

    echo randString(7, array(
      "abcdefghijklnmopqrstuvwxyz",
      "ABCDEFGHIJKLNMOPQRSTUVWX­YZ",
      "0123456789",
      "!@#\$%^&*()",
    ));