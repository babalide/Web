# 基础



## 1.1	MySQL概述

### 1.1.1	数据库相关概念

1. 数据库：存放数据的仓库，数据是有组织的进行存放

2. 数据库管理系统：操纵和管理数据库的大型软件
3. SQL：操作关系数据库的编程语言，定义了一套关系型数据库统一标准

### 1.1.2	MySQL数据库







## 1.2	SQL

### 1.2.1	SQL通用语法

1. SQL语句可以单行或多行书写，以分号结尾
2. SQL语句可以使用空格/缩进来增强语句的可读性
3. MySQL数据库的SQL语句不区分大小写，关键字建议使用大写
4. 注释
   * 单行注释：--注释内容 或 注释内容（MySQL特有）
   * 多行注释：/*注释内容*/





### 1.2.2	SQL分类

| 分类 | 说明                                                   |
| ---- | ------------------------------------------------------ |
| DDL  | 数据定义语言，用来定义数据库对象（数据库，表，字段）   |
| DML  | 数据操作语言，用来对数据库表中的数据进行增删改         |
| DQL  | 数据查询语言，用来查询数据库中表的记录                 |
| DCL  | 数据控制语言，用来创建数据库用户、控制数据库的访问权限 |





### 1.2.3	DDL(定义对象)

#### 1.2.3.1	DDL—数据库操作

- 查询
  - 查询所有数据库：show databases;
  - 查询当前数据库：select databases;

- 创建
  - 数据名：create databases[if not exists];
  - 字符集：default charset;
  - 排序规则：collate;

- 删除
  - 数据库名：drop databases[if exists];

- 使用
  - 数据库名：use;	

#### 1.2.3.2	DDL—表操作

- 查询

  - 查询当前数据库中所有表：show tables;
  - 查询表结构：desc 表名;
  - 查询指定表的建表语句：show create table 表名;

- 创建

  create table 表名{

  ​	字段1 字段1类型[comment 字段1注释],

  ​	字段2 字段2类型[comment 字段2注释],

  ​	字段3 字段3类型[comment 字段3注释],

  ​	...

  ​	字段n 字段n类型[comment 字段n注释],

  }[comment 表注释];

- 修改

  - 修改数据类型：alter table 表名 modify 字段名 新数据类型（长度）

  - 添加字段：alter table 表名 add 字段名 类型（长度）[cemment 注释][约束]

    ```
     alter table emp add nickname varchar(20) comment '昵称';
    ```

  - 修改字段名和字段类型：alter table 表名 change 旧字段名 新字段名 类型 长度[comment 注释] [约束]；

    ```
    alter table emp change nickname username varchar(30) comment '用户名';
    ```

  - 删除字段：alter table 表名 字段名

    ```
    alter table emp drop username;
    ```

  - 修改表名：alter table 表名 rename to 新表名

  - 删除表：drop table[if exists] 表名

  - 删除指定表，并重新创建该表：truncate table 表名

- 数据类型

  - 数值类型

    | 类型         | 大小    | 有符号的范围                                       | 无符号的范围                                            | 描述           |
    | ------------ | ------- | -------------------------------------------------- | ------------------------------------------------------- | -------------- |
    | tinyint      | 1 bytes | -128,127                                           | 0,255                                                   | 小整数值       |
    | smalltnt     | 2 bytes | -32768,32767                                       | 0，65535                                                | 大整数值       |
    | mediumint    | 3 bytes | -83886088，8388607                                 | 0，16777215                                             | 大整数值       |
    | tnt或integer | 4 bytes | -2147483648，2147483647                            | 0，4294967295                                           | 大整数值       |
    | bigint       | 8 bytes | -2^63,2^63-1                                       | 0，2……64-1                                              | 极大整数值     |
    | float        | 4 bytes | -3.402823466 E+38,3.402823466351 E+ 38             | 0和（1.175494351 E-38，3.402823466 E+38）               | 单精度浮点数值 |
    | double       | 8 bytes | -1.7976931348623157 E+308,1.7976931348623157 E+308 | 0和（2.2250738585072014 E-308,1.7976931348623157 E+308) | 双精度浮点数值 |
    | decimal      |         | 依赖与M（精度）和D（标度）的值                     | 依赖与M（精度）和D（标度）的值                          | 小树值         |

    

  - 字符串类型

    |      |      |      |
    | ---- | ---- | ---- |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |
    |      |      |      |

    

  - 日期时间类型

    |      |      |      |      |      |
    | ---- | ---- | ---- | ---- | ---- |
    |      |      |      |      |      |
    |      |      |      |      |      |
    |      |      |      |      |      |
    |      |      |      |      |      |
    |      |      |      |      |      |

    - [ ] 设计一张员工信息表

      1，编号（纯数字）

      2，员工工号（字符串类型，长度不超过10位）

      3，员工姓名（字符串类型，长度不超过10位）

      4，性别（男/女，存储一个汉字）

      5，年龄（正常人年龄，不可能存储负数）

      6，身份证号码（二代身份证为18位，身份证中有X这样的字符）

      7，入职时间（取值年月日即可）

      ```
      create table emp(
      	id int comment '编号',
      	workno varchar(10) comment '工号',
      	name varchar(10) comment '姓名',
      	gender char(1) comment '性别',
      	age tinyint unsigned comment '年龄',
      	idcard char(18) comment '身份证号',
      	entrydate date comment '入职时间'
      )comment '员工表';
      ```

    


