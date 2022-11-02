# Основы си
Оглавление:
#1 Калькулятор
#2 Процедуры и функции
#3 Массивы и циклы
#4 Библиотеки/строки/языки/символы
#5 Циклы
#6 Массивы/матрицы
#7 Заполнение всего столбца/строки
#8 Макросы
#9 Рандомные числа
#10 Структуры/typedef
#11 Вещественные числа/float
#12 Функции Atoi(int)/Atof(int)
#13 Указатели адреса/NULL
#14 Указатель на структуру
#15 Размер в байтах
#16 Распределение памяти
#17 Динамический массив/адресация памяти
#18 Указатель на указатель
#19 Поменять местами значения
#20 Заполнение массива
#21 Указатель на функцию
#22 Тернарный оператор
#23 Факториалы/последовательность ввода текста
#24 Оператор выбора switch
#25 Статическая переменная
#26 Возведение в степень
#27 Инициализация
#28 Открытие файла/запись в файл/закрытие файла
#29 Коды символов и бинарный режим(<<wb>> <<rb>>)
#30 Функции ftell и fseek
#31 Объединения
#32 Строки подробно
#33 Перечисления и перечисляемые константы
#34 Функции с переменным количеством аргументов
#35 Среднее арифметическое
#36 Системы счисления
#37 Флаги
#38 Аргументы командной строки
#39 Константы const
#40 Оператор запятая
#41



#1 Калькулятор

int main()
{
    float x, y;
    int i;
    printf("input x=");
    scanf(«%f», &x);
    printf("input y=");
    scanf(«%f», &y);
    printf("oper: \n1=*\n2=+\n3=-\n4=:\nselect code=");
    scanf(«%d», &i);
    if (i == 1)
        printf("%f*%f=%g", x, y, x * y);
    if (i == 2)
        printf("%f+%f=%g", x, y, x + y);
    if (i == 3)
        printf("%f-%f=%g", x, y, x - y);
    if (i == 4)
        printf("%f / %f=%g", x, y, x / y);
    return 0;
}          


#2 Процедуры и функции

void proc1()
{
    printf("ggg\n»);
    printf("qqq\n»);
}
int ret7(int x, int y)
{
    return x * y;
}
int main()
{
    int t;
    printf("hw\n");
    t = ret7(22, 10);
    t = ret7(t, 4);
    printf("t = %d", t);
    return 0;
}      

void proc1(int x)
{
   if(x<10)
   {
       printf("%d\n",x);
   }
   else 
   {
       printf("error\n");
   }
}
int main()
{   
    
    proc1(5); 
    proc1(15);
    return 0;
}
 

void proc(int x)
{
    if (x < 10)
    printf("%d\n", x);
    else
    printf("error\n");
}
int func(int a, int b)
{
    if (a > b)
    return 1;
    else
    return 0;
}
int main()
{
    int t;
    proc(5);
    proc(15);
    t = func(30, 20);
    proc(t);
    return 0;
}


#3 Массивы и циклы

int main()
{
    int i;
    int mas[10];
    mas[0] = 555;
    mas[1] = 333;
    mas[2] = 666;
    i = 0;
    while (i < 10)
    {
        printf("%d = %d\n", i, mas[i]);
        i = i + 1;
    }
    return 0;
}   

{
    int i;
    int mas[10];
    i = 0;
    while (i < 10)
    {
        if (i < 0)
            mas[i] = 7;
        else
            mas[i] = i * i;
        i = i + 1;
    }
    i = 0;
    while (i < 10)
    {
        printf("%d = %d\n", i, mas[i]);
        i = i + 1;
    }
    return 0;
}        
 

#include <stdio.h>
int main()
{
    int i = 0;
    int mas[] = {1,2,3,40,5,6,7,80,9,0};
    int len = sizeof(mas) / sizeof(mas[0]);

    for (i=0;i<10;i++)
        printf("%d\n", mas[i]);

    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int a[5] = {10, 2, 3, 4, 15};
    int i = 0;
    while (printf("%d\n", a[i]), ++i < 5);
    return 0;
}  

Копирование массива

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
typedef struct {int x, y, z;} point;
int main()
{
    int i = 0;
    int mas[8] = {1, 2, 3, 4, 5, 6};
    memcpy(mas, (int[8]){55, 66, 77}, sizeof(mas));
    for (i = 0; i < 8; i++)
        printf("%d\n", mas[i]);
    return 0;
} 

#include <stdio.h>
#include <stdlib.h>
typedef struct {
    int x;
    int mas[10];
    int y;
} obj;
int i = 0;
int k = 0;
int main()
{
    obj o[2] = {{10, {[7] = 3, 4, 5}}, {100, {[0] = 33, 44, 55}, 200}};
    for (k=0;k<2;k++)
    {
        printf("%d %d   ", o[k].x, o[k].y);
        for (i = 0; i < 10; i++)
            printf("%d ", o[k].mas[i]);
        printf("\n");
    }
    return 0;
}   


#4 Библиотеки/строки/языки/символы

#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <windows.h>
#include <winuser.h>
int main()
{
    setlocale(LC_ALL, "Russian");
    char s[10] = "абвгАБВГ";
    s[0] = '7';
    printf("%s\n", s);
    sprintf(s, "12121212");
    s[4] = '\0';
    printf("%s\n", s);
    scanf(«%s», s);
    gets();
    OemToChar(s, s);
    printf("%s\n", s);
    return 0;
}      

%c/%i

int main()
{
    int c = 105;
    printf("%c", c);
    return 0;
}        


#5 Циклы

int main()                    
{
    int a = 22, b = 8;
    a += ++b + ++b;
    printf("%d %d", a, b);
    return 0;
}           


int main()
{
    int a;
    do
    {
        printf("input integer =");
        scanf("%d", &a);
    }
    while (a != 7);
    return 0;
}


int main()
{
    int a;
    for (a = 0; a < 10; a++)
        printf("%d\n", a);
    return 0;
}


#include <stdio.h>
#include <stdlib.h>
int main()
{
    int a;
    for (a = 2; a <= 18; a+=2)
        printf("%d\n", a);
    a = 2;
    do
    {
        printf("%d\n", a);
        a += 2;
    }
    while (a <= 18);
    return 0;
}


#include <stdio.h>
#include <stdlib.h>
int main()
{
    int i;
    char str[9];
    for (i = 0; i < 8; i++)
        str[i] = '#';
    str[8] = '\0';
    printf("%s\n", str);
    i = 0;
    while(str[i] != '\0')
    {
        printf("%c", str[i]);
        i++;
    }
    return 0;
}


#6 Массивы/матрицы

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int m[9][9];
    m[2][5] = 3;
    int i, k;
    for (k = 0; k < 9; k++)
    {
        for (i = 0; i < 9; i++)
        {
            m[k][i] = 7;
            printf("%d", m[k][i]);
        }
        printf("\n");
    }
    char mm[2][6][20];
    mm[0][1][10] = 'w';
    return 0;
}      


#include <stdio.h>
#include <stdlib.h>
int main()
{
    int m[9][9];
    m[2][5] = 3;
    int i, k;
    for (k = 0; k < 9; k++)
    {
        for (i = 0; i < 9; i ++)
        {
            m[k][i] = (k + 1) * (i + 1);
            printf("%d\t", m[k][i]);
        }
        printf("\n");
    }
    return 0;
}   


#7 Заполнение всего столбца/строки

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int m[9][9];
    m[2][5] = 3;
    int i, k;
    for (k = 0; k < 9; k++)
    {
        for (i = 0; i < 9; i ++)
        {
            m[k][i] = (k + 1) * (i + 1);
            if (k == 5)
                m[k][i] = 5;
            if (i == 3)
                m[k][i] = 3;
            printf("%d\t", m[k][i]);
        }
        printf("\n");
    }
    return 0;
}  


