# MySQL 常用命令

> mysql命令行操作db的常用命令，为了更好地展示命令行的效果，我将我的远程ip假设为**10.83.29.246**，端口号为**17286**，账号为**root**，密码为**123456**；创建的数据库名为**testDb**，创建的数据表名为**testTable**。

- 连接db

```markdown
mysql -h10.83.29.246 -P17286 -uroot -p123456
```

- 查看账号下所有的数据库

```mysql
show databases;
```

- 创建数据库

```mysql
create database 数据库名;
例： create database testDb;
```

- 删除数据库

```mysql
drop database 数据库名;
```

- 进入某数据库

```mysql
use 数据库名;
例： use testDb;
```

- 查看数据库中的数据表

```mysql
show tables;
```

- 创建数据表

```mysql
create table 表名(字段列表);
例： create table testTable(id INTEGER(5) primary key AUTO_INCREMENT, userName VARCHAR(256) not null, pwd VARCHAR(256) not null);
```

- 删除数据表

```mysql
drop table 表名;
```

- 查看数据表结构

```mysql
describe / desc table 表名;
例： describe / desc table testTable; 
```

- CRUD（增、查、改、删）基本操作

  - 增

  ```mysql
  insert into 表名(字段列表) values(值列表);
  例： insert into testTable(userName, pwd) values("qiuqiu", "123456");
  ```

  - 查

  ```mysql
  select * from 表名 [where 等语句];
  例： select * from testTable where userName='qiuqiu' and pwd='123456';
  ```

  - 改

  ```mysql
  update 表名 set 字段名=字段值 [条件];
  例： update testTable set pwd='123' where userName='qiuqiu';
  ```

  - 删

  ```mysql
  delete from 表名 [条件];
  例： delete from testTable where userName='qiuqiu';
  ```

- 删除表

```mysql
drop table 表名;
例： drop table testTable;
```

- 清空表

```mysql
delete from 表名; （delete支持条件删除）
或
truncate table 表名;
```

- 删除表中主键

```mysql
alter 表名 drop primary key;
```

- 为数据表添加主键

```mysql
alter 表名 add primary key 字段;
alter 表名 add primary key (字段1, 字段2, ...);
```

- 添加字段

```mysql
alter table 表名 add 字段名 属性;
```

- 删除字段

```mysql
alter table 表名 drop 字段名;
```

- 修改字段类型

```mysql
alter table 表名 modify 字段 属性;
例： alter table testTable modify pwd VARCHAR(20) not null;
```

- 修改字段名

```mysql
alter table 表名 change 原字段名 新字段名;
```

- 修改字段默认值

```mysql
alter table 表名 alter 字段名 set default 默认值;
```

- 连接，具体可查看 => [菜鸟教程详解](http://www.runoob.com/mysql/mysql-join.html) 

  - inner join 内连接或等值连接

  ![1541580878833](C:\Users\raeleneqiu\AppData\Roaming\Typora\typora-user-images\1541580878833.png)



  - left join 左连接

  ![1541580921569](C:\Users\raeleneqiu\AppData\Roaming\Typora\typora-user-images\1541580921569.png)

  - right join 右连接

  ![1541580938849](C:\Users\raeleneqiu\AppData\Roaming\Typora\typora-user-images\1541580938849.png)


