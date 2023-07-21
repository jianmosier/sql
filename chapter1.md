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






