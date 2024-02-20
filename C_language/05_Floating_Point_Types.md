### Типы чисел с плавающей точкой в С ###

![Текст описания](https://foxford.ru/uploads/tinymce_image/image/2912/fb1d3d3268d51f53.png)

В языке Си реализованы только два типа чисел с плавающей точкой, соответствующие международному стандарту **IEEE754**.

Считывание и печать чисел **float**, **double** и **long double** функциями printf и scanf:
```c
printf("%f", my_float);
scanf("%f", &my_float);

printf("%f", my_double); //Обратите внимание! Спецификаторы для double различаются!
scanf("%lf", &my_double);

printf("%Lf", my_long_double);
scanf("%Lf", &my_long_double);
```
