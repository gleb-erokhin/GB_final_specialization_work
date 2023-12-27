# GB_final_specialization_work


<details>
    <summary>### Задание №8</summary>

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

<details>
    <summary>### Задание №9</summary>

```sql
```

<details>
    <summary>### Задание №8</summary>

```sql
```