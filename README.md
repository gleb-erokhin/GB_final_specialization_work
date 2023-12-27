# GB_final_specialization_work


<details>
    <summary>Задание №8</summary>

```sql
-- Создаем базу данных
CREATE DATABASE People_friends;

-- Создем родительский класс с видами животных
CREATE TABLE Parent_class (
  id INT PRIMARY KEY AUTO_INCREMENT,
  species VARCHAR(50)
);

-- Наполняем таблицу видами
insert into parent_class (species)
values ('вьючные'),
		('домашние');

-- Создаем таблицу Домашних животных
CREATE TABLE Home_animals (
  id INT PRIMARY KEY AUTO_INCREMENT,
  species_name VARCHAR(50),
  class_id INT,
  FOREIGN KEY (class_id) REFERENCES Parent_class(id)
);

-- Наполняем таблицу доашними животнми
insert into home_animals (species_name, class_id)
values ('кошки', 2),
	   ('собаки', 2),
	   ('хомяки', 2);
	  
-- Создаем таблицу для вьючных животных
CREATE TABLE Pack_animals (
  id INT PRIMARY key AUTO_INCREMENT,
  species_name VARCHAR(50),
  class_id INT,
  FOREIGN KEY (class_id) REFERENCES parent_class(id)
);

-- Наполняем таблицу животными
insert into pack_animals (species_name, class_id)
values ('лошади', 1),
	   ('ослы', 1),
	   ('верблюды', 1);
```
</details>


<details>
    <summary>Задание №9</summary>

```sql
-- Домашние животные  

	  
-- Создаем таблицу Собаки
CREATE TABLE Dogs (
  id INT PRIMARY key AUTO_INCREMENT,
  name VARCHAR(50),
  orders VARCHAR(50),
  birdth DATE,
  class_id int,
  FOREIGN KEY (class_id) REFERENCES home_animals(id)
);


-- Наполняем таблицу Собаки командами
INSERT INTO dogs ( name, orders, birdth, class_id)
VALUES ('Барбос', 'Дай лапу', '2022-01-21', 2),
       ('Полкан', 'Лежать', '2010-03-08', 2);

      
-- Создаем таблицу кошки
CREATE TABLE Cats (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50),
  orders VARCHAR(50),
  birdth DATE,
  class_id int, 
  FOREIGN KEY (class_id) REFERENCES Home_animals(id)
);


-- наполняем таблицу кошки командами
INSERT INTO cats (id, name, orders, birdth, class_id)
VALUES (1, 'Симба', 'Кис-кис', '2020-01-27', 1),
       (2, 'Делайла', 'Давай играть', '2019-03-08', 1);
      
      
 -- Создаем таблицу хомяки     
CREATE TABLE Hamster (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50),
  orders VARCHAR(50),
  birdth DATE,
  class_id int,
  FOREIGN KEY (class_id) REFERENCES Home_animals(id)
);


-- Наполняем таблицу хомяки командами
INSERT INTO hamster ( name, orders, birdth, class_id)
VALUES ('Кулик', 'Спать', '2023-01-21', 3),
       ('Хаги', 'Бегать', '2002-03-08', 3);


-- Вьючные животные
CREATE TABLE Horses (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50),
  orders VARCHAR(50),
  birdth DATE,
  class_id int,
  FOREIGN KEY (class_id) REFERENCES Pack_animals(id)
);


-- Наполняем таблицу Лошади
INSERT INTO horses ( name, orders, birdth, class_id)
VALUES ('Скорость', 'Но', '2018-01-21', 1),
       ('Грей', 'Бррррр', '2023-03-08', 1);


-- Создаем таблицу Верблюды
CREATE TABLE Camels (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50),
  orders VARCHAR(50),
  birdth DATE,
  class_id int, 
  FOREIGN KEY (class_id) REFERENCES Pack_animals(id)
);


-- Наполняем таблицу верблюды командами
INSERT INTO camels ( name, orders, birdth, class_id)
VALUES ('Зефир', 'Но, пошел', '2019-09-01', 3),
       ('Багдад', 'На месте', '2020-11-12', 3),
       ('Скорость', 'Ждать', '2021-04-05', 3);


-- Создаем таблицу Обезьяны
CREATE TABLE Donkeys (
  id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50),
  orders VARCHAR(50),
  birdth DATE,
  class_id int,
  FOREIGN KEY (class_id) REFERENCES Pack_animals(id)
);


-- Наполняем таблицу Ослы
INSERT INTO donkeys ( name, orders, birdth, class_id)
VALUES ('Вася', 'Есть', '2017-01-21', 2),
       ('Иван', 'Прыгать', '2005-03-08', 2);

```
</details>

<details>
    <summary>Задание №10</summary>

```sql
-- Удаление таблицы camel
DELETE FROM camels;

-- Объеденяем таблицы Лошади и Ослы
SELECT Name, orders, birdth FROM horses
UNION SELECT  Name, orders, birdth FROM donkeys;

![Результат запроса](https://github.com/gleb-erokhin/GB_final_specialization_work/blob/master/10.jpg)

```
</details>


<details>
    <summary>Задание №11</summary>

```sql
-- Создаем временную таблицу животные, для хранения промежуточных данных
CREATE TEMPORARY TABLE animals AS 
SELECT *, 'Лошади' as species FROM horses
UNION SELECT *, 'Ослы' AS species FROM donkeys
UNION SELECT *, 'Собаки' AS species FROM dogs
UNION SELECT *, 'Кошки' AS species FROM cats
UNION SELECT *, 'Хомяки' AS species FROM hamster;


-- Создаем таблицу молодые животные
CREATE TABLE no_old_animal AS
SELECT Name, orders, birdth, species, TIMESTAMPDIFF(MONTH, birdth, CURDATE()) AS Age_in_month
FROM animals WHERE birdth BETWEEN ADDDATE(curdate(), INTERVAL -3 YEAR) AND ADDDATE(CURDATE(), INTERVAL -1 YEAR);
 
SELECT * FROM no_old_animal;

```
</details>


<details>
    <summary>Задание №10</summary>

```sql
```
</details>


<details>
    <summary>Задание №10</summary>

```sql
```
</details>


<details>
    <summary>Задание №10</summary>

```sql
```
</details>