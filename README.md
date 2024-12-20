# **Создание языка программирования и компилятора**

## **Описание проекта**
Цель данной работы — разработка языка программирования с ключевыми словами на русском языке, а также создание компилятора, который будет транслировать программы на этом языке в эквивалентный код на языке C.

---

## **Особенности языка**
### **Типы данных**
1. `целое` — для хранения положительных целых чисел.
2. `строка` — для работы с текстовыми данными.
3. `карта` — ассоциативный массив, где ключи — строки, а значения — целые числа.

### **Ключевые слова**
- **Управляющие конструкции:**
  - `если`, `иначе`, `конец` — условные операторы.
  - `цикл`, `конец` — циклы.
- **Ввод/вывод:**
  - `ввод` — ввод данных с клавиатуры.
  - `вывод` — вывод данных на экран.

---

## **Пример программы на языке**
```plaintext
целое x = 10;  // Объявление целого числа с присваиванием
строка str = "Hello, world!";  // Объявление строки с присваиванием
карта phone_book[5];  // Объявление карты с размером

// Простое присваивание
x = 20;

// Вложенное условие
если x > 5 {
    если x > 10 {
        x = 100;
    } иначе {
        x = 1;
    }
}
```

---

## **Вывод генератора кода**
```plaintext
Лексер: распознано 85 токенов

Построенное AST:
Тип узла: 8, Значение: целое
  Тип узла: 6, Значение: x
  Тип узла: 0, Значение: =
    Тип узла: 6, Значение: x
    Тип узла: 7, Значение: 10
Тип узла: 8, Значение: строка
  Тип узла: 6, Значение: str
  Тип узла: 0, Значение: =
    Тип узла: 6, Значение: str
    Тип узла: 7, Значение: "Hello, world!"
Тип узла: 8, Значение: карта
  Тип узла: 6, Значение: phone_book
  Тип узла: 7, Значение: 5
Тип узла: 0, Значение: =
  Тип узла: 6, Значение: x
  Тип узла: 7, Значение: 20
Тип узла: 1, Значение: если
  Тип узла: 9, Значение: ==
    Тип узла: 6, Значение: x
    Тип узла: 7, Значение: 20
  Тип узла: 0, Значение: =
    Тип узла: 6, Значение: x
    Тип узла: 7, Значение: 30
Тип узла: 1, Значение: если
  Тип узла: 11, Значение: >
    Тип узла: 6, Значение: x
    Тип узла: 7, Значение: 5
  Тип узла: 1, Значение: если
    Тип узла: 11, Значение: >
      Тип узла: 6, Значение: x
      Тип узла: 7, Значение: 10
    Тип узла: 0, Значение: =
      Тип узла: 6, Значение: x
      Тип узла: 7, Значение: 100
  Тип узла: 2, Значение: иначе
    Тип узла: 0, Значение: =
      Тип узла: 6, Значение: x
      Тип узла: 7, Значение: 1

Сгенерированный код на C:
#include "map.h"
#include <stdio.h>

int main() {
    int x = 10;
    char* str = "Hello, world!";
    map phone_book[5];
    x = 20;
    if (x > 5) {
        if (x > 10) {
            x = 100;
        } else {
            x = 1;
        }
    }
    return 0;
}
```