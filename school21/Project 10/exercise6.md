# Создание SQL-запросов

## 1. Вывести количество всех записей таблице Products . Столбец, в котором выводится число, необходимо назвать products_count

#### Запрос:
```SELECT COUNT(*) AS products_count FROM Products;```
#### Скрин ответа из БД:
[![01sql.png](https://i.postimg.cc/QCqLRpQV/01sql.png)](https://postimg.cc/JHtdXHdW)

---

## 2. Вывести все записи из таблицы Suppliers , у которых указана страна Germany 

#### Запрос:
```SELECT * FROM Suppliers WHERE Country = 'Germany'```
#### Скрин ответа из БД:
[![02sql.png](https://i.postimg.cc/J4SBdZhR/02sql.png)](https://postimg.cc/mtNDPcMn)

---

## 3. Вывести все записи из таблицы OrderDetails , у которых количество товара (Quantity) находится в диапазоне от 20 до 35

#### Запрос:
```SELECT * FROM OrderDetails WHERE Quantity BETWEEN 20 AND 35;```
#### Скрин ответа из БД:
[![03sql.png](https://i.postimg.cc/KzQM9W1W/03sql.png)](https://postimg.cc/fttyyBj7)

---
## 4. Вывести первые 5 записей из таблицы Products с CategoryID = 1 

#### Запрос:
```SELECT * FROM Products WHERE CategoryID = 1 ORDER BY CategoryID LIMIT 5;```
#### Скрин ответа из БД:
[![04sql.png](https://i.postimg.cc/ncXDk0pd/04sql.png)](https://postimg.cc/KRyjc7KL)
---
## 5. Вывести имена всех работников (таблица Employees)

#### Запрос:
```SELECT FirstName, LastName FROM Employees;```
#### Скрин ответа из БД:
[![05sql.png](https://i.postimg.cc/G37DGZw8/05sql.png)](https://postimg.cc/mh9hGprB)
---
## 6. Вывести OrderID и ShipperID из таблицы Orders , gредварительно отсортировав записи по полю ShipperID (по возрастанию)

#### Запрос:
```SELECT OrderID, ShipperID FROM Orders ORDER BY ShipperID ASC;```
#### Скрин ответа из БД:
[![06sql.png](https://i.postimg.cc/L5XZGVf8/06sql.png)](https://postimg.cc/BLr6KHMr)
---
## 7. Вывести последнюю запись из таблицы Customers . Запрос не должен зависеть от данных внутри самой записи, то есть если добавится новая запись, то запрос должен вывести уже её.

#### Запрос:
```SELECT * FROM Customers ORDER BY CustomerID DESC LIMIT 1;```
#### Скрин ответа из БД:
[![07sql.png](https://i.postimg.cc/x84bQbyy/07sql.png)](https://postimg.cc/CnbKH52z)
---
