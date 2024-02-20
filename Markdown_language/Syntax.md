# Руководство по оформлению Markdown файлов
Markdown - это облегчённый язык разметки, который преобразует текст в структурированный HTML. Следующее руководство поможет вам разобраться, как использовать Markdown.

## Заголовки
```
# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня
#### Заголовок четвёртого уровня
##### Заголовок пятого уровня
###### Заголовок шестого уровня
```
***Пример:***

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня
#### Заголовок четвёртого уровня
##### Заголовок пятого уровня
###### Заголовок шестого уровня
---

## Параграфы и переносы строк
```
Это параграф. Чтобы создать новый параграф, оставьте пустую строку между двумя строками текста.
Это первая строка  
И это вторая строка, но они находятся в одном параграфе. Для переноса строки используйте два пробела в конце предыдущей строки.
```
***Пример:***

Это параграф. Чтобы создать новый параграф, оставьте пустую строку между двумя строками текста.

Это первая строка  
И это вторая строка, но они находятся в одном параграфе. Для переноса строки используйте два пробела в конце предыдущей строки.

---

## Выделение текста
```
*курсив*  
_курсив_
**жирный**  
__жирный__
***жирный курсив***  
___жирный курсив___
~~зачеркнутый~~
```
***Пример:***

*курсив*  
_курсив_

**жирный**  
__жирный__

***жирный курсив***  
___жирный курсив___

~~зачеркнутый~~

---

## Списки
### Нумерованный список
```
1. Пункт первый
2. Пункт второй
3. Пункт третий
```
***Пример:***

1. Пункт первый
2. Пункт второй
3. Пункт третий
---

### Маркированный список
```
- Пункт первый
- Пункт второй
- Пункт третий
```
***Пример:***

- Пункт первый
- Пункт второй
- Пункт третий
---
### Вложенные списки
Также можно делать вложенные списки, добавляя 4 пробела перед пунктом:
```
1. Пункт первый
    - Подпункт первый
    - Подпункт второй
2. Пункт второй
```
***Пример:***

1. Пункт первый
    - Подпункт первый
    - Подпункт второй
2. Пункт второй
---

## Ссылки
```
[Текст ссылки](https://www.example.com)
```
***Пример:***

