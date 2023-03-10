# **Базы данных и SQL (семинары)**

![Attention](images/attention.png) В качестве СУБД использовалась Postgres!


## **Урок 1. Установка СУБД, подключение к БД, просмотр и создание таблиц**
**Задание 1.** Создайте таблицу с мобильными телефонами, используя графический интерфейс. Необходимые поля таблицы: product_name (название товара), manufacturer (производитель), product_count (количество), price (цена). Заполните БД произвольными данными.

**Решение:**

*Создание*
```
CREATE TABLE geekbrains.phones (
	product_name varchar(20) NOT NULL,
	manufacturer varchar(20) NOT NULL,
	product_count int4 NOT NULL,
	price numeric(8, 2) NOT NULL
);
```
*Заполнение*

```
INSERT INTO geekbrains.phones VALUES ('POCO M5','Xiaomi',2,13900.00);
INSERT INTO geekbrains.phones VALUES ('Galaxy S23 Ultra','Samsung',5,102990.00);
INSERT INTO geekbrains.phones VALUES ('Galaxy S23 Ultra','Samsung',5,102990.00);
INSERT INTO geekbrains.phones VALUES ('Galaxy Note 20 Ultra','Samsung',4,73990.00);
INSERT INTO geekbrains.phones VALUES ('iPhone 14 Pro','Apple',1,104190.00);
INSERT INTO geekbrains.phones VALUES ('iPhone 7','Apple',3,10400.00);
INSERT INTO geekbrains.phones VALUES ('iPhone 8','Apple',1,14500.00);
```

**Задание 2.** Напишите SELECT-запрос, который выводит название товара, производителя и цену для товаров, количество которых превышает 2

**Решение:**
```
SELECT product_name,manufacturer,price FROM geekbrains.phones WHERE product_count>2;
```

**Задание 3.** Выведите SELECT-запросом весь ассортимент товаров марки “Samsung”

**Решение:**
```
SELECT * FROM geekbrains.phones WHERE manufacturer='Samsung';
```
**Задание 4.*** С помощью SELECT-запроса с оператором LIKE / REGEXP найти:

- Товары, в которых есть упоминание "iPhone"
```
SELECT * FROM geekbrains.phones WHERE product_name LIKE '%iPhone%' OR manufacturer LIKE '%iPhone%';
```
- Товары, в которых есть упоминание "Samsung"
```
SELECT * FROM geekbrains.phones WHERE product_name LIKE '%iPhone%' OR manufacturer LIKE '%iPhone%';
```
- Товары, в названии которых есть ЦИФРЫ
```
SELECT * FROM geekbrains.phones WHERE product_name ~'[0-9]';
```
Товары, в названии которых есть ЦИФРA "8"
```
SELECT * FROM geekbrains.phones WHERE product_name ~'[8]';
```