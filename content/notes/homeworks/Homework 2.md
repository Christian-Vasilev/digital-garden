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
  
using namespace std;  
  
int gcd(unsigned a, unsigned b);  
  
int gcd(unsigned a, unsigned b) {  
    if (b == 0) {  
        return a;  
    }  
  
    return gcd(b, a % b);  
}  
  
int main() {  
    unsigned a, b;  
  
    cout << "Enter First Number" << endl;  
    cin >> a;  
  
    cout << "Enter Second Number" << endl;  
    cin >> b;  
  
    unsigned result = gcd(a, b);  
  
    cout << "The GCD of " << a << " AND " << b << " = " << result << endl;  
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
  
using std::string;  
  
int print(unsigned, unsigned, string);  
  
int print(unsigned *info, unsigned size, string label) {  
    for (int i = 0; i < size; i++) {  
        std::cout << std::setw(4) << info[i];  
    }  
    std::cout << std::setw(4) << label << std::endl;  
  
    return 1;  
}  
  
int main() {  
    unsigned size = 4;  
    unsigned numbers[4] = {5, 6, 7, 8};  
    unsigned moreNumbers[4] = {2, 3, 4, 5};  
  
    unsigned carry = 0;  
    unsigned sum[4];  
    unsigned remainder[4];  
  
    for (int i = 0; i < size; i++) {  
        sum[i] = numbers[i] + moreNumbers[i];  
        remainder[i] = sum[i] % 10 != sum[i] ? sum[i] % 10 : 0;  
  
        carry += sum[i] + remainder[i];  
    }  
  
    print(numbers, size, "A");  
    print(moreNumbers, size, "B");  
    print(sum, size, "SUM");  
    print(remainder, size, "REM");  
  
  
    std::cout << "TOTAL SUM - " << carry << std::endl;  
}
```

### Резултат
```bash
g++ main.cpp && ./a.out

   5   6   7   8   A

   2   3   4   5   B

   7   9  11  13 SUM

   0   0   1   3 REM
```
