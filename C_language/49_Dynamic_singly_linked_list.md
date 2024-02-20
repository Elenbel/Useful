### Динамический односвязный список на С ###

```c
#include <stdio.h>
#include <stdlib.h>
typedef int tData;
typedef struct sNode{
    tData value;
    struct sNode *next;
} tNode;
tNode* create_list(int N)
{
    tNode *p_begin = NULL;
    tNode *p = NULL;
    //заполним односвязный список
    p_begin = (tNode *)malloc(sizeof(tNode));
    p = p_begin;
    p->next = NULL;
    p->value = 0;
    for(int k = 1; k < N; k++) {
        p->next = (tNode *)malloc(sizeof(tNode));
        //шагнуть вперед !!!
        p = p->next;
        //заполнить _новую_ структуру данных
        p->next = NULL;
        p->value = k;
    }
    return p_begin;
}
//распечатаем односвязный список
void print_list(tNode *p_begin)
{
    tNode *p = p_begin;
    while (p != NULL) {
        //распечатать структуру данных
        printf("%d \t", p->value);
        //шагнуть вперед !!!
        p = p->next;
    }
}
void delete_list(tNode *p_begin)
{
    tNode *p = p_begin;
    while (p != NULL) {
        tNode *tmp;
        tmp = p;
        //шагнуть вперед !!!
        p = p->next;
        //удалить память ячейки
        free(tmp);
    }
}
int main()
{
    tNode *p_begin = create_list(10);
    print_list(p_begin);
    delete_list(p_begin);
    printf("List printed!\n");
    return 0;
}
```
Подобным образом можно реализовать и двусвязный список, по которому можно будет пробегать не только вперед, но и назад.
