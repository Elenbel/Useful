### Динамические двумерные массивы в С ###

Динамические двумерные массивы в языке Си имеют сложный способ представления в памяти компьютера.

Рассмотрим одномерный массив из 10 указателей на объекты типа int:
```c
int *A[10];
```
A представляет собой указатель на указатель на int.

Кроме того, массив указателей может быть не статическим, а динамическим:
```c
int **A;
```
Следующий шаг сделать очень просто — по указателям, хранящимся в массиве A могут лежать не по одному 
значению, а по одномерному динамическому массиву таких значений.

![Текст описания](https://foxford.ru/uploads/tinymce_image/image/3132/dynamic_array.png)

#### Передача динамических двумерных массивов в функцию ###
Динамические массивы передаются в функции по-другому, **передается указатель на начало массива указателей**, 
а длина строки и количество строк вообще нигде не фигурируют. Контроль за границами массивов лежит полностью 
на программисте, поэтому, вероятно, стоит передавать в функцию отдельными параметрами размеры массива — 
количество строк и столбцов.

#### Пример работы с динамическим двумерным массивом ####
```c
#include <stdio.h>
#include <stdlib.h>

#define MATRIX_HEIGHT 4
#define MATRIX_WIDTH 5

void dynamic_array_print(int **A, size_t N, size_t M)
{
    for(int i = 0; i < N; i++) {
        for(int j = 0; j < M; j++) {
            printf("%*d", 5, A[i][j]);
        }
        printf("\n");
    }
}

/*
    return pointer on 2d dynamic array
    !allocates memory -> to be freed later
*/
int ** dynamic_array_alloc(size_t N, size_t M)
{
    int **A = (int **)malloc(N*sizeof(int *));
    for(int i = 0; i < N; i++) {
        A[i] = (int *)malloc(M*sizeof(int));
    }
    return A;
}

void dynamic_array_free(int **A, size_t N)
{
    for(int i = 0; i < N; i++) {
        free(A[i]);
    }
    free(A);
}

void dynamic_array_test(size_t N, size_t M)
{
    int **A = dynamic_array_alloc(N, M);
    int x = 1;
    for(int i = 0; i < N; i++) {
        for(int j = 0; j < M; j++) {
            A[i][j] = x;
            x += 1;
        }
    }
    dynamic_array_print(A, N, M);
    /*memory investigation*/
    printf("\n Pointers to lines: ");
    for(int **p = A; p < A + 3; p++)
        printf("%10d", (long int)*p);
    printf("\n Direct memory access (dangerous!!!):\n");
    for(int *p = (int*)*A; p < (int*)*A + 25; p++)
        printf("%d\t", *p);
    dynamic_array_free(A, N);
}

int main()
{
    dynamic_array_test(MATRIX_HEIGHT, MATRIX_WIDTH);
    return 0;
}
```
#### Выделение памяти под динамический массив ####
Как видно из примера, создание такой сложной структуры как двумерный динамический массив требует множества 
системных вызовов по выделению памяти:
```c
int **A = (int **)malloc(N*sizeof(int *));
for(int i = 0; i < N; i++) {
    A[i] = (int *)malloc(M*sizeof(int));
}
```
При таком выделении памяти нельзя просто взять, и освободить память по адресу A, т.к. будет возникать утечка 
памяти.

Правильное очищение таково:
```c
for(int i = 0; i < N; i++) {
    free(A[i]);
}
free(A);
```
Альтернатива такова: при некотором владении адресной арифметикой можно выделить память сразу для всех одномерных 
массивов, необходимых для организации двумерного динамического массива:
```c
int ** A = malloc(n*sizeof(int*) + n*m*sizeof(int));
char * pc = A;
pc += n*sizeof(int*);
for (int i=0; i<n; i++)
    A[i] = pc + i*sizeof(m*sizeof(int));
```
Тогда освобождение памяти будет происходить очень легко:
```c
free(A);
```
