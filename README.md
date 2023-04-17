# Mysql


### Getting Started

터미널로 mysql 접속

mysql -u root -p

-u  mysql 사용자를 지칭하는 옵션

-p 패스워드

### Database 관리

SHOW DATABASES;

CREATE DATABASE <name>;

DROP DATABASE <name>;

USE DATABASE;

SELECT DATABASE(); // 현재 연결된 데이터베이스의 이름을 반환하는 MySQL 쿼리

### TABLE 관리

SHOW TABLES;

SHOW COLUMNS FROM <name>; // DESCRIBE <name> // DESC <name>

CREATE TABLE cats(
name varchar (50),
age int);

DROP TABLE <name>