### 1.2.4	DML(添加，修改，删除数据)

- 添加数据：

  - 给指定字段添加数据：insert into 表名（字段1，字段2，...） values(值1，值2...);

  - 给全部字段添加数据：insert into 表名 values(值1,值2...);

  - 批量添加数据：

    ​	insert into表名（字段名1，字段名2，...）values(值1，值2...)(值1，值2...)(值1，值2...);

    ​	insert into表名 values(值1，值2...)(值1，值2...)(值1，值2...);

- 修改数据：update 表名 set 字段名1 = 值1，字段名2 = 值2，...[where条件];
- 删除数据：
  - 删除部分数据：delete from 表名[where 条件];
  - 删除所有员工：delete from 表名;





### 1.2.5	DQL(查询数据)

- 基本查询

  - 查询返回多个字段

    select 字段1,字段2,字段3...from 表名;

    select * from 表名;

  - 设置别名

    select 字段1[as 别名1]，字段2[as 别名2]...from 表名

  - 去除重复记录

    select distinct 字段列表 from 表名;
    
    

- 条件查询(where)

  - 语法：select 字段列表 from 表名 where 条件列表

  - 条件

    | 比较运算符    | 功能                                     |
    | ------------- | ---------------------------------------- |
    | >             | 大于                                     |
    | >=            | 大于等于                                 |
    | <             | 小于                                     |
    | <=            | 小于等于                                 |
    | =             | 等于                                     |
    | <>或!=        | 不等于                                   |
    | between...and | 在某个范围之内                           |
    | in(...)       | 在in之后的列表中的值，多选一             |
    | like占位符    | 模糊匹配(_匹配单个字符，%匹配任意个字符) |
    | is null       | 是null                                   |
    
    | 逻辑运算符 | 功能                       |
    | ---------- | -------------------------- |
    | and 或 &&  | 并且(多个条件同时成立)     |
    | or 或 \|\| | 或者(多个条件任意一个成立) |
    | not 或 ！  | 非，不是                   |
    
    

- 聚合函数(count、max、min、avg、sum)

  语法：select 聚合函(字段列表) from 表名

  注意：null值不参与所有的聚合函数运算

  

- 分组查询(group by)

  select 字段列表 from 表名[where 条件] group by 分组字段名[having 分组后过滤条件]

  

- 排序查询(order by)

  

- 分页查询(limit)

  语法：select 字段列表 from 表名 limit 起始索引，查询记录

  注意：

  - 起始索引从0开始，起始索引  = (查询页码-1) * 每页显示记录数
  - 分页查询是数据库的方言，不同的数据库有不同的实现方式，mysql中是limit
  - 如果查询的第一页数据，起始索引可以省略，直接简写为limit 10

- 查询循序

  from                 表名列表

  where               条件列表

  group by          分组字段列表

  having              分组后条件列表

  select                字段列表

  order by           排序字段列表

  limit                   分页参数

  - select e.name ename, e.age eage from emp e where e.age > 15 order by eage asc;





### 1.2.6	DCL(权限控制)

#### 管理用户

- 查询用户：

  use mysql;

  select * from user;

  

- 创建用户：create user '用户名'@'主机名' identified by '密码';

  

- 修改用户密码： alter user '用户名'@'主机名' identified with mysql_native_password by '密码';

  

- 删除用户：drop user '用户名'@'主机名';

#### 权限常用种类

