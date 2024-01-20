# Задание №1. 
# Оптимальное тестирование поля ввода возраста, от 1 до 100, при этом система позволяет получить доступ к фильму только если пользователю есть хотя бы 18 лет (≥18)

## Позитивные проверки

#### Тест-кейс №GP001. Проверка граничного значения "18"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 18
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система позволяет получить доступ к фильму

---
#### Тест-кейс №GP002. Проверка граничного значения "17"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 17
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система не позволяет получить доступ к фильму

---
#### Тест-кейс №GP003. Проверка граничного значения "1"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 1
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система не позволяет получить доступ к фильму

---
#### Тест-кейс №GP004. Проверка среднего значения "8"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 8
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система не позволяет получить доступ к фильму

---
#### Тест-кейс №GP005. Проверка граничного значения "19"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 19
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система позволяет получить доступ к фильму

---
#### Тест-кейс №GP006. Проверка среднего значения "50"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 50
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система позволяет получить доступ к фильму 

---
#### Тест-кейс №GP007. Проверка граничного значения "99" 
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 99
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система позволяет получить доступ к фильму 

---
#### Тест-кейс №GP008. Проверка среднего значения "100"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 100
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100, ≥18
Система позволяет получить доступ к фильму

---
## Негативные проверки

#### Тест-кейс №GP009. Оставить поле ввода возраста пустым
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст"  ничего не вводить
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не принимает пустое поле

---
#### Тест-кейс №GP010. Проверка граничного значения "0"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 0
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP011. Проверка граничного значения "101"
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 101
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP012. В поле ввода возраста ввести не целое число с (.)
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 0.5
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP013. В поле ввода возраста ввести не целое число с (,)
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 0,5
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP014. В поле ввода возраста ввести не целое число с (/)
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 0/5
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP015. В поле ввода возраста ввести кирилицу
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - кп
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP016. В поле ввода возраста ввести латиницу
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - ok
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст   

---
#### Тест-кейс №GP017. В поле ввода возраста ввести иероглифы
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - 漢字
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP018. В поле ввода возраста ввести спецсимволы
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - *=
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP019. В поле ввода возраста ввести буквы и цифры
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - а2
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 

---
#### Тест-кейс №GP020. В поле ввода возраста ввести отрицательное число
<u>Предшествующие условия:</u>  
 Открыта страница  где доступно поле для ввода возраста

<u>Шаги:</u>  
- в поле "Возраст" ввести - -1
- нажать кнопку "Далее"

<u>Ожидаемый результат: </u>  
Допустимые значения — целые числа от 1 до 100  
Система не приняла возраст 