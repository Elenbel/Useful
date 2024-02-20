### Стек через динамический список на С ###

На основе односвязного списка удобно построить структуру данных стек, причем у этого стека не будет возникать 
проблем переполнения, т.к. для каждого нового элемента запрашивается дополнительная память.

#### Интерфейс стека на основе односвязного списка ####

```c
#ifndef MYSTACK_H_INCLUDED
#define MYSTACK_H_INCLUDED
#include <stdlib.h>
typedef int tData;
typedef struct sNode{
    tData value;
    struct sNode *next;
} tNode;
typedef struct{
    tNode *p_begin;
    size_t m_size;
} tStack;
void stack_push(tStack *s, tData value);
tData stack_pop(tStack *s);
tData stack_top(const tStack *s);
size_t stack_size(const tStack *s);
void stack_clear(tStack *s);
tStack stack_create();
void stack_print(const tStack *s);
int stack_is_empty(const tStack *s);
#endif // MYSTACK_H_INCLUDED
```

#### Реализация стека на основе односвязного списка ####

```c
#include "mystack.h"

#include <stdio.h>
#include <assert.h>

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

//грамотно чистит односвязный список
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

void stack_push(tStack *s, tData value)
{
    tNode *p = (tNode *)malloc(sizeof(tNode));
    p->value = value;
    p->next = s->p_begin;
    s->p_begin = p;
    s->m_size++;
}

tData stack_pop(tStack *s)
{
    //??? А что, если стек пуст ???

    tNode *tmp = s->p_begin;
    tData tmp_value = tmp->value;
    s->p_begin = s->p_begin->next;
    s->m_size--;
    free(tmp);
    return tmp_value;
}

tData stack_top(const tStack *s)
{
    //??? А что, если стек пуст ???
   
    return s->p_begin->value;
}

size_t stack_size(const tStack *s)
{
    return s->m_size;
}

void stack_clear(tStack *s)
{
    delete_list(s->p_begin);
    s->p_begin = NULL;
    s->m_size = 0;
}

tStack stack_create()
{
    tStack new_stack = {NULL, 0};
    return new_stack;
}

void stack_print(const tStack *s)
{
    print_list(s->p_begin);
}

int stack_is_empty(const tStack *s)
{
    return s->m_size == 0;
}
```
