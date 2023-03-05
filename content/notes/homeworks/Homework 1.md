---
title: Домашна Работа По Алгоритми 1
tags:
- homeworks-algorithms
---

## 1. Препишете определението за алгоритъм от лекцията.

> **Алгоритъмът** е такова крайно, дискретно (постъпково), детерминирано преобразование, което приложено над произволен допустим набор от стойности на входа на множеството довежда до получаването на единствен набор от допустими стойности на изходното множество.


## 2. Съставете схеми на Базовите Елементи на Управление с техните наименования.

### Безусловен Преход


![Безусловен Преход](notes/assets/unconditional-transition.png)

***
### Условен преход

![Условен преход](notes/assets/conditional-transition.png)

## 3. Съставете **схемата на управление** за алгоритъма за RAM машина от лекцията


![Ram macine algorithm](notes/assets/ram-machine-algorithm.png)

```C++
#include <iostream>  
  
using namespace std;  
  
int main() {  
    int firstNumber = 2, secondNumber = 5, result = 0, counter = 0;  
  
    result = secondNumber;  
  
    while (counter < firstNumber) {  
        result++;  
        counter++;  
    }  
  
    cout << firstNumber << " + " << secondNumber << " = " << result << endl;  
}
```


## 4. Съставете **схема на управление** за алгоритъма на Евклид.

![Euclid Algorith](notes/assets/euclid-algorith.png)