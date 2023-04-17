---
title: Домашна Работа По Алгоритми 2
tags:
- homeworks-algorithms
---

## 1.  Съставете програма за алгоритъма на Евклид, в която няма оператор за цикъл.

![Euclid Algorith Without Iterations](notes/assets/euclid-alorith-without-iterations.png)

### Код

```C++
#include <iostream>  
  
int main() {  
    unsigned a, b, result;  
  
    std::cout << "Enter First Number" << std::endl;  
    std::cin >> a;  
  
    std::cout << "Enter Second Number" << std::endl;  
    std::cin >> b;  
  
  
    body:  
        result = a % b;  
  
        if (result != 0) {  
            goto end;  
        }  
  
        a = b;  
        b = result;  
  
        goto body;  
  
    end:  
  
    std::cout << "The GCD is " << result << std::endl;  
  
    return 0;  
}
```

### Резултат

```bash
Enter First Number

20

Enter Second Number

40

The GCD of 20 AND 40 = 20
```

## 2.  Съставете петте схеми на основните Конструкти на Управление

> Клоновете (_двуклон_ и _байпас_) и на Повторенията (цикли с предусловие, със следусловие и по брояч)


### Клонове

#### Байпас


![Bypass Operator](notes/assets/bypass-homework.png)

#### Двуклонов

![Bypass-with-condition](notes/assets/bypass-with-statement.png)

### Повторения

#### Цикли с предусловие

![Cycle with condition](notes/assets/cycle-with-before-condition.png)


#### Цикли със следусловие
![Cycle with after condition](notes/assets/cycle-with-after-condition.png)
#### Цикъл с вграден брояч

![Cycle with integrated counter](notes/assets/cycle-with-integrated-counter.png)

### 3.  Съставете схемата на управление за събиране на две числа (зададени с два вектора)

![Sum Numbers WIth Remainder Scheme](notes/assets/sum-numbers-with-remainder.png)

### 4.  Реализирайте съставената по предходната тачка програма и проверете дали работи за събиране на числа (представени като вектори) в десетичен код.

### Код

```C++
#include <iostream>  
#include <iomanip>  
const int SIZE = 4;  
  
using std::string;  
  
int print(unsigned, unsigned, string);  
  
int print(unsigned *info, unsigned size, string label) {  
    for (int i = 0; i < size; i++) {  
        std::cout << std::setw(4) << info[i];  
    }  
    std::cout << std::setw(4)    << label << std::endl;  
  
    return 1;  
}  
  
int main() {  
    unsigned numbers[SIZE] = {5, 6, 7, 8}; // 5678  
    unsigned moreNumbers[SIZE] = {5, 6, 7, 8}; // 2345  
  
    unsigned carry = 0;  
    unsigned sum[SIZE + 1];  
    unsigned remainder[SIZE];  
  
    for (int i = 0; i < SIZE; i++) {  
        int index = SIZE - (i + 1);  
        int summedNumbers = numbers[index] + moreNumbers[index] + carry;  
  
        sum[index] = summedNumbers % 10;  
        remainder[i] = summedNumbers / 10;  
  
        carry = remainder[i];  
    }  
  
    sum[0] = carry;  
  
    print(numbers, SIZE, "A");  
    print(moreNumbers, SIZE, "B");  
    print(sum, SIZE + 1, "SUM");  
    print(remainder, SIZE, "REM");  
}
```

### Резултат
```bash
g++ main.cpp && ./a.out

   5   6   7   8   A

   2   3   4   5   B

   8   0   2   3 SUM

   1   1   1   0 REM
```