| 权限                | 说明               |
| ------------------- | ------------------ |
| all, all privileges | 所有权限           |
| select              | 查询数据           |
| insert              | 插入数据           |
| update              | 修改数据           |
| delete              | 删除数据           |
| alter               | 修改表             |
| drop                | 删除数据库/表/视图 |
| create              | 创建数据库/表      |



#### 权限控制

- 查询权限：show grants for '用户名'@'主机名'

  

- 授予权限：grants 权限列表 on 数据库名.表名 to '用户名'@'主机名';

  

- 撤销权限：revome 权限列表 on 数据库名.表名 from '用户名'@'主机名'







### 汇总

#### 1，创建表与输入数据

```
--  创建表
create table emp(
    id                  int                 comment '编号',
    workno              varchar(10)         comment '工号',
    name                varchar(10)         comment '姓名',
    gender              char(1)             comment '性别',
    age                 tinyint unsigned    comment '年龄',
    idcard              char(18)            comment '身份证号',
    workaddress         varchar(50)         comment '工作地址',
    entrydate           date                comment '入职时间'
)comment '员工表';

-- 输入数据
insert into emp(id, workno, name, gender, age, idcard, workaddress, entrydate)
values (1,'1','柳岩','女',20,'123456789012345678','北京','2000-01-01'),
       (2,'2','张无忌','男',20,'123456789012345670','北京','2005-09-01'),
       (3,'3','韦一笑','男',18,'123456789012345671','上海','2005-08-01'),
       (4,'4','赵敏','女',38,'123456789012345672','长沙','2009-01-01');
```







#### 2，查询

##### 基础查询

```mysql
--  基础查询
-- 1，查询指定字段 name,workno,age 返回
select name ,workno,age from emp;

-- 2，查询所有字段返回
select id, workno, name, gender, age, idcard, workaddress, entrydate from emp;

select * from emp;--    效果是一样的 ，但是*不直观；

-- 3，查询所有员工的工作地址，起别名
select workaddress as '工作地址' from emp;

-- 4，查询公司员工的上班地址（不要重复）
select distinct workaddress '工作地址' from emp;

--  条件查询
--  1，查询年龄等于 18 的员工
select  * from emp where age = 18;

--  2，查询年龄小于 20 的员工信息
select * from emp where age < 20;

--  3，查询年龄小于等于 20 的员工信息
select * from emp where age <= 20;

--  4，查询没有身份证号的员工信息
select * from emp where idcard is null;

--  5，查询有身份证号的员工信息
select * from emp where idcard is not null;

--  6，查询年龄不等于 88 的员工信息
select * from emp where age != 88;
select * from emp where age <> 88;

--  7，查询年龄在15到20岁的之间的员工信息
select * from emp where age <= 20 && age >= 15;
select * from emp where age <= 20 and age >= 15;

select * from emp where age between 15 and 20;

--  8，查询性别为女且年龄小于38 岁的员工信息
select * from emp where gender = '女' and age < 25;

--  9，查询年龄等于 18 或 20 或 38 的员工信息
select * from emp where age = 18 or age = 20 or age = 38;
select * from emp where age in (18,20,38);

--  10，查询姓名为两个字的员工信息
select * from emp where name like '__';

--  11,查询身份证最后以为为8 的员工信息
select * from emp where idcard like '%8';
select * from emp where idcard like '_________________8';
```



##### 聚合函数

```
--  聚合函数
--  1,统计该企业员工的数量
select  count(*) from emp;
select count(idcard) from emp;

--  2,统计该企业员工的平均年龄
select avg(age) from emp;

--  3,统计该企业员工的最大年龄
select max(age) from emp;

--  4,统计该企业员工的最小年龄
select min(age) from emp;

--  5,统计西安地区员工年龄之和
select sum(age) from emp where workaddress = '长沙';
```



##### 分组查询

```mysql
--  分组查询
--  1,根据性别分组，统计男性员工和女性员工的数量
select gender,count(*) from emp group by gender;

--  2,根据性别分组，统计男性员工和女性员工的平均年龄
select gender,avg(age) from emp group by gender;

--  3,查询年龄小于45的员工，并根据工作地址分组，获取员工数量大于等于3的工作地址
select workaddress,count(*) address_count from emp where age < 45 group by workaddress having address_count >= 1;
```



##### 排序查询

