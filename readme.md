# Лабораторная работа №9
## Задание 1. Выберите базу данных, с которой вы планируете работать:

Для выполнения лабораторной работы я выбрала `mysql (mariadb)` ,так как она подходит для проектов среднего и крупного масштаба,
где необходима поддержка высокой производительности и
масштабируемости. MariaDB, форк MySQL (то есть основана на MySQL),
также предоставляет дополнительные функции и улучшенную
производительность.

## Задание 2. Создайте базу данных blog и создайте две базы данных users и comments с помощью языка DDL (CREATE TABLE).

Структура баз данных:

* users:

![](./Screenshot%202024-04-04%20135302.png)

```sql
CREATE TABLE IF NOT EXISTS User
(
    id      INT AUTO_INCREMENT PRIMARY KEY,
    name    VARCHAR(255) NOT NULL,
    surname VARCHAR(255) NOT NULL,
    email   VARCHAR(255) NOT NULL
);
```

* comments:

![](./Screenshot%202024-04-04%20135335.png)

```
CREATE TABLE IF NOT EXISTS Comments
(
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    comment TEXT NOT NULL,
    FOREIGN KEY (user_id) REFERENCES User(id)
);
```

## Экспортируем базу данных `blog.sql` в папку `/data`

## Примечание 

Для выполения данной лабораторной работы я использовала OpenServer. Эта база данных предполагает хренение данных пользователей и их коммернтариев. 