# Linux C 程式設計 Part 1: 範例學習

## 格式化輸入與輸出
### 輸入與輸出: printf() 與 scanf()
```c
#include <stdio.h>

int main() {
    int integerVar;
    float floatVar;

    printf("請輸入一個整數和一個浮點數：");
    scanf("%d %f", &integerVar, &floatVar);
    printf("您輸入的整數是：%d，浮點數是：%f\n", integerVar, floatVar);

    return 0;
}
```
這段程式碼展示了如何使用 `printf()` 和 `scanf()` 進行基本的輸入輸出。

## 各種運算
### 算術運算子（Arithmetic Operators）
```c
#include <stdio.h>

int main() {
    int a = 10, b = 4;

    printf("a + b = %d\n", a + b);
    printf("a - b = %d\n", a - b);
    printf("a * b = %d\n", a * b);
    printf("a / b = %d\n", a / b);

    return 0;
}
```
展示加減乘除的基本算術運算。

### 遞增和遞減運算子（Increment and Decrement Operators）
```c
#include <stdio.h>

int main() {
    int a = 10;

    printf("a++ = %d\n", a++);
    printf("++a = %d\n", ++a);
    printf("a-- = %d\n", a--);
    printf("--a = %d\n", --a);

    return 0;
}
```
展示遞增和遞減運算子的使用。

### 關係運算子（Relational Operators）
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20;

    printf("a > b = %d\n", a > b);
    printf("a < b = %d\n", a < b);
    // 其他關係運算子的示例

    return 0;
}
```
展示大於、小於等關係運算子的使用。

### 邏輯運算子（Logical Operators）
```c
#include <stdio.h>

int main() {
    int a = 1, b = 0;

    printf("a && b = %d\n", a && b);
    printf("a || b = %d\n", a || b);
    printf("!a = %d\n", !a);

    return 0;
}
```
展示邏輯運算子 and, or, not 的使用。

### 位元運算子（Bitwise Operators）
```c
#include <stdio.h>

int main() {
    int a = 12, b = 25;

    printf("a & b = %d\n", a & b);
    printf("a | b = %d\n", a | b);
    printf("a ^ b = %d\n", a ^ b);

    return 0;
}
```
展示位元運算的使用。

### 運算子的優先順序
```c
#include <stdio.h>

int main() {
    int a = 5, b = 10, c;

    c = a + b * 2;
    printf("a + b * 2 = %d\n", c);

    return 0;
}
```
展示運算子的優先順序：先乘除後加減。


## 流程控制
### 迴圈設計1 (loop_1)
#### for 迴圈
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("%d ", i);
    }
    return 0;
}
```
展示 for 迴圈的基本用法。

#### while 迴圈
```c
#include <stdio.h>

int main() {
    int i = 0;
    while (i < 5) {
        printf("%d ", i);
        i++;
    }
    return 0;
}
```
展示 while 迴圈的基本用法。

#### do...while 迴圈
```c
#include <stdio.h>

int main() {
    int i = 0;
    do {
        printf("%d ", i);
        i++;
    } while (i < 5);
    return 0;
}
```
展示 do...while 迴圈的基本用法。

### 迴圈設計2 (loop_2)
#### break 敘述
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) break;
        printf("%d ", i);
    }
    return 0;
}
```
使用 break 中斷迴圈。

#### continue 敘述
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        if (i == 5) continue;
        printf("%d ", i);
    }
    return 0;
}
```
使用 continue 跳過當前迴圈的迭代。

#### 多重迴圈
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("(%d, %d) ", i, j);
        }
        printf("\n");
    }
    return 0;
}
```
展示多重迴圈的用法。

## 函數
### 函數呼叫: call by value vs call by address
#### Call by Value (傳值呼叫)
```c
#include <stdio.h>

void addTen(int a) {
    a += 10;
    printf("Inside addTen: %d\n", a);
}

int main() {
    int num = 5;
    addTen(num);
    printf("In main: %d\n", num);
    return 0;
}
```
展示傳值呼叫，調用函數時，實際參數的值被複製到形式參數。

#### Call by Address (傳址呼叫)
```c
#include <stdio.h>

void addTen(int *a) {
    *a += 10;
    printf("Inside addTen: %d\n", *a);
}

int main() {
    int num = 5;
    addTen(&num);
    printf("In main: %d\n", num);
    return 0;
}
```
展示傳址呼叫，調用函數時，傳遞變量地址，函數內的操作會影響實際參數。

### 遞迴函數
```c
#include <stdio.h>

int factorial(int n) {
    if (n == 0)
        return 1;
    else
        return n * factorial(n - 1);
}

int main() {
    int num = 5;
    printf("Factorial of %d is %d\n", num, factorial(num));
    return 0;
}
```
展示遞迴函數的使用，計算階乘。

