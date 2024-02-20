### Математические функции в С ###

Математические функции описаны в математической библиотеке Си, а их заголовки находятся в заголовочном файле **math.h**. 
Для его подключения нужно вставить в начало программы:
```c
#include <math.h>
```
Все математические функции принимают в качестве аргументов и возвращают числа с плавающей точкой двойной точности **double**.

#### Функции по работе со степенями числа ####

<table>
    <tr>
        <th align="center">Функция</th>
        <th align="center">Описание функции</th>
    </tr>
    <tr>
        <td align="center">double pow (double x, double y);</td>
        <td align="left">$x^{y}$ — возводит число х в степень y.</td>
    </tr>
    <tr>
        <td align="center">double sqrt (double x);</td>
        <td align="left">$\sqrt{x}$ — квадратный корень (square root) из положительного числа х. Для отрицательных чисел возвращает константу NAN.</td>
    </tr>
    <tr>
        <td align="center">double exp (double x);</td>
        <td align="left">$e^{x}$, где e = 2.718281828459045…</td>
    </tr>
    <tr>
        <td align="center">double log (double x);</td>
        <td align="left">$ln_{x}$ — натуральный логарифм аргумента х.</td>
    </tr>
    <tr>
        <td align="center">double log10 (double x);</td>
        <td align="left">$log_{10}x$ — десятичный логарифм аргумента х.</td>
    </tr>
</table>
Для вычисления логарифма по другому основанию можно использовать математическую формулу:
<p align="center">$log_{y}x$ = $ln_{x}$ / $ln_{y}$</p>

#### Тригонометрические функции ####

<table>
    <tr>
        <th align="center">Функция</th>
        <th align="center">Описание функции</th>
    </tr>
    <tr>
        <td align="center">double sin (double x);</td>
        <td align="left">$sin x$ — синус аргумента х</td>
    </tr>
    <tr>
        <td align="center">double cos (double x);</td>
        <td align="left">$cos x$ — косинус аргумента х</td>
    </tr>
    <tr>
        <td align="center">double tan (double x);</td>
        <td align="left">$tan x$ — тангенс аргумента х</td>
    </tr>
    <tr>
        <td align="center">double asin (double x);</td>
        <td align="left">$arcsin x$ — главное значение арксинуса х. Для х из интервала [-1 ; +1] возвращает значение в 
          радианах из интервала [- $\pi$ / 2; + $\pi$ / 2]. Для остальных возвращает константу NAN.
        </td>
    </tr>
    <tr>
        <td align="center">double acos (double x);</td>
        <td align="left">$arccos x$ — главное значение арккосинуса х. Для х из интервала [-1 ; +1] возвращает значение в 
          радианах из интервала [0; $\pi$ ]. Для остальных возвращает константу NAN.
        </td>
    </tr>
    <tr>
        <td align="center">double atan (double x);</td>
        <td align="left">$arctan x$ — главное значение арктангенса х. Определена для всех чисел.</td>
    </tr>
</table>
Значения углов задаются в **радианах**.

***Замечание***. **Константа  в стандарте языка Си не определена**. В разных компиляторах (в частности, в POSIX совместимых) принята 
константа **M_PI**, но во многих случаях Пи придется описывать самостоятельно.

#### Функции округления и модуля ####

<table>
    <tr>
        <th align="center">Функция</th>
        <th align="center">Описание функции</th>
    </tr>
    <tr>
        <td align="center">double ceil (double x);</td>
        <td align="left">Вычисляет наименьшее целое, значение которого не будет меньшим, чем х. Например, функция ceil (4.68) 
          вернет значение 5.00.
        </td>
    </tr>
    <tr>
        <td align="center">double floor (double x);</td>
        <td align="left">В отличии от предыдущей функции эта функция вычисляет наибольшее целое, по значению не превосходящее 
          х. Например, функция floor (4.68) вернет значение 4.00.
        </td>
    </tr>
    <tr>
        <td align="center">double modf (double value, double *ptr);</td>
        <td align="left">Разбивает значение аргумента value на целую и дробные части. Целую часть функция сохраняет в объекте 
          на который указывает указатель *ptr, а дробную возвращает.
        </td>
    </tr>
    <tr>
        <td align="center">double fabs (double x);</td>
        <td align="left">$|x|$ — модуль числа х (абсолютное значение)</td>
    </tr>
    <tr>
        <td align="center">double fmod (double x, double y);</td>
        <td align="left">остаток от деления х на y.</td>
    </tr>
    <tr>
        <td align="center">double round (double x);</td>
        <td align="left">Округляет к ближайшему целому числу, но тип оставляет double.</td>
    </tr>
    <tr>
        <td align="center">long int lround (double x);</td>
        <td align="left">Округляет к ближайшему целому числу, возвращает тип long int.</td>
    </tr>
</table>
***Важно!*** Функции **round** (x) и **lround** (x) существуют начиная со стандарта C99, который включается опцией компилятора -std=c99.