[Текст ссылки](https://www.example.com)

---

## Изображения
```
![Текст описания](https://www.example.com/image.jpg)
```
***Пример:***

![Текст описания](https://assets.simpleviewinc.com/simpleview/image/upload/c_fill,h_720,q_75,w_1400/v1/clients/newyorkcity/Coronavirus_Info_midtown_manhattan_skyline_nyc_3000x2000_364fa9b8-86ce-4f95-907a-4bd8ea32f232.jpg)

---

## Блоки кода
### Строка кода
```
`строка кода`
```
***Пример:***

`строка кода`

---
### Блок кода

Удалите символы `\`
```
\```
Блок кода
\```
```
***Пример:***

```
Блок кода
```

---
### Подсветка кода
Для блоков кода можно указывать язык программирования.

Используется подсветка синтаксиса из библиотеки `linguist`, которая включает множество различных языков.

Удалите символы `\`
```
\```python
print("Привет, мир!")
\```
```
***Пример:***
```python
print("Привет, мир!")
```

---

## Цитаты
```
> Первый уровень цитирования
>> Второй уровень цитирования
>>> Третий уровень цитирования
```
***Пример:***

> Первый уровень цитирования
>> Второй уровень цитирования
>>> Третий уровень цитирования

---

## Горизонтальная линия
```
---
```
***Пример:***

---

---

## Таблицы
```
| Заголовок 1 | Заголовок 2 |
| ----------- | ----------- |
| Ячейка 1    | Ячейка 2   |
| Ячейка 3    | Ячейка 4   |
```
***Пример:***

| Заголовок 1 | Заголовок 2 |
| ----------- | ----------- |
| Ячейка 1    | Ячейка 2   |
| Ячейка 3    | Ячейка 4   |

---

### Таблица как HTML
```
<table>
    <tr>
        <th>Заголовок 1</th>
        <th>Заголовок 2</th>
    </tr>
    <tr>
        <td>Ячейка 1.1</td>
        <td>Ячейка 2.1</td>
    </tr>
    <tr>
        <td>Ячейка 1.2</td>
        <td>Ячейка 2.2</td>
    </tr>
</table>
```
***Пример:***

<table>
    <tr>
        <th>Заголовок 1</th>
        <th>Заголовок 2</th>
    </tr>
    <tr>
        <td>Ячейка 1.1</td>
        <td>Ячейка 2.1</td>
    </tr>
    <tr>
        <td>Ячейка 1.2</td>
        <td>Ячейка 2.2</td>
    </tr>
</table>

---

## Чек-листы
```
- [x] Задача 1
- [ ] Задача 2
- [ ] Задача 3
```
***Пример:***

- [x] Задача 1
- [ ] Задача 2
- [ ] Задача 3

---

## Внутренние ссылки
```
[Перейти к Заголовку 1](#title1)
## <a id="title1">Заголовок 1</a>
Какой-то контент
```
***Пример:***

[Перейти к Заголовку 1](#title1)

## <a id="title1">Заголовок 1</a>
Какой-то контент

---

### Ссылка на заголовок на английском
```
[Some title 1](#some-title-1)
## Some Title 1
Some content
```
***Пример:***

[Some title 1](#some-title-1)

## Some Title 1
Some content

---

## Автоматические ссылки
```
<http://example.com/>
<address@example.com>
```
***Пример***

<http://example.com/>

<address@example.com>

---

## HTML
Markdown поддерживает использование прямого HTML внутри документа, так что вы можете использовать любые HTML-теги для более сложного оформления:
```
<kbd>CTRL</kbd> + <kbd>P</kbd>
```
***Пример:***

<kbd>CTRL</kbd> + <kbd>P</kbd>

---

## HTML-коды
Например, вы можете использовать HTML-код `&macr;` для добавления черты над буквой:
```
A&macr;
```
***Пример:***

A&macr;

---

## Комментарии
Вы можете вставить комментарии в свой markdown-файл, которые не будут отображаться в окончательном отформатированном виде:
```
[//]: # (Это комментарий, он не будет отображаться)
```
***Пример:***

[//]: # (Это комментарий, он не будет отображаться)

---

## Эмодзи (Github)
Вы можете использовать эмодзи в своих Markdown-файлах. [Существует множество эмодзи](https://gist.github.com/rxaviers/7360908), которые вы можете использовать, вот некоторые из них:
```
:smile:
:laughing:
:blush:
```
***Пример:***

:smile:
:laughing:
:blush:

---

## Математические формулы
### Основные принципы
Формулы можно написать двумя способами: внутри текста (строчные) и на отдельной строке (вынесенные). Строчные формулы окружаются знаками доллара с обеих сторон
$...$. Между символами операций (плюс, умножение и т.д.) пробелов можно ставить сколько угодно или вовсе не ставить —  автоматически поставит только один пробел.
```
Строчные формулы: $x+y=0$; $a + b = 1$
```
***Пример:***

Строчные формулы: $x+y=0$; $a + b = 1$

Вынесенные формулы окружаются конструкцией `\$$...$$`. Неважно, ставите вы доллары на одной строке с текстом или нет, всё равно 
выведет это на отдельную строку.
```
\$$
x + y = 0
$$
```
***Пример:***

\$$
x + y = 0
$$

---

### Степени и индексы
Для индекса используется синтаксис **x_{индекс}**, а **“крышечка”** возводит в степень **x^{степень}**. Если индекс или степень записвается одной цифрой то 
фигурные скобки '{ }' можно убрать.
```
$x_1$
```
```
$y^2$
```
```
$a_{90}$
```
```
$b^{34}$
```
```
$c_{56}^{78}$
```
```
$d^{78}_{56}$
```
***Пример:***

$x_1$ <br>
$y^2$ <br>
$a_{90}$ <br>
$b^{34}$ <br>
$c_{56}^{78}$ <br>
$d^{78}_{56}$

---

### Корни и дроби
Переходим к командам в формулах, они начинаются со знака косой черты, т.e. **\команда**. Самые используемые команды в работе это корень и дроби. Корень из 
n-ой степени выполняет команда **\sqrt[n]{выражение}**, где **n** является необязательным аргументом, а дробь пишется как **\frac{числитель}{знаменатель}**.
```
$\sqrt[n]{1 + x^2}$
```
```
$\frac{37}{41}$
```
***Пример:***

$\sqrt[n]{1 + x^2}$ <br>
$\frac{37}{41}$

---

### Суммы и интегралы
Синтаксис для сумм и интегралов представлен. В строчной формуле эти операторы меньше, чем в вынесенных.
```
Сумма $\sum$ $^{N}_{i=1}$, интеграл $\int^\infty_0$
```
***Пример:***

Сумма $\sum$ $^{N}_{i=1}$, интеграл $\int^\infty_0$

Еше интегралы

***Пример:***

$\oint$ - `$\oint$` <br>
$\iint$ - `$\iint$` <br>
$\iiint$ - `$\iiint$` <br>
$\idotsint$ - `$\idotsint$` <br>

---

### Команды функций
Некоторые функции встроены в виде команд, например, тригонометрические. После запуска напечатаются названия функций обычным текстом, а не математическим
шрифтом. Я предпочитаю ими пользоваться, чтобы отличать функции от переменных внешне, но это, конечно, необязательно.

***Пример:***

$\sin$ - `$\sin$` <br>
$\cos$ - `$\cos$` <br>
$\tan$ - `$\tan$` <br>
$\arcsin$ - `$\arcsin$` <br>
$\arccos$ - `$\arccos$` <br>
$\arctan$ - `$\arctan$` <br>
$\log$ - `$\log$` <br>

---

### Текст внутри формул
Если вам нужно добавить какой-то текст сбоку от формул, то нужно использовать для этого универсальную команду **\text{...}**. Ещё с помощью данной команды можно
напечатать обычным текстом элементы формул, как в командах для функций, только самостоятельно выбирать, что написать прямым шрифтом.
```
\$$
\text{Уравнение окружности: } x^2 + y^2 = R^2, R \text{ - радиус}
$$
```

***Пример:***

\$$
\text{Уравнение окружности: } x^2 + y^2 = R^2, R \text{ - радиус}
$$

Текст также может быть написан курсивом **\textit{...}** или жирным шрифтом **\textbf{...}**.

---

### Пробелы в формулах
Настраивать расположение можно разными способами, например, через вставку **\text{пробел}**, но можно воспользоваться более простыми и гибкими командами:

***Пример:***

Положительные пробелы: <br>
$|x\,y|$ - `$|x\,y|$` <br>
$|x\;y|$ - `$|x\;y|$`

Отрицательный пробел: <br>
$|x\!y|$ - `$|x\!y|$`

---

### Популярные символы
Эти коды предоставляет вам возможность написать любой нужный символ, не представленный на клавиатуре. Здесь приведены некоторые примеры часто используемых 
символов: греческие буквы, знаки сравнения, математические операторы и другое.

***Пример:***

Греческие буквы: <br>
$\Phi$ - `$\Phi$` <br>
$\phi$ - `$\phi$` <br>
$\varphi$ - `$\varphi$` <br>
$\Delta$ - `$\Delta$` <br>
$\delta$ - `$\delta$` <br>
$\theta$ - `$\theta$` <br>
$\pi$ - `$\pi$` <br>
$\alpha$ - `$\alpha$` <br>
$\beta$ - `$\beta$` <br>
$\gamma$ - `$\gamma$`

Знаки сравнения: <br>
$\leq$ - `$\leq$` <br>
$\geq$ - `$\geq$` <br>
$\ll$ - `$\ll$` <br>
$\gg$ - `$\gg$` <br>
$\neq$ - `$\neq$` <br>
$\approx$ - `$\approx$` <br>
$\equiv$ - `$\equiv$` <br>
$\pm$ - `$\pm$` <br>
$\mp$ - `$\mp$` <br>
$\times$ - `$\times$` <br>
$\cdot$ - `$\cdot$`

Другое: <br>
$\infty$ - `$\infty$` <br>
$\to$ - `$\to$` <br>
$\partial$ - `$\partial$` <br>
$\hbar$ - `$\hbar$` <br>
$\nabla$ - `$\nabla$` <br>
$\vdots$ - `$\vdots$` <br>
$\cdots$ - `$\cdots$` <br>
$\ldots$ - `$\ldots$`

---

### Многострочные формулы
Часто в работе приходится писать логически связанные между собой формулы: они чередуются одна за другой. В обычной вынесенной формуле не получится написать 
формулы на разных строках в пределах одного блока. В таком случае удобно использовать окружение align, которое используется так:
```
$$

\begin{align}

  первая формула \\ 

  вторая формула \\ 

  ...

\end{align}

$$
```
Две косые черты \\ используются для того, чтобы перенести выражение на другую строку.
```
$$
\begin{align}
ax^2 + bx + c = 0 \\
D = b^2 - 4ac \\
x_{1,2} = \frac{-b \pm \sqrt{D}}{2a}
\end{align}
$$
```

***Пример:***

$$
\begin{align}
ax^2 + bx + c = 0 \\
D = b^2 - 4ac \\
x_{1,2} = \frac{-b \pm \sqrt{D}}{2a}
\end{align}
$$

Так же можно использовать выравнивание, чтобы получить более удобочитаемый вид формулы. Осуществить его можно с помощью знака амперсанда **&**, для этого 
достаточно поставить его в тех местах, относительно которых вы хотите произвести выравнивание:
```
$$
\begin{align}
ax^2 + bx + c &= 0 \\
D &= b^2 - 4ac \\
x_{1,2} &= \frac{-b \pm \sqrt{D}}{2a}
\end{align}
$$
```

***Пример:***

$$
\begin{align}
ax^2 + bx + c &= 0 \\
D &= b^2 - 4ac \\
x_{1,2} &= \frac{-b \pm \sqrt{D}}{2a}
\end{align}
$$

---

### Векторы и матрицы
Для обозначения вектора с помощью стрелочки используется команда **\vec{...}**, для написания вектора в матричном виде выбирают окружение **pmatrix**, подобных 
окружений есть несколько. Для матрицы использую этот же пакет, а столбцы разделяю знаком **&**:

Вектор:
```
$$
\vec{r} = 
\begin{pmatrix}
x \\ y \\ z \\
\end{pmatrix}
$$
```

***Пример:***

$$
\vec{r} = 
\begin{pmatrix}
x \\ y \\ z \\
\end{pmatrix}
$$

Матрица:
```
$$
M = 
\begin{pmatrix}
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3 \\
c_1 & c_2 & c_3 \\
\end{pmatrix}
$$
```

***Пример:***

$$
M = 
\begin{pmatrix}
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3 \\
c_1 & c_2 & c_3 \\
\end{pmatrix}
$$

---

### Скобки
Согласитесь, неприятно, когда написана большая формула с дробями, а скобки стоят несоответствующие сей конструкции — обычные, маленькие. Для такого случая есть 
несколько команд для увеличения размера скобок. Причем как круглых, так и квадратных и фигурных скобок. Когда некогда разбираться и подбирать размер, применяйте
конструкцию **\left( ... \right)**, она сама решает, какой взять масштаб для скобок. Эти команды используется только в паре, по одиночке они работать не будут.
```
$$
\left( \frac{1}{2} + \int^\infty_0 \frac{dx}{x^2} \right)
$$
```

***Пример:***

$$
\left( \frac{1}{2} + \int^\infty_0 \frac{dx}{x^2} \right)
$$

Если не устраивает автоматически подобранный размер, то тогда можно отрегулировать его самостоятельно командами **\bigl** < **\Bigl** < **\biggl** < **\Biggl** 
для левых скобок и соответствующими командами для правых скобок **\bigr** < **\Bigr** < **\biggr** < **\Biggr**.
```
$$
\Biggl(\biggl(\Bigl(\bigl(
(x + y)
\bigr)\Bigr)\biggr)\Biggl)
$$
```

***Пример:***

$$
\Biggl(\biggl(\Bigl(\bigl(
(x + y)
\bigr)\Bigr)\biggr)\Biggl)
$$