#8 Макросы

#include <stdio.h>
#include <stdlib.h> 
#define cnt 5           //cnt = 5//
#define celoei int i = cnt
#define showi printf("%d\n", i)
int main()
{
    celoei;
    showi;
    return 0;
}  

#include <stdlib.h>
#include <stdio.h>
#define w 100
#define mm (a, b) (a) * (b)
/* ifdef проверка на наличие макроса
 * ifndef проверка на отсутствие макроса
 * endif для обозначения конца цикла if
 * elif иначе если
 * undef отмена работы макроса */
int main()
{
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
#define work1
#ifdef work1
    #define sqr(a) (a) * (a)
    #define mod(a) ((a) < 0 ? -(a) : (a))
#else
    #error не указан макрос
#endif
#define len 70
#if len < 10
    #error ошибка
#endif
int main()
{
    int i = 0;
    #ifdef sqr
        i = sqr(5);
    #endif
    printf("%d\n", i);
    printf("%d\n", mod(5-25));
    printf("%d\n", mod(15));
    return 0;
} 

#include <stdlib.h>
#include <stdio.h>
#define A 0b0001
#define B 0b0010
#define C 0b0100
#define D 0b1000
char tmp = A | C;
int main()
{
    printf("%x\n", tmp);
    if ((tmp & A) && (tmp & C))
        printf("OK!\n");
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
int main()
{
    printf("%d\n", __LINE__);
    printf("%s\n", __FILE__);
    return 0;
}   


#9 Рандомные числа

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main()
{
    int i;
    srand(time(NULL));
    i = rand();
    printf("%d\n", i % 18);
    srand(time(NULL));
    i = rand();
    printf("%d\n", i % 10);
    i = rand();
    printf("%d\n", i);
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
#define k 10
int main()
{
    int mas[k];
    for (int i = 0; i < k; i ++)
        mas[i] = rand() % 20 + 20;
    for (int i = 0; i < k; i ++)
        printf("%d\n", mas[i]);
    int r = rand() % 10 + 10;
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
int main()
{
    char s[21];
    s[20] = '\0';
    for (int i=0; i<20; i++)
        s[i] = rand() % ('z' - 'a' + 1) + 'a';
    printf("%s", s);
    return 0;
}


#10 Структуры/typedef

#include <stdio.h>
#include <stdlib.h>
struct sPoint {
    int x, y;
} p;
typedef int celoe;
int main()
{
    struct sPoint a;
    a.y = 9;
    p.x = 7;
    celoe i = 5;
    printf("%d\n", i);
    printf("%d\n", a.y);
    return 0;
}  

#include <stdio.h>
#include <stdlib.h>
struct sPoint {
    int x, y;
} p;
typedef struct sPoint TPoint;
int main()
{
    TPoint a[10];
    a[4].y = 9;
    a[6].y = 17;
    printf("%d\n", a[4].y);
    printf("%d\n", a[6].y);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
struct sp {
    int x, y;
};
struct SShape {
    char *name;
    struct sp pos;
};
int main()
{
    struct SShape shape = {"quad", 10, 20};
    shape.pos.x = 55;
    printf("%s %d %d\n", shape.name, shape.pos.x, shape.pos.y);
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
typedef struct s1 t1;
typedef struct s2 t2;
struct s1 {
    int x;
    t2 *ref;
};
struct s2 {
    int y;
    t1 *ref;
};
int main()
{
    struct s1 a;
    struct s2 b;
    a.ref = &b;
    b.ref = &a;
    a.x = 10;
    b.y = 20;
    printf("%d\n", a.ref->y);
    printf("%d\n", b.ref->x);
    return 0;
}   


#11 Вещественные числа/float

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int i = 7;
    float f;
    f = (float)i;
    printf("%f", f);
    return 0;
}  

#include <stdio.h>
#include <stdlib.h>
int main()
{
    float f = 2.5;
    int i;
    i = f;
    printf("%f", f - (int)f);
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
float ms(float a, float b)
{
    return a + b;
}
float mm(float a, float b)
{
    return a * b;
}
int main()
{
    float tmp = 1;
    float (*func) (float, float);
    func = mm;
    tmp = func(5, 5);
    printf("%g\n", tmp);
    return 0;
}


#12 Функции Atoi(int)/Atof(float)

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int i = 123;
    char c[50] = "567";
    i = atoi(c);
    printf("%d", i);
    return 0;
}


#13 Указатели адреса/NULL

#include <stdio.h>                                         
#include <stdlib.h>
int main()
{
    int i = 5;
    int *iPtr = NULL;
    iPtr = &i;
    /*iPtr = 2;
    iPtr = NULL;*/
    if (iPtr != NULL) {
        *iPtr = 7;
        printf("%d\n", *iPtr);
    }
    return 0;
} 

#include <stdio.h>
#include <stdlib.h>
int inc(int a)
{
    return a + 1;
}
void inc2(int *x)
{
    if (x != NULL)
        *x = *x + 1;
}
int main()
{
    int i = 7;
    i = inc(i);
    inc2(&i);
    printf("%d\n", i);
    return 0;
}


#14 Указатель на структуру

#include <stdio.h>
#include <stdlib.h>
struct spoint {
    int x;
    int y;
};
typedef struct spoint tpoint;
void showpoint(tpoint point)
{
    printf("x=%d y=%d\n", point.x, point.y);
}
void SetPoint(tpoint *pointPtr, int xPos, int yPos)
{
    if (pointPtr != NULL) {
        (*pointPtr).x = xPos;
        (*pointPtr).y = yPos;
    }
}
int main()
{
    tpoint p;
    tpoint *pPtr = NULL;
    pPtr = &p;
    SetPoint(&p, 11, 22);
    showpoint(*pPtr);
    return 0;
} 


#15 Размер в байтах

 #include <stdio.h>
#include <stdlib.h>
int main()
{
    int x;
    x = sizeof(double);
    printf("%d\n", x);
    x = sizeof(char);
    printf("%d\n", x);
    return 0;
}


#16 Распределение памяти

#include <stdio.h>
#include <stdlib.h>
int main()
{
    void *p;
    int *x = NULL;
    x = malloc(sizeof(int));
    if (x != NULL) {
        *x = 333;
        printf("%d\n", *x);
    }
    free(x);
    x = NULL;
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
void CreateInt(int **p)
{
    *p = malloc(sizeof(int));
}
int main()
{
    int *a = NULL;
    CreateInt(&a);
    if (a != NULL)
    {
        *a = 777;
        printf("%d\n", *a);
    }
    free(a);
    a = NULL;
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
int main()
{
    void *p = NULL;
    p = malloc(8);
    if (p != NULL)
    {
        *(double *)p = 7.2;
        printf("%f\n", *(double *)p);
    }
    free(p);
    p = NULL;
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
void cr(int **p)
{
    *p = malloc(sizeof (int ));
}
void fr(void **p)
{
    free(*p);
    *p = NULL;
}
int main()
{
    int *a = NULL;
    cr(&a);
    if (a != NULL)
    {
        *a = 777;
        printf("%d\n", *a);
    }
    fr(&a);
    if (a == NULL)
        printf("ok\n");
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
int main()
{
    char c[2][20] = {"sdsdsdsds", "fefefeffe"};
    printf("size = %d\n", sizeof(c));
    int i = 0;
    for (i = 0; i<2; i++)
        printf("%s\n", c[i]);
    return 0;
}


#17 Динамический массив/адресация памяти

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int *mas = NULL;
    mas = malloc(sizeof(int) * 2);
    *mas = 4444;
    *(mas + 1) = 777;
    mas = realloc(mas, sizeof(int) * 5);
    printf("%d\n", mas[0]);
    printf("%d\n", mas[1]);
    free(mas);
    mas = NULL;
    return 0;
}     


#18 Указатель на указатель

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int k = 777;
    int *p;
    p = &k;
    *p = 111;
    int **p2;
    p2 = &p;
    **p2 = 333;
    int ***p3;
    p3 = &p2;
    ***p3 = 999;
    printf("%d\n", k);
    return 0;
} 

#include <stdio.h>
#include <stdlib.h>
int main()
{
    float a = 1.5;
    float b = 333;
    float *p;
    p = &a;
    *p = 3.1413;
    p = &b;
    *p = 2.718;
    printf("%f\n%f\n", a, b);
    return 0;
}


#19 Поменять местами значения

#include <stdio.h>
#include <stdlib.h>
void DoSomething(int *x, int *y)
{
    int buf = *x;
    *x = *y;
    *y = buf;
}
int main()
{
    int a = 5;
    int b = 9;
    DoSomething(&a, &b);
    printf("%d\n%d\n", a, b);
    return 0;
}


#20 Заполнение массива

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int i = 0;
    int *mas = NULL;
    int cnt = 10;
    mas = malloc(sizeof(*mas) * cnt);
    for (i=0;i<cnt;i++)
    {
        if (i == 0)
            mas[i] = 1;
        else
            mas[i] = mas[i - 1] * 2;
    }
    cnt += 4;
    mas = realloc(mas, sizeof(*mas) * cnt);
    for (i = cnt - 4;i<cnt;i++)
        mas[i] = 777;
    for (i=0;i<cnt;i++)
        printf("%d\n", mas[i]);
    return 0;
}


#21 Указатель на функцию

#include <stdio.h>
#include <stdlib.h>
typedef int(*TFuncAB) (int, int);
int max(int a, int b)
{
    if (a > b)
        return a;
    else
        return b;
}
int min(int a, int b)
{
    if (a < b)
        return a;
    else
        return b;
}
int GetOne(int mas[], TFuncAB fn)
{
    int i;
    int val = mas[0];
    if (fn != NULL)
        for (i = 1;i<10;i++)
            val = fn(val, mas[i]);
    return val;
}
int main()
{
    int (*fn[2]) (int, int);
    fn[0] = max;
    fn[1] = min;
    printf("%d\n", fn[0](11,5));
    printf("%d\n", fn[1](11,5));
    return 0;
}


#22 Тернарный оператор

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int i;
    scanf("%d", &i);
    i = 50 + (i < 10 ? 10 : i * 2);             (если i < 10 то вернуть 10 иначе i * 2)
    printf("%d\n", i);
    return 0;  
} 

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int i;
    scanf("%d", &i);
    i = i<10?10:(i>100?100:i+1000);             (если i > 100 то вернуть 100 иначе i + 1000)
    printf("%d\n", i);
    return 0;
}


#23 Факториалы/последовательность ввода текста

#include <stdlib.h>
#include <stdio.h>
void mp(int cnt)
{
    printf("chuni\n");
    cnt--;
    if (cnt > 0)
        mp(cnt);
}
int fact(int x)
{
    int i = 1;
    int res = 1;
    for (i = 1;i<=x;i++)
        res *= i;
    return res;
}
int factr(int x)
{
    if (x > 1)
        return x * factr(x - 1);
    else
        return 1;
}
int main()
{
    printf("f1 = %d\n", fact(10));
    printf("f1 = %d\n", factr(9));
    mp(10);
    return 0;
}

#include "stdio.h"
unsigned int factor(unsigned int k)
{
    if ( k == 1 )
        return(1);
    else
        return(k*factor(k-1));
}
void main ()
{
    unsigned int n;
    unsigned int f;
    printf("n--> ");
    scanf("%u", &n);
    f = factor(n);
    printf("Factorial %u is equal %u", n, f);
    getchar();
}   


#24 Оператор выбора switch

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int val = 1;
    switch (val) {
        case 9:
            printf("999\n");
            break;
        case 7:
        case 6:
        case 5:
            printf("777\n");
            break;
        case 2:
            break;
        default:
            printf("None\n");
    }
    return 0;
} 


#25 Статическая переменная

#include <stdlib.h>
#include <stdio.h>
int glhf()
{
    static int i = 0;
    return i++;
}
int main()
{
    printf("%d\n", glhf());
    printf("%d\n", glhf());
    printf("%d\n", glhf());
    return 0;
}


#26 Возведение в степень

#include <stdlib.h>
#include <stdio.h>
int mp(int ch, int s)
{
    if (s < 1) return 1;
    return ch * mp(ch, s- 1);
}
int main()
{
    int i;
    i = mp(6, 4);
    printf("%d\n", i);
    return 0; 
}   


#27 Инициализация

#include <stdlib.h>
#include <stdio.h>
struct sch {
    int x;
    char c;
};
typedef struct sch tch, *pnt;
int main()
{
    tch ic = {10, 'A'};
    pnt pic;
    pic = &ic;
    pic->x = 55;
    pic->c = 'F';
    /*struct sch ic = {10, 'A'};*/
        printf("%d   %c", ic.x, ic.c);
    return 0;
}    

#include <stdio.h>
#include <stdlib.h>
typedef struct {int x, y, z;} point;
int main()
{
    int m[3] = {[1] = 5, 6};
    point p = {.y = 33, 44};
    printf("%d %d %d\n", m[0], m[1], m[2]);
    printf("%d %d %d\n", p.x, p.y, p.z);
    return 0;
} 

#include <stdio.h>
#include <stdlib.h>
typedef struct {int x, y, z;} point;
/*int i;
int m[3];
point p;   то же самое что и static */
int main()
{
    static int i;
    static int m[3];
    static point p;
    printf("%d\n", i);
    printf("%d %d %d\n", m[0], m[1], m[2]);
    printf("%d %d %d\n", p.x, p.y, p.z);
    return 0;
}


#28 Открытие файла/запись в файл/закрытие файла

#include <stdlib.h>
#include <stdio.h>
int main()
{
    FILE *f;
    char c[1000];
    int i;
    float a;
    f = fopen("001.txt", "w");
    fprintf(f, "%d\n", 100);
    fprintf(f, "%g\n", 2.5);
    fprintf(f, "%s", "zfrfrfr gtrgrgrg\n");               (%s - слово целиком / %c - один символ)
    fprintf(f, "%s", "vcvcvc huuhuhu\n");
    fclose(f);
    f = fopen("001.txt", "r");
    if (f == NULL)
        printf("fopen read error");
    else {
        fscanf(f, "%d", &i);
        fscanf(f, "%g\n", &a);
        printf("%d  %g\n", i, a);
        while (!feof(f)) {
            /*fscanf(f, "%s\n", c);*/                      
            if (fgets(c, 1000, f) != NULL)
                printf("%s", c);
        }
    }
    fclose(f);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main()
{
    FILE *f;
    int i[10] = {1,2,3,444,5,6,7,888,9,10};
    f = fopen("001.txt", "w");
    /*fprintf(f, "%d", i);*/
    fwrite(i, 1, sizeof(i), f);
    fclose(f);
    int buf;
    f = fopen("001.txt", "r");
    while (!feof(f)) {
        if (fread(&buf, 1, sizeof(buf), f) > 0)
            printf("%d\n", buf);
    }
    fclose(f);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
typedef struct STest {
    int x,y;
    float f;
    char c[10];
} test;
int main()
{
    FILE *f;
    test i = {50, 88, 3.1413, "zvenigorod"};
    f = fopen("001.txt", "w");
    fwrite(&i, 1, sizeof(i), f);
    fclose(f);
    test buf;
    f = fopen("001.txt", "r");
    fread(&buf, 1, sizeof(buf), f);
    fclose(f);
    printf("%d %d %f %s\n", buf.x, buf.y, buf.f, buf.c);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int mas[] = {1, 2, 3, 4, 55, 66, 77};
    FILE *f = fopen("001.txt", "w");
    fwrite(mas, 1, sizeof(mas), f);
    fclose(f);
    int buf;
    f = fopen("001.txt", "r");
    while (!feof(f)) {
        if (fread(&buf, 1, sizeof(buf), f) > 0)
            printf("%d\n", buf);
    }
    fclose(f);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main()
{
    FILE *f;
    int i = 0;
    int cnt = 5;
    int *mas = malloc(sizeof(*mas) * cnt);
    for (i = 0; i < cnt; i++)
        mas[i] = 100 + i;
    f = fopen("001.txt", "w");
    fwrite(mas, cnt, sizeof(*mas), f);
    fclose(f);
    int *buf = malloc(sizeof(*buf) * cnt);
    f = fopen("001.txt", "r");
    fread(buf, cnt, sizeof(*buf), f);
    fclose(f);
    for (i = 0; i < cnt; i++)
        printf("%d\n", buf[i]);
    return 0;
} 

#include <stdlib.h>
#include <stdio.h>
int main()
{
    div_t mas[] = {{11, 111}, {2, 2222}, {33, 44}};
    FILE *f = fopen("001.txt", "w");
    fwrite(mas, 1, sizeof(mas), f);
    fclose(f);
    div_t buf;
    f = fopen("001.txt", "r");
    while (!feof(f)) {
        if (fread(&buf, 1, sizeof(buf), f) > 0)
            printf("[%d, %d]\n", buf.quot, buf.rem);
    }
    fclose(f);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int i = 555;
    float f1 = 36.6;
    char c[20] = "zvenigorod";
    FILE *f = fopen("001.txt", "w");
    fwrite(&i, 1, sizeof(i), f);
    fwrite(&f1, 1, sizeof(f1), f);
    fwrite(&c, 1, sizeof(c), f);
    fclose(f);
    int ibuf;
    float fbuf;
    char cbuf[20];
    f = fopen("001.txt", "r");
    fread(&ibuf, 1, sizeof(ibuf), f);
    fread(&fbuf, 1, sizeof(fbuf), f);
    fread(&cbuf, 1, sizeof(cbuf), f);
    printf("%d %f %s", ibuf, fbuf, cbuf);
    fclose(f);
    return 0;
}


#29 Коды символов и бинарный режим(«wb» «rb»)

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
int main()
{
    int i = 0;
    FILE *f;
    char c[3] = "AB";
    c[1] = 10;
    f = fopen("001.txt", "wb");
    fprintf(f, c);
    fclose(f);
    char buf[10] = "";
    f = fopen("001.txt", "rb");
    fread(buf, 1, sizeof(buf), f);
    fclose(f);
    for (i = 0;i<10;i++)
        printf("%d\n", buf[i]);
    return 0;
}    


#30 Функции ftell и fseek - положение курсора
Литералы: a, a+, r, r+, w, w+, r+b, r+t

#include <stdlib.h>
#include <stdio.h>
int main()
{
    FILE *f;
    f = fopen("001.txt", «r+»);
    fprintf(f, "ABC123");
    printf("%d\n", ftell(f));
    fseek(f, 2, SEEK_SET);
    fprintf(f, "++");
    char c[100];
    fseek(f, 0, SEEK_SET);
    if (fgets(c, 100, f) != NULL)
        printf(c);
    fclose(f);
    return 0;
}  

#include <stdlib.h>
#include <stdio.h>
int main()
{
    char c[5] = {"abcde"};
    FILE *f;
    f = fopen("001.txt", "wb+");
    fwrite(c, 1, sizeof(c), f);
    fseek(f, 4, SEEK_SET);               //4 отвечает за курсор/с какого символа будет выведен текст//
	char buf;
    while (!feof(f))
    {
        if (fread(&buf, 1, sizeof(buf), f) > 0)
            printf("%c\n", buf);
    }
    fclose(f);
    return 0;
}   


#31 Объединения

#include <stdlib.h>
#include <stdio.h>
union u1 {
    int x,y;
    char mas[4];
};
int main()
{
    union u1 a;
    a.x = 55;
    a.y = 22;
    a.mas[1] = 4;
    printf("%d %d\n", a.x, a.mas[0]);
    return 0;
} 


#32 Строки подробно

#include <stdlib.h>
#include <stdio.h>
int main()
{
    char *str = "";
    str = "123";
    str = malloc(10);
    sprintf(str, "%s", "45454");
    str[2] = "-";
    printf("%s\n", str);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main() {
    char str[100];
    snprintf(str, 100, "wewewe");
    char *str2;
    str2 = malloc(10);
    snprintf(str2, 10, "123456");
    snprintf(str, 100, "%s %c %s %f\n", str, 'A', str2, 3.14);
    snprintf(str2, 10, "%s %s", str2, str);
    printf("%s%s\n", str, str2);
    return 0;
}  

#include <stdio.h>
#include <stdlib.h>
typedef struct {
    int x, y, z;
    char name[50];
    char color[20];
} TBox;
int main()
{
    TBox box[3];
    for (int i=0; i<3; i++)
    {
        box[i].x = rand() % 100;
        box[i].y = rand() % 100;
        box[i].z = rand() % 100;
    }
    sprintf(box[0].name, "chair");
    sprintf(box[0].color, "green");
    sprintf(box[1].name, "table");
    sprintf(box[1].color, "red");
    sprintf(box[2].name, "something strange");
    sprintf(box[2].color, "blue");
    for (int i=0; i<3; i++)
        printf("name=%s\n\n x=%d\n y=%d\n z=%d\n color=%s\n",
               box[i].name, box[i].x, box[i].y, box[i].z, box[i].color);
    return 0;
} 


#33 Перечисления и перечисляемые константы

#include <stdlib.h>
#include <stdio.h>
enum color {clRed = 3, clGreen, clBlue = 8} clr;
enum mc {bigA = 'A', smB = 'b'};
/* typedef enum color TColor;
   enum создает перечисление */
int main()
{
    int a = clBlue;
    clr = clGreen;
    if (clr == clRed)
        printf("Red\n");
    else if (clr == clGreen)
        printf("Green\n");
    else if (clr == clBlue)
        printf("Blue\n");
    printf("%d %d %d\n", clr, a, clRed);
    printf("%d %c\n", bigA, smB);
    return 0;
}  

#include <stdlib.h>
#include <stdio.h>
typedef enum {oPlus, oMinus, oMult} toper;
int operation(int a, int b, toper oper)
{
    if (oper == oMinus) return a - b;
    else if (oper == oMult) return a * b;
    else return a + b;
}
int main()
{
    printf("%d\n", operation(10, 5, oPlus));
    printf("%d\n", operation(10, 5, oMinus));
    printf("%d\n", operation(10, 5, oMult));
    return 0;
}  


#34 Функции с переменным количеством аргументов

#include <stdlib.h>
#include <stdio.h>
void func(int a, int b, int c)
{
    printf("%d %d %d\n", &a, &b, &c);
    /*int *ptr = &a + 1;
    printf("%d\n", *(ptr++));*/
}
double sum(int cnt, ...)
{
    double res = 0;
    double *ptr = &cnt + 1;
    for (; cnt > 0; cnt--)
        res += *(ptr++);
    return res;
}
int main()
{
    func(10, 20, 30);
    return 0;
}  


#35 Среднее арифметическое

#include <stdlib.h>
#include <stdio.h>
#include <stdarg.h>
double sr(int cnt, ...)
{
    int i = 0;
    int res = 0;
    va_list ptr;
    va_start(ptr, cnt);
    for (i = 0; i < cnt; i++)
        res += va_arg(ptr, int);
    va_end(ptr);
    return res / (float)cnt;
}
int main()
{
    printf("%f\n", sr(5, 1, 2, 3, 4, 6));
    return 0;
}   

#include <stdlib.h>
#include <stdio.h>
#include <stdarg.h>
double sr(char *prm, ...)
{
    double res = 0;
    int cnt = 0;
    va_list ptr;
    va_start(ptr, cnt);
    while (*prm)
    {
        res += (*prm) == 'i' ? va_arg(ptr, int) : va_arg(ptr, double);
        cnt++;
        prm++;
    }
    va_end(ptr);
    return res / cnt;
}
int main()
{
    printf("%f\n", sr("iiddi", 1, 2, 3.333, 4.222, 5));
    return 0;
}  


#36 Системы счисления
//%o - восьмеричная система счисления//
//%x - 16ая система счисления//

#include <stdlib.h>
#include <stdio.h>
int main()
{
    unsigned char a = 12;     //десятичная система счисления//
    unsigned char b = 014;    //восьмеричная система счисления//
    unsigned char c = 0xC;    //16ая система счисления//
    unsigned char d = 0b1100; //двоичная система счисления//
    printf("%d\n%o\n%x\n%d\n", a, b, c, d);
    return 0;
}

// %x = 16ая система счисления //
// ~(тильда) = инверсия //
// << >> = сдвиг влево или вправо //
// & = И //
// | = ИЛИ //
// ^ = исключающее ИЛИ //

#include <stdlib.h>
#include <stdio.h>
int main()
{
    unsigned char a = ~0b1100;
    printf("%x\n", a);
    unsigned char b = 0b1100;
    b = b << 2;
    printf("%x\n", b);
    unsigned char c = 0b1100;
    c = c & 0b111;
    printf("%x\n", c);
    unsigned char d = 0b1100;
    d = d | 0b111;
    printf("%x\n", d);
    unsigned char e = 0b1100;
    e = e ^ 0b111;
    printf("%x\n", e);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int main()
{
    unsigned char a = 0xAA;
    a = a & 0x0f;
    printf("%x\n", a);
    unsigned char b = 0xAA;
    b = b | 0x0f;
    printf("%x\n", b);
    unsigned short c = (b << 8) | a;
    printf("%x\n", c);
    unsigned char d = 0xAA;
    if (d & 0x80)
        printf("%x\n", d);
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
struct {
    unsigned char a2 : 2;
    char b2 : 2;
    unsigned char a4 : 4;
    char b4 : 4;
} tmp;
int main()
{
    int i = 0;
    for (i = 0; i < 16; i++)
    {
        tmp.a2 = tmp.b2 = tmp.a4 = tmp.b4 = i;
        printf("%5d%5d%5d%5d\n", tmp.a2, tmp.b2, tmp.a4, tmp.b4);
    }
    return 0;
}


#37 Флаги
// | | | = флаги //

#include <stdlib.h>
#include <stdio.h>
enum {bold = 0b0001, it = 0b0010, underline = 0b0100};
union {
    struct {
        unsigned char isBold: 1;
        unsigned char isit: 1;
        unsigned char isUnderline: 1;
    };
    unsigned char flags;
} textPar;
int main()
{
    //char tp = bold | underline;//
    textPar.flags = it | underline | bold;
    if (textPar.isBold)
        printf("text is bold\n");
    if (textPar.isit)
        printf("text is it\n");
    if (textPar.isUnderline)
        printf("text is underline\n");
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
struct {
    unsigned char a : 1;
    unsigned char b : 2;
    unsigned char c : 3;
    unsigned char d : 4;
} tmp = {1, 0, 1, 0};
int main()
{
    printf("%d%d%d%d\n", tmp.a, tmp.b, tmp.c, tmp.d);
    if (tmp.a && tmp.c && !tmp.b && !tmp.d)
        printf("OK!\n");
    return 0;
}



#38 Аргументы командной строки
strtol преобразует строку в число

#include <stdlib.h>
#include <stdio.h>
int main(int argc, char *argv[])
{
    while (*argv)
        printf("-- %s --\n", *argv++);
    char *c;
    int i = strtol("123ddfdf", &c, 10);
    printf("%d  %s\n", i, c);
    getchar();
    return 0;
}   


#39 Константы const

#include <stdlib.h>
#include <stdio.h>
typedef struct {
    int const x;
    int *y;
} point;
int a = 33;
int main()
{
    point const p = {5, &a};
    // p.x = 7 - выдаст ошибку//
    *p.y = 77;
    printf("%d %d\n", p.x, *p.y);
    return 0;
}   

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int const mas[5] = {1, 2, 3, 4, 5};
    // mas[2] = 7 - выдаст ошибку//
    printf("%d\n", mas[2]);
    return 0;
}


#40 Оператор запятая

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int a;
    a = 5, a += 2;
    printf("%d\n", a);
    return 0;
}  

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int a, b;
    for (a = 5, b = 10; a < 10; a++, b += 10)
        printf("%d %d\n", a, b);
    return 0;
}


#41 Числовые литералы

#include <stdlib.h>
#include <stdio.h>
int main()
{
    float a = 1.33e2f;
    double b = 5E3;
    printf("%g %g\n", a, b);
    return 0;
}   


#42 Сложные объявления

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int mas[5];
    mas[3] = 7;
    printf("%d\n", mas[3]);
    int a = 33;
    int *mas2[5];
    mas2[2] = &a;
    printf("%d\n", *mas2[2]);
    typedef int tmas3[5];
    tmas3 * pmas3;
    pmas3 = &mas;
    printf("%d\n", (*pmas3)[3]);
    typedef int * tmas4[5];
    tmas4 * pmas4;
    pmas4 = &mas2;
    printf("%d\n", *(*pmas4)[2]);
    int mas5[5][5];
    mas5[1][3] = 100;
    printf("%d\n", mas5[1][3]);
    int (*pmas6)[5][5];
    pmas6 = &mas5;
    printf("%d\n", (*pmas6)[1][3]);
    int (*mas7[5])[5];
    mas7[1] = &mas;
    printf("%d\n", (*mas7[1])[3]);
    int (*(*mas8)[5])[5];
    mas8 = &mas7;
    (*mas8)[2] = &mas;
    printf("%d\n", (*(*mas8)[2])[3]);
    return 0;
}   

#include <stdlib.h>
#include <stdio.h>
typedef int tfunc1(int);
int func1(int x) {return x;}
tfunc1 * var1;
tfunc1 *func2() {return func1;}
tfunc1 **func3() {return &var1;}
int main()
{
    var1 = func1;
    printf("%d\n", var1(11));
    printf("%d\n", func2()(22));
    printf("%d\n", (*func3())(33));
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
int m[5] = {1, 2, 3, 4, 5};
int (*fumas())[] {return &m;}
int (*(*varm1)())[] = fumas;
int f1() {return 20;}
int f2() {return 77;}
int (*masfu2[2])() = {f1, f2};
int (*(*fumasfu3())[2])() {return &masfu2;}
int main()
{
    printf("%d\n", (*fumas())[2]);
    printf("%d\n", (*varm1())[4]);
    printf("%d\n", masfu2[0]());
    printf("%d\n", (*fumasfu3())[1]());
    return 0;
}

#include <stdlib.h>
#include <stdio.h>
typedef int * TmasP[5];
typedef TmasP * T2();
int k = 11;
TmasP *mas[5];
TmasP *func() {return &mas;}
T2 *masf[5];
int main()
{
    mas[3] = &k;
    masf[1] = func;
    printf("%d\n", *(*masf[1]())[3]);
    return 0;
}


#43 Двуменые и динамические массивы

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int j = 0;
    int i = 0;
    int w = 5;
    int h = 3;
    int **mas = 0;
    mas = malloc(sizeof(mas) * w);
    for (i = 0; i < w; i++)
        mas[i] = malloc(sizeof(**mas) * h);
    for (j = 0; j < h; j++)
        for (i = 0; i < w; i++)
            mas[i][j] = 100*j + i;
    
//h = 4;
    for (i = 0; i < w; i++)
        mas[i] = realloc(mas[i], sizeof(**mas) * h);//   увеличение/уменьшение высоты массива

//int ow = w;
w = 6;
if (ow < w)
{
    mas = realloc(mas, sizeof(*mas) * w);
    for (i = ow; i < w; i++)
        mas[i] = malloc(sizeof(**mas) * h);
} //   увеличение/уменьшение длины массива

    for (j = 0; j < h; j++)
        for (i = 0; i < w; i++)
            printf("%d\t%s", mas[i][j], (i == w - 1) ? "\n" : "");
    for (i = 0; i < w; i++)
        free(mas[i]);
    free(mas);
    return 0;
}    

Псевдо двумерный динамический массив:

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int j = 0;
    int i = 0;
    int w = 5;
    int h = 3;
    int *mas = 0;
    mas = malloc(sizeof(*mas) * w * h);
    for (j = 0; j < h; j++)
        for (i = 0; i < w; i++)
            mas[j * w + i] = 100*j + i;
    /*h = 2;
    mas = realloc(mas, sizeof(*mas) * w * h); увеличение/уменьшение высоты*/
    for (j = 0; j < h; j++)
        for (i = 0; i < w; i++)
            printf("%d\t%s", mas[j * w + i], (i == w - 1) ? "\n" : "");
    free(mas);
    return 0;
} 

Отличие статического массива от динамического массива:

#include <stdlib.h>
#include <stdio.h>
int main()
{
    int i = 0;
    int mas[5] = {1, 2, 3, 4, 5};
    int *d = malloc(sizeof(*d) * 5);
    for (i = 0; i < 5; i++)
        d[i] = i + 11;
    for (i = 0; i < 5; i++)
        printf("%d  %d\n", mas[i], d[i]);
    printf("\n");
    printf("%d\n", &mas);
    printf("%d\n", mas);
    printf("%d\n", &d);
    printf("%d\n", d);
    return 0;
}   

Указатель на динамический массив:

#include <stdlib.h>
#include <stdio.h>
int i = 0;
void fpd(int **m)
{
    printf("%d  %d\n", m, *m);
    for (i = 0; i < 5; i ++)
        printf("%d\n", (*m)[i]);
}
int main()
{
    int mas[5] = {1, 2, 3, 4, 5};
    int *d = malloc(sizeof(*d) * 5);
    for (i = 0; i < 5; i++)
        d[i] = i + 11;
    for (i = 0; i < 5; i++)
        printf("%d  %d\n", mas[i], d[i]);
    printf("\n");
    void *p = mas;
    fpd(&p);
    return 0;
} 

Реверс динамического массива

#include <stdio.h>
void swap(int ar[], int j, int k)
{
  int temp;
  temp  = ar[j];
  ar[j] = ar[k];
  ar[k] = temp;
}
void reverse(int array[], int size)
{
   int i;
   double mean=0.0;
   for (i=0; i<size/2; i++)
     swap(array, i, (size-i-1));
}
int main()
{
  int  line[] = {5, 6, 2, 4, 9, 2, 1};
  int sizeLine = sizeof(line)/sizeof(line[0]);
  int i;
  printf("Begin array:\n");
  for (i=0; i<sizeLine; i++)
    printf("[%d]=%d\t",i,line[i]);
  reverse(line, sizeLine);
  printf("\nResult array:\n");
  for (i=0; i<sizeLine; i++)
    printf("[%d]=%d\t",i,line[i]);

  return 0;
} 


#44 Объявление функции

#include <stdlib.h>
#include <stdio.h>
void func(int a);
int main()
{
    func(5);
    return 0;
}
void func(int a) //заголовок функции//
{
    printf("%d\n", a); //тело функции//
} 


#45 Расположение структуры

#include <stdlib.h>
#include <stdio.h>
struct S1;
void useS1();
int main()
{
    useS1();
    return 0;
}
struct S1
{
    int x;
};
void useS1()
{
    struct S1 o;
    o.x = 7;
    printf("%d", o.x);
}     

#include <stdlib.h>
#include <stdio.h>
typedef struct S1 T1;
struct S1
{
    int x;
    T1 *next;
};
int main()
{
    struct S1 a;
    a.x = 3;
    printf("%d\n", a.x);
    return 0;
}


#46 Безымянные переменные

#include <stdio.h>
#include <stdlib.h>
typedef struct {int x, y, z;} point;
int main()
{
    printf("%d\n", (int){5});
    printf("%d\n", (int[3]){[1] = 2, 3}[2]);
    printf("%d\n", (point){}.y);
    return 0;
}  

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
typedef struct {int x, y, z;} point;
point f1(){return(point){22, 33, 44};}
int main()
{
    point p;
    p = f1();
    printf("%d %d %d\n", p.x, p.y, p.z);
    return 0;
}

#include <stdio.h>
#include <stdlib.h>
typedef struct {
    int x;
    int mas[10];
    int y;
} obj;
int i = 0;
int main()
{
    obj o = {10, {[7] = 3, 4, 5}, 20};
    //o = (obj){111, {5, 6, 7}, 222};  безымянная переменная//
    printf("%d %d   ", o.x, o.y);
    for (i=0;i<10;i++)
        printf("%d ", o.mas[i]);
    return 0;
} 


#include <stdio.h>
#include <stdlib.h>
int main()
{
    int (*a)[3] = (int[3]){1, 2, 3};
    printf("%d %d %d\n", (*a)[0], (*a)[1], (*a)[2]);
    return 0;
}


#47 Функции exit/atexit/abort

#include <stdio.h>
#include <stdlib.h>
void func()
{
    printf("AAAA\n");
    exit(7);
    printf("BBBB\n");
}
int main()
{
    printf("%d\n", 5);
    func();
    printf("%d\n", 7);
    return 0;
}     

#include <stdio.h>
#include <stdlib.h>
void end()
{
    printf("END\n");
}
int main()
{
    atexit(end);
    printf("some code\n");
    //abort();//
    exit(7);
    return 0;
} 


#48 Модуль assert

#include <stdio.h>
#include <stdlib.h>
//#define NDEBUG макрос отключает assert//
#include <assert.h>
void errFunc(int a)
{
    int i[10] = {};
    assert(a >= 0 && a < 10);
    printf("%d\n", i[a]);
}
int main()
{
    errFunc(9);
    return 0;
}   


#49 Куб числа

#include <stdio.h>
int cube(int x)
{
    int y;
    y = x*x*x;
    return y;
}
void main()
{ int i;
    for (i = 1; i <= 10; i++)
        printf("%2d %4d\n", i, cube(i));
    getchar();
} 