```mysql
--  排序查询
--  1,根据年龄对公司的员工进行升序排序
select * from emp order by age asc;
select * from emp order by age desc;

select * from emp order by age;

--  2,根据入职时间对员工进行降序排序
select * from emp order by entrydate desc;

--  3,根据年龄对公司的员工进行升序排序，年龄相同再按照入职时间进行降序排序
select * from emp order by age asc ,entrydate desc ;
```



##### 分页查询

```mysql
--  分页查询
--  1，查询第1页员工数据，每页展示10条记录
select * from emp limit 0,10;

select * from emp limit 10;

--  2,查询第2页员工数据，每页展示10条记录 -----------> (页码-10) * 页展示的记录数
select * from emp limit 10,10;
```







#### 3，权限管理

##### 管理用户

```
-- 创建用户itcast,只能在当前主机localhost访问，密码123456
create user 'itcast' @'localhost' identified by '123456';

--  创建用户heima，可以在任意主机访问，密码123456
create user 'heima'@'%' identified by'123456';


--  修改用户heima的访问密码为1234
alter user 'heima'@'%' identified with mysql_native_password by '1234';

--  删除itcast@localhost用户
drop user 'itcast' @'localhost';
```



##### 权限管理

```
--  查询权限
show grants for 'heima'@'%';

--  授予权限
grant all on itcast.* to 'heima'@'%';

--  撤销权限
revoke all on itcast.* from 'heima'@'%';
```







## 1.3	函数

定义：是指一段可以直接被另一段程序调用的程序或代码

分类：	

1. 字符串函数
2. 数值函数
3. 日期函数
4. 流程函数



### 1.3.1	字符串函数

| 函数                     | 功能                                                      |
| ------------------------ | --------------------------------------------------------- |
| concat(s1,s2...sn)       | 将字符串拼接，将s1,s2..sn,拼接成一个字符串                |
| lower(str)               | 将字符串str全部转为小写                                   |
| upper(str)               | 将字符串str全部转为大写                                   |
| lpad(str,n,pad)          | 左填充，用字符串pad对str的左边进行填充，达到n个字符串长度 |
| rpad(str,n,pad)          | 右填充，用字符串pad对str的右边进行填充，达到n个字符串长度 |
| trim(str)                | 去掉字符串头部和尾部的空格                                |
| substring(str,start,len) | 返回从字符串str从start位置起的len个长度的字符串           |







### 1.3.2	数值函数

| 函数       | 功能                               |
| ---------- | ---------------------------------- |
| ceil(x)    | 向上取整                           |
| floor(x)   | 向下取整                           |
| mod(x,y)   | 返回x/y的模                        |
| rand()     | 返回0~1内的随机数                  |
| round(x,y) | 求参数x的四舍五入的值，保留y位小数 |







### 1.3.3	日期函数

| 函数                              | 功能                                              |
| --------------------------------- | ------------------------------------------------- |
| curdate()                         | 返回当前日期                                      |
| curtime()                         | 返回当前时间                                      |
| now()                             | 返回当前日期和时间                                |
| year(data)                        | 获取指定date的年份                                |
| month(data)                       | 获取指定date的月份                                |
| day(data)                         | 获取指定date的日期                                |
| date_add(date,interval expr type) | 返回一个日期/时间值加上一个时间间隔expr后的时间值 |
| datediff(date1,date2)             | 返回起始时间date1和结束时间date2之间的天数        |







### 1.3.4	流程函数

| 函数                                                        | 功能                                                    |
| ----------------------------------------------------------- | ------------------------------------------------------- |
| if(value,t,f)                                               | 如果value为true,则返回t,否则返回f                       |
| ifnull(value1,value2)                                       | 如果value不为空，返回value1,否则返回value2              |
| case   when[val1]   then[res1] ... else[default]   end      | 如果value1为true,返回res1,...否则返回default默认值      |
| case[expr]    when[val1]   then[res1]...else[deflaut]   end | 如果expr的值等于val1，返回res1,...否则返回default默认值 |



### 汇总

#### 1，字符串函数

```
--  拼接
select concat('hello ','mysql');

--  全部转为小写
select lower('HELLO');

--  全部转为大写
select upper('hello');

--  左填充
select lpad('01',5,'-');

--  右填充
select rpad('01',5,'-');

--  去掉字符串头部和尾部的空格
select trim('  hello  mysql  ');

-- 返回从字符串str从start位置起的len个长度的字符串
select substring('Hello MySQL ',1,5);
```

##### 列题

