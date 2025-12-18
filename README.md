Домашнее задание к занятию «Работа с данными (DDL/DML)»
Ялова Л.В.


Задание можно выполнить как в любом IDE, так и в командной строке.

Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:

ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.


Скриншот 1: результат SELECT User, Host FROM mysql.user;
Скриншот 2: результат SHOW GRANTS FOR 'sys_temp'@'%';
Скриншот 3: результат SHOW TABLES; из базы sakila

```bash
CREATE USER 'sys_temp'@'%' IDENTIFIED BY 'password';
SELECT User, Host FROM mysql.user;
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%';
FLUSH PRIVILEGES;
SHOW GRANTS FOR 'sys_temp'@'%';
ALTER USER 'sys_temp'@'%' IDENTIFIED WITH mysql_native_password BY 'password';
USE sakila;
SHOW TABLES;
```