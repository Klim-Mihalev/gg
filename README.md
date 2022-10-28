# gg
все основы на c

Калькулятор


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


Процедуры и функции

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


Массивы и циклы

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


Библиотеки/строки/языки/символы

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


Циклы

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


Массивы/матрицы

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


Заполнение всего столбца/строки

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


Макросы/cnt=5

#include <stdio.h>
#include <stdlib.h>
#define cnt 5
#define celoei int i = cnt
#define showi printf("%d\n", i)
int main()
{
    celoei;
    showi;
    return 0;
}  


Рандомные числа

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


Структуры/typedef

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


Вещественные числа/float

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


Atoi(int)/Atof(float)

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


Прикольный код 1

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


Указатели адреса/NULL

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


Указатель на структуру

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


Размер в байтах

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


Распределение памяти

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


Динамический массив/адресация памяти

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


Указатель на указатель

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


Поменять местами значения

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


Заполнение массива

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


Указатель на функцию

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


Тернарный оператор

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


Факториалы/последовательность ввода текста

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


Оператор выбора switch

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


Статическая переменная

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


Возведение в степень

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


Инициализация

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


Открытие файла/запись в файл/закрытие файла

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