由于业务需求变更，企业员工的工号，统一为5位数，目前不足5位数，目前不足5位数的全部在前面补0。比如：1号员工的工号为00001

```
update emp set workno = lpad(workno,5,'0');
```







#### 2，数值函数

```
--  向上取整
select ceil(1.1);

--  向下取整
select floor(1.9);

--  返回x/y的模
select mod(7,4);

--  返回0~1内的随机数
select rand();

--  求参数x的四舍五入的值，保留y位小数
select round(2.34,1);
```

##### 列题

生成一个六位数的随机验证码

```
select lpad(round(rand()*1000000,0 ),6,'0');
```









#### 3，日期函数

```
--  返回当前日期
select curdate();

--  返回当前时间
select curtime();

--  返回当前日期和时间
select now();

--  获取指定date的年份/月份/日期
select year(now());
select month(now());
select day(now());


--  返回一个日期/时间值加上一个时间间隔expr后的时间值
select date_add(now(),interval 70 year);

--  返回起始时间date1和结束时间date2之间的天数
select datediff('2021-12-01','2021-11-01');
```

##### 列题

查询所有员工的入职天数，并根据入职天数倒叙排序

```
select name,datediff(curdate(),entrydate) as 'entrydays' from emp order by entrydays  desc ;
```







#### 4，流程函数

```
--  如果value为true,则返回t,否则返回f
select if(false,'OK','Error');

--  如果value不为空，返回value1,否则返回value2
select ifnull('ok','default');
select ifnull('','default');
select ifnull(null,'default');
```



```
--  如果value1为true,返回res1,...否则返回default默认值
--  case when then else end
--  需求：查询emp表的员工姓名和工作地址(北京/上海---一线城市，其他---二线城市）
select
    name ,
    (case workaddress when '北京'  then '一线城市' when '上海' then '一线城市' else '二线城市' end) as '工作地址'
from emp;
```



```
--  如果expr的值等于val1，返回res1,...否则返回default默认值
--  需求：统计班级各个学员的成绩，展示的规则如下：
/*
    >=85，展示优秀
    >=60，展示及格
    否则展示不各级
 */

create table score(
    id int comment 'ID',
    name varchar(20) comment '姓名',
    math int comment '数学',
    english int comment '英语',
    chinese int comment '语文'
)comment '学员成绩表';
insert into score(id,name,math,english,chinese) values (1,'tom',67,88,95),(2,'rose',23,66,90),(3,'jack',98,13,68);

select * from score;

select
    id,
    name,
    (case when math>=85 then '优秀' when math>=60 then '及格' else '不及格' end) '数学',
    (case when english>=85 then '优秀' when english>=60 then '及格' else '不及格' end) '英语',
    (case when chinese>=85 then '优秀' when chinese>=60 then '及格' else '不及格' end) '语文'
from score;
```









## 1.4	约束

### 1.4.1	概念

- 概念：约束时作用于表中字段上的规则，用于限制存储在表中的数据

- 目的：保证数据库中的数据正确，有效性和完整性

- 分类

  | 约束                   | 描述                                                     | 关键字      |
  | ---------------------- | -------------------------------------------------------- | ----------- |
  | 非空约束               | 限制该字段的数据不能为null                               | not null    |
  | 唯一约束               | 保证该字段的所有数据都是唯一、不重复的                   | unique      |
  | 主键约束               | 主键时一行数据的唯一标识，要求非空且唯一                 | primary key |
  | 默认约束               | 保存数据时，如果未指定该字段的值，则采用默认值           | default     |
  | 检查约束(8.0.16版本后) | 保证字段值满足某个条件                                   | check       |
  | 外键约束               | 用来让两张表的数据之间建立联系，保证数据的一致性和完整性 | foreign key |

  注意：约束时作用于表中字段的，可以在创建表/修改表的时候添加约束



#### 样列

| 字段名 | 字段含义   | 字段类型    | 约束条件                  | 约束关键字                |
| ------ | ---------- | ----------- | ------------------------- | ------------------------- |
| id     | id唯一标识 | int         | 主键，并且自动增长        | primary key,auto_incement |
| name   | 姓名       | varchar(10) | 不为空，并且唯一          | not null,unique           |
| age    | 年龄       | int         | 大于0，并且小于等于120    | cherk                     |
| status | 状态       | char(1)     | 如果没有指定该值，默认为1 | default                   |
| gender | 性别       | char(1)     | 无                        |                           |





1.4.2	外键约束

