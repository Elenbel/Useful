### Проверка скобочной последовательности на С ###

Программа на языке Си, выясняющая корректность скобочной последовательности при помощи стека:
```c
#include <stdio.h>
#include <stdlib.h>
#include "mystack.h"
int check_left_brace(char brace);
int check_right_brace(char brace);
char get_the_brace_left_pair(char brace);
void braces_succession_checker();
int main()
{
    braces_succession_checker();
    return 0;
}
void braces_succession_checker()
{
    int good_braces_succession = 1;
    tStack open_braces = stack_create();
    char brace = getchar();
    while (brace != '\n') {
        if (check_left_brace(brace)) {
            stack_push(&open_braces, brace);
        } else if (check_right_brace(brace)) {
            if (stack_is_empty(&open_braces)) {
                good_braces_succession = 0;
                break;
            }
            char pair_candidate = stack_pop(&open_braces);
            if (get_the_brace_left_pair(brace) != pair_candidate) {
                good_braces_succession = 0;
                break;
            }
        } //else символ вообще не скобка
        brace = getchar();
    }
    if (good_braces_succession
        && !stack_is_empty(&open_braces)) {
        //остались незакрытые левые скобки
        good_braces_succession = 0;
    }
    if (good_braces_succession) {
        printf("OK!\n");
    } else {
        printf("Bad succession!\n");
    }
}
int check_left_brace(char brace)
{
    return (brace == '(' || brace == '{'
            || brace == '[' || brace == '<');
}
int check_right_brace(char brace)
{
    return (brace == ')' || brace == '}'
            || brace == ']' || brace == '>');
}
char get_the_brace_left_pair(char brace)
{
    if (brace == ')') return '(';
    else if (brace == '}') return '{';
    else if (brace == ']') return '[';
    else if (brace == '>') return '<';
    else brace;
}
```

#### Интерфейс стека ####

```c
#ifndef MYSTACK_H_INCLUDED
#define MYSTACK_H_INCLUDED

#include <stdlib.h>

typedef char tData;

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

#### Реализация стека ####

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
        printf("%c \t", p->value);
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
