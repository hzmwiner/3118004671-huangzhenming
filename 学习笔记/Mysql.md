### Mysql

### 一、数据库概念

#### DB：数据库

#### DBMS：数据库管理系统

- 基于共享文件系统地DBMS（Access）
- 基于客户机—服务器的DBMS（MySQL）

### 二、数据库存储数据的特点

​	1.将数据放到表中，表再放到库中

​	2.一个数据库中可以有多个表，每个表有一个名字，用来标识自己。表名唯一性。

​	3.表具有一些特性，这些特性定义了数据在表中如何存储，类似java中“类”地设计。

​	4.表由列组成，我们也称为字段。所以表都是由一个或多个列组成地，每一列类似java中的“属性”

​	5.表中数据是按行存储的，每一行类似于Java中的对象。

### 三、MySQL服务的启动和停止

​	方式一：计算机—右击管理—服务

​	方式二：通过管理员身份运行

​	net start 服务名（启动服务）

​	net stop 服务吗（停止服务）

### 四、MySQL服务的登录和退出

​	方式一：通过mysql自带客户端

​	只限于root用户		

​	方式二：通过windows自带客户端

​	mysql -h 主机名（localhost） -P端口号 -u用户名 -p密码

​	退出

​	exit或者 Ctrl + C

### 五、MySQL的常见命令

​	1.查看当前所有的数据库

​		show databases；

​	2.打开指定的库

​		use 库名

​	3.查看当前库的所有表

​	 	show tables；

​	4.查看其他库的所有表

​		show tables from 库名；

​	5.创建表

​		create table 表名（

​			列名 列类型，

​			。。。

​		）；

​	6.查看表的结构

​		desc 表名；

​	7.查看服务器的版本

​	方式一：登录mysql服务的

​	select version();

### 六 MySQL的语法规范

​	1.不区分大小写，但建议关键字大写，表名，列名小写

​	2.每条命令最好用分号结尾

​	3.每条命令根据需要，可以进行缩进或者换行

### 七、查询（基础、条件、特定）

- 语法：

​		select 查询列表  from 表名；

​		类似于 System.out.println();

​		特点：1.查询列表可以是：表中的字段、常量、表达式、函数

​					2.查询的结果是一个虚拟的表格

​		eg： select last_name from employess;

​				 select last_name,salary from employess;	

​				 select * from employees;(查询所有)

- 条件查询：

​		select	查询列表 ——3

​		from	表名   ——1（运行顺序）

​		where 查询条件 ——2

- 特定查询：

- - between and：(两者之间，大于什么，小鱼什么)

    select * from employees where employees_id between 100 and 120;  

  - 

  - - like：查询员工名中包含字符a的员工信

    ​        特点：

    ​			1.一般和通配符搭配使用

  ​					通配符：%任意多个字符，包含0个字符

  ​									—任意一个字符

  ​					select * from employees where last_name like '%a%';

  ​					特例：要查询第二个字符为—的员工名

  ​					‘_ \\_%’使用转义字符

  ​					‘_x(任意符号字母)%’escape ‘x’;表示自定义转义

### 八、起别名

​	便于理解

​	 方式一：使用AS

​	 select 100 as 数字；

​	方式二：使用空格

​	 select 100 数字；s

​	 案例： 查询salary，显示结果为 out put

​	select salary as “” output”“ from employees；

### 九、去重

​	去除重复的编号

​	 select distinct xxx from xxx；

### 十、拼接

​	null与任何字符串拼接都为null

​	concat（xxx,xxx）；

​    

