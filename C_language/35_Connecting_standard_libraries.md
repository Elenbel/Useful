 ### Подключение стандартных библиотек в С ###

В языке Си не очень много стандартных библиотек. В частности, **не существет стандартной библиотеки по работе с графикой**, 
о чем часто плачут школьники.

В данном списке указаны почти все стандартные библиотеки (исключены появившиеся со стандартом С99 и позже). Самые важные 
библиотеки выделены жирным.

Подключение осуществляется включением в начало файла строки
```c
#include <library.h>
```
Где *library.h* — соответствующая библиотека.

#### Ввод-вывод и стандартные функции ####

<table>
    <tr>
        <th align="center">stdio.h</th>
        <th align="left">Библиотека ввода-вывода.</th>
    </tr>
    <tr>
        <td align="center">stdlib.h</td>
        <td align="left">Собственно, стандартная библиотека Си. Содержит очень много полезных функций.</td>
    </tr>
</table>

#### Математическая библиотека и спутники ####

<table>
    <tr>
        <th align="center">math.h</th>
        <th align="left">Математическая библиотека.</th>
    </tr>
    <tr>
        <td align="center">limits.h</td>
        <td align="left">Содержит платформо-зависимые константы лимитов целых чисел. В частности: INT_MAX, LONG_MAX и т.п.</td>
    </tr>
    <tr>
        <td align="center">float.h</td>
        <td align="left">Содержит платформо-зависимые константы лимитов чисел с плавающей точкой.</td>
    </tr>
</table>

#### Работа с текстом ####

<table>
    <tr>
        <th align="center">string.h</th>
        <th align="left">Работа с Си-строками (массивами символов).</th>
    </tr>
    <tr>
        <td align="center">ctype.h</td>
        <td align="left">Работа с символами (посимвольно).</td>
    </tr>
    <tr>
        <td align="center">wchar.h</td>
        <td align="left">Поддержка работы со строками в Unicode (UTF-16 или UTF-32 в зависимости от реализации).</td>
    </tr>
    <tr>
        <td align="center">wctype.h</td>
        <td align="left">Работа с символами (посимвольно) для Unicode.</td>
    </tr>
    <tr>
        <td align="center">locale.h</td>
        <td align="left">Для поддержки локализации (национальных особенностей) при работе с датами, стоками, символами и т.п.</td>
    </tr>
    <tr>
        <td align="center">time.h</td>
        <td align="left">Функции по работе с датами и временем, в том числе текущим.</td>
    </tr>
</table>

#### Прочие библиотеки ####

<table>
    <tr>
        <th align="center">assert.h</th>
        <th align="left">Определяет макрос assert, необходимый для отладки программы.</th>
    </tr>
    <tr>
        <td align="center">errno.h</td>
        <td align="left">Определяет макрос errno, необходимый для получения кода ошибки, произошедшей в стандартной функции.</td>
    </tr>
    <tr>
        <td align="center">signal.h</td>
        <td align="left">Установка обработчиков и вызов сигналов.</td>
    </tr>
    <tr>
        <td align="center">stdarg.h</td>
        <td align="left">Поддержка работы функций с эллипсисом.</td>
    </tr>
    <tr>
        <td align="center">iso646.h</td>
        <td align="left">Для любителей писать and вместо && и or вместо ||.</td>
    </tr>
</table>
