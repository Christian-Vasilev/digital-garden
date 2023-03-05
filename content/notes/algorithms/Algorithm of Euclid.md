---
title: Алгоритъм на Евклид
tags:
- algorithms
---

## Дефиниция

> Алгоритъмът на Евклид се използва за намирането на най-големият общ делител (НОД) на две естествени числа. Той е един от най-първиет публикувани алгоритми.
> 
> Взимайки двете дадени на входа на алгоритъма числа a и b, провери дали b е равно на 0.
> 
> Ако да, числото a е търсеният най-голям общ делител.
> Ако не, повтори процеса, като използваш за входни данни b и остатъка, получен при деленето a на b (означаван по-долу с a mod b)


[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/fwuj4yzoX1o/0.jpg)](https://www.youtube.com/watch?v=fwuj4yzoX1o)


![Euclid Algorith](notes/assets/euclid-algorith.png)



## Алгоритъм без цикъл

![Euclid Algorith Without Iterations](notes/assets/euclid-alorith-without-iterations.png)

### Code

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

### Result
```bash
Enter First Number

20

Enter Second Number

40

The GCD of 20 AND 40 = 20
```