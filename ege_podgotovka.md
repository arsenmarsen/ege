###  Подготовка к Егэ

### Задание номер 1 - ассиметричный граф
1. смотрим на количество дорог исходящих из города - сопоставляем со схемой
2. обращаем внимание на геометрические фигуры образованные путями городов

### Задание номер 2 - логические функции

1. помнить логические операторы (и-или-следование)

<img width="563" alt="Снимок экрана 2024-04-20 в 15 58 41" src="https://github.com/arsenmarsen/ege/assets/167619428/3fce903f-c6e3-4d6b-b641-4514e506c82d">

2) Пример кода как решать на питоне

```
print('X Y W F')
for x in range(0,2):
  for y in range(0,2):
    for w in range(0,2):
      if ((x<=y)and(w or not(w))) == 1:
        print(x,y,w,1)

```
### Задание номер 10 - поиск информации в тексте
1. Внимательно читать задание
2. не сразу записывать ответ, проверить результат с результатом поиска(посмотреть в текст)
3. открыть в редакторе поиск/замена открыть параментры для уточнения поиска
   
### Задание номер 3 - поиск в экселевских таблицах
1. внимательно читаем задание
2. после фильтрации всегда копируем в другую таблицу(номера строк фильтрация не учитывает) получили 6231,  а на самом деле - 1027


### Задание номер 4 - неравномерное кодирование информации
1. условие фано - никакое кодовое слово не является началом другого( тоесть строим бинарное дерево)

<img width="778" alt="Screenshot 2024-04-20 at 17 29 03" src="https://github.com/arsenmarsen/ege/assets/167619428/1a3f35c2-e2ba-4f76-89fb-1f406a20d81f">

2. составляем в питоне формулу для подстановки значений(если надо)
3. пробуем несколько вариантов,берем нужный,учитываем вес кажого элемента(даем тяжелому элементу количество бит поменьше)
<img width="1474" alt="Снимок экрана 2024-04-20 в 17 31 52" src="https://github.com/arsenmarsen/ege/assets/167619428/61b88af9-c322-4ad1-9668-07cd893e91e2">

### Задание номер 8 - подсчет комбинаций 
1. x система - цифры от нуля до x-1
2. перевод десятичной системы в x нужно написать функцию:
```
def convert_to(number, base, upper=False):
    digits = '0123456789abcdefghijklmnopqrstuvwxyz'
    if base > len(digits): return None
    result = ''
    while number > 0:
        result = digits[number % base] + result
        number //= base
    return result.upper() if upper else result
```
3. 8миричная - oct(x),hex(x)

Код решения
```
def convert_to(number, base, upper=False):
    digits = '0123456789abcdefghijklmnopqrstuvwxyz'
    if base > len(digits): return None
    result = ''
    while number > 0:
        result = digits[number % base] + result
        number //= base
    return result.upper() if upper else result
    
g = 0
for a in range(16807,117649):
  astr = convert_to(a, 7)
  if astr.count('0') == 1:
    #print(astr)
    ch = 0
    ch += astr.count('2')
    ch += astr.count('4')
    ch += astr.count('6')

    if ch%2 == 0:
      #print(astr)
      #print(ch)
      g += 1

print(g)
```






