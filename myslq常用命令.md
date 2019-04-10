#### myslq常用命令

1.查看所有数据库

```mysql
show databases;
```

2. 查看所有表

```mysql
show tables;
```

3. 查看表结构

```mysql
desc table_name;
```

4. 切换数据库

```mysql
use 库名;
```

5. 查看表所有数据

```mysql
select * from table_name;
```

6、创建数据库

```mysql
create database test;
```

7.清空表数据

```mysql
truncate test;
```

8.mysql端口查询

```mysql
sudo netstat -anp | grep mysql
```

9.简单分页查询

```mysql
select * from table limit(page-1)*limit,limit;
/*page : 当前页数*/
/*limit : 每页的数量*/
```

10.like操作符

```mysql
select * from user where name like '小%';
/*查询user表 name字段 以小开头的数据*/
select * from user where name like '%小%';
/*查询user表 name字段 包含小的数据*/
select * from user where name like '%小';
/*查询user表 name字段 以小结尾的数据*/
```

11.not like操作符

```mysql
select * from user where name not like '小%';
/*查询user表 name字段 不是以小开头的数据*/
```

12.IN操作符

```mysql
select * from user where name IN('小红','小紫');
/*从user表查询 name字段为IN里边的值*/
```

13.or运算符

```mysql
select * from user where score>80 or gender='女';
/*从user表查询 score大于80或者gender=女的数据，任意一条成立*/
```

14.and运算符

```mysql
select * from user where gender='女' and score>90;
/*从user表查询gender=女,且score大于90的，两边同时成立*/
```

15.合并查询

```mysql
select * from student,user where student.age=user.age;
/*从student和user表中查询age相同的数据*/21.
```

16.count()

```mysql
select count(*) from user where score>80;
/*从user表中查询满足条件score>80的数量*/
```

17.AVG()

```mysql
select AVG(score) from user;
/*从user表中查询score字段的平均值*/
```

18.order by(排序)

```mysql
select * from user order by score;
/*从user表查询数据根据score字段进行升序*/
select * from user order by score desc;
/*从user表查询数据根据score字段进行降序*/
```

19.插入数据

```mysql
insert into user(name,age,score,gender) values('小红',18,90,'女');
/*向user表插入一条数据字段为user后边的 值为values后边的一一对应*/
```

20.更新数据

```mysql
update user set score=61,age=17 where name='小红';
/*更新user表名字为小红的score字段和age字段的值*/
/*注意：如果没有where条件的话则所有数据的score和age字段都改变*/
```

21.删除数据

```mysql
delete from user where name='小红';
/*删除user表中name=小红的数据*/
/*注意：没有where条件的话则删除表中所有数据*/
```

22.between操作符

```mysql
select * from user where score between 60 and 80;
/*查询user表score字段60-80范围的数据*/
select * from user where score not between 60 and 80;
/*查询user表score字段不在60-80范围的数据*/
```

