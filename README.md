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

### INSERTING DATA

INSERT INTO cats(name, age) VALUES (’Jetson’ , 7);

INSERT INTO cats(name,age) VALUES ('Meatball',5),('Turkey',1),('PotatoFace',15);

\를 넣어서 특수문자를 넣을 수 있다. (’mario\’s pizza’)

CREATE TABLE cats2 (

name VARCHAR(100) NOT NULL,

age INT NOT NULL

);

CREATE TABLE cats3(

name VARCHAR(100) DEFAULT ‘unnamed’,

age INT DEFAULT 99

);



**default 값은 null 값을 넣어도 된다.**

CREATE TABLE cats4 (

name VARCHAR(20) NOT NULL DEFAULT 'unnamed',

age INT NOT NULL DEFAULT 99

);

CREATE TABLE unique_cats (
cat_id INT PRIMARY KEY,
name VARCHAR(100) NOT NULL,
age INT NOT NULL
);

CREATE TABLE unique_cats (
cat_id INT AUTO_INCREMENT,
name VARCHAR(100) NOT NULL,
age INT NOT NULL,

PRIMARY KEY(cat_id)
);

**Primary Key는 not null이다**

## CRUD Basic

SELECT cat_id FROM cats;
SELECT name,breed FROM cats;
SELECT name,age FROM cats WHERE breed = 'Tabby';
SELECT cat_id,age FROM cats WHERE cat_id = age;

### Aliases

SELECT name AS kittyName FROM cats;

### Update

UPDATE cats SET breed= 'shortair' WHERE breed='tabby';

//where 쓰지 않으면 전체 업데이트됨

### Delete

DELETE FROM cats WHERE name = 'Egg';

DELETE FROM cats