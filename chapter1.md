# 初识数据库
数据库安装和数据库基本介绍，mysql
## 初识数据库
数据库是将大量数据保存起来，通过计算机加工而成的可以进行高效访问的数据集合。该数据集合称为数据库（Database，DB）。用来管理数据库的计算机系统称为数据库管理系统（Database Management System，DBMS）
### DBMS的种类
DBMS 主要通过数据的保存格式（数据库的种类）来进行分类，现阶段主要有以下 5 种类型.
> 层次数据库（Hierarchical Database，HDB）
> 关系数据库（Relational Database，RDB）
* Oracle Database：甲骨文公司的RDBMS
* SQL Server：微软公司的RDBMS
* DB2：IBM公司的RDBMS
* PostgreSQL：开源的RDBMS
* MySQL：开源的RDBMS据库（Relational Database，RDB）
5种代表的RDBMS,特点是行列组成的二维表管理数据，这种类型的 DBMS 称为关系数据库管理系统（Relational Database Management System，RDBMS）
* 面向对象数据库（Object Oriented Database，OODB）
* XML数据库（XML Database，XMLDB）
* 键值存储系统（Key-Value Store，KVS），举例：MongoDB
其中关系数据库是重点

### RDBMS的常见系统结构
客户端 ----> sql语句   ----> 服务器 ----> 数据库
客户端 <---- 请求的数据 <---- 服务器 <---- 数据库

## 初识SQL
行 为 记录   列 为 字段
基于标准的SQL的RDBMS很少，通常需要编写特定的sql语句
+ DDL Data Definition Language，数据定义语言  CREATE  DROP  ALTER 
+ DML Data Manipulation Language，数据操纵语言 SELECT INSERT UPDATE DELETE 
+ DCL Data Control Language，数据控制语言 COMMIT  ROLLBACK  GRANT  REVOKE 
DML主要
### SQL书写规则
;
分大小

### 数据库创建
CREATE DATABASE shop;
### 表的创建
CREATE TABLE product
(product_id CHAR(4) NOT NULL,
 product_name VARCHAR(100) NOT NULL,
 product_type VARCHAR(32) NOT NULL,
 sale_price INTEGER ,
 purchase_price INTEGER ,
 regist_date DATE ,
 PRIMARY KEY (product_id));
### 命名规则

### 数据类型的指定

INTEGER 型    CHAR 型   VARCHAR 型    DATE 型
### 表的删除更新

DROP TABLE product;
ALTER TABLE product ADD COLUMN product_name_pinyin VARCHAR(100);
ALTER TABLE < 表名 > DROP COLUMN < 列名 >;
ALTER TABLE product DROP COLUMN product_name_pinyin;
DELETE FROM product WHERE COLUMN_NAME='XXX';
TRUNCATE TABLE TABLE_NAME;


### 向product表插入数据

CREATE TABLE productins
(product_id    CHAR(4)      NOT NULL,
product_name   VARCHAR(100) NOT NULL,
product_type   VARCHAR(32)  NOT NULL,
sale_price     INTEGER      DEFAULT 0,
purchase_price INTEGER ,
regist_date    DATE ,
PRIMARY KEY (product_id)); 

### 索引

创建索引
CREATE TABLE mytable(  
 
ID INT NOT NULL,   
 
username VARCHAR(16) NOT NULL,  
 
INDEX [indexName] (username(length))  
 
);  

### 练习题

#### 1 编写一条 CREATE TABLE 语句，用来创建一个包含表 1-A 中所列各项的表 Addressbook （地址簿），并为 regist_no （注册编号）列设置主键约束

```
CREATE TABLE Addressbook (
    regist_no VARCHAR(255) PRIMARY KEY,
    name VARCHAR(255),
    address VARCHAR(255),
    tel_no VARCHAR(255),
    mail_address VARCHAR(255)
);
```
### 2 假设在创建练习1.1中的 Addressbook 表时忘记添加如下一列 postal_code （邮政编码）了，请编写 SQL 把此列添加到 Addressbook 表中。

列名 ： postal_code

数据类型 ：定长字符串类型（长度为 8）

约束 ：不能为 NULL

```
ALTER TABLE Addressbook
ADD postal_code CHAR(8) NOT NULL;
```
### 3 请补充如下 SQL 语句来删除 Addressbook 表。

(    ) table Addressbook;
```
DROP TABLE Addressbook;

```
### 4 是否可以编写 SQL 语句来恢复删除掉的 Addressbook 表？
```
一旦使用了 `DROP TABLE` 命令删除了一个表，这个表和它的所有数据都会被永久性地删除，无法被恢复。这就是为什么在执行 `DROP TABLE` 命令之前一定要小心，并确保你有最新的数据备份。

如果有这个表的备份（例如，一个 SQL dump 文件），可以使用那个备份来恢复这个表。如果没有备份，但在删除表之前已经将数据导出或者复制到了另一个地方，也可以创建一个新的表，并将数据导入到新表。

如果没有备份也没有导出数据，那么恢复已删除的表将会非常困难，可能需要专业的数据恢复服务，而且成功的可能性也不大。

因此，对数据库进行操作时一定要小心，尤其是使用 `DROP TABLE` 这样的命令。建议定期备份你的数据，以防止数据丢失。
```








