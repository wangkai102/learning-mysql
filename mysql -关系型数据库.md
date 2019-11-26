# mysql -关系型数据库

## 终端操作数据库

### 1、如何登陆数据库服务器

```shell
mysql  -u<账户> -p<密码>
```

### 2、如何查询数据库服务器中所有的数据库

```shell
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sakila             |
| test               |
| world              |
+--------------------+
6 rows in set (0.00 sec)
```

### 3、如何选中某一数据进行操作

```shell
mysql> select * from admin;
ERROR 1046 (3D000): No database selected
```

未查找到数据报错

```shell
mysql> use test
Database changed
```

选中数据库

### 4、如何在数据库服务器中创建数据库

```shell
mysql> create database test2;
Query OK, 1 row affected (0.01 sec)
```

### 5、如何查看数据库中中的所有数据

```shell
mysql> show tables;
Empty set (0.00 sec)
```

### 6、如何创建一个数据表

```shell
CREATE TABLE pet (
	name VARCHAR(20),
	owner VARCHAR(20),
	species VARCHAR(20),
	sex CHAR(1),
	birth DATE,
	death DATE
);
mysql> CREATE TABLE pet (
    -> name VARCHAR(20),
    -> owner VARCHAR(20),
    -> species VARCHAR(20),
    -> sex CHAR(1),
    -> birth DATE,
    -> death DATE
    -> );
Query OK, 0 rows affected (0.01 sec)
```

### 7、查看创建好的数据表的结构

```shell
mysql> describe pet;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| name    | varchar(20) | YES  |     | NULL    |       |
| owner   | varchar(20) | YES  |     | NULL    |       |
| species | varchar(20) | YES  |     | NULL    |       |
| sex     | char(1)     | YES  |     | NULL    |       |
| birth   | date        | YES  |     | NULL    |       |
| death   | date        | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
6 rows in set (0.02 sec)
```

### 8、如何查看数据表中的记录

```shell
mysql> select * from pet;
Empty set (0.00 sec)
```

### 9、如何往数据表中添加记录

```shell
mysql> INSERT INTO pet
    -> VALUES('Sunny','kid','cat','f','2017-08-01',null);
Query OK, 1 row affected (0.02 sec)
mysql> select * from pet;
+-------+-------+---------+------+------------+-------+
| name  | owner | species | sex  | birth      | death |
+-------+-------+---------+------+------------+-------+
| Sunny | kid   | cat     | f    | 2017-08-01 | NULL  |
+-------+-------+---------+------+------------+-------+
1 row in set (0.00 sec)
```

### 10、mysql常用数据类型

 MySQL支持多种类型，大致可以分为三类：数值、日期/时间和字符串(字符)类型。 

- 数值

  