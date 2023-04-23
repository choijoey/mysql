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

### 연습
create database shirts_db;
use shirts_db;
create table shirts(
shirt_id int auto_increment primary key,
article varchar(50),
color varchar(50),
shirt_size varchar(50),
last_worn int
);

insert into shirts(article,color,shirt_size,last_worn) values ('t-shirt', 'white', 'S', 10),
('t-shirt', 'green', 'S', 200),
('polo shirt', 'black', 'M', 10),
('tank top', 'blue', 'S', 50),
('t-shirt', 'pink', 'S', 0),
('polo shirt', 'red', 'M', 5),
('tank top', 'white', 'S', 200),
('tank top', 'blue', 'M', 15);

select * from shirts;
insert into shirts(article,color,shirt_size,last_worn) values('polo shirt','purple','M',50);
select article,color from shirts where shirt_size='M';
select article,color,shirt_size,last_worn from shirts where shirt_size='M';
update shirts set shirt_size='L' where article='polo shirt';
update shirts set last_worn=0 where last_worn=15;
update shirts set shirt_size='XS' ,color='off white' where color='white';
delete from shirts where last_worn=200;
delete from shirts where article='tank top';
delete from shirts;
drop table shirts;


### 터미널로 SQL 추가

1. sql이 저장된 폴더로 이동
2. mysql> use book_shop
3. mysql> source book_data.sql

### String Function

select concat('h','e','l','l');
select concat(author_fname,' ',author_lname) as fullname from books;

select concat_ws(' ','hi','bye','lol'); //단어 사이에 첫번째 값이 들어감

>hi bye lol

select substring('Hello World' , 1, 4);// 첫번째 단어의 1자리에서 4개의 character

>Hell

select substring('Hello World' , 2, 4);

>ello

select substring('Hello World' , 7); // 3번째 값이 없으면 7자리에서 끝까지 출력

>World

select substring('Hello World' , -1); //음수는 뒤에서부터

>d

SELECT SUBSTRING(title, 1, 10) AS 'short title' FROM books;

select concat(substr(title,1,10), '...') as short_title from books;

from books

### REPLACE

select replace(title, ' ','-') from books ; // 바꾸고 싶은 문장, 탐색할 문장, 바꿀 문장

### REVERSE

select reverse(’Hello World’);

### CHAR LENGTH

SELECT CHAR_LENGTH('Hello World');

### LOWER & UPPER

SELECT UPPER('Hello World');
SELECT LOWER('Hello World');