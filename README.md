# Oracle-sql-comments
Oracle常用sql语句总结

# 插入数据

```aidl
//普通
INSERT INTO 表名称 VALUES (值1, 值2,....)
INSERT INTO table_name (列1, 列2,...) VALUES (值1, 值2,....)





```

# 删除数据

```aidl
//普通删除
DELETE FROM 表名称 WHERE 列名称 = 值
DELETE FROM Person WHERE LastName = 'Wilson' 

//删除所有行
DELETE FROM table_name
DELETE * FORM TABLE_NAME

```
# 查询数据

```
-- 普通查询
SELECT 列名称 FROM 表名称
SELECT * FROM 表名称

----------------------------------------------------------
-- 去重
SELECT DISTINCT 列名称 FROM 表名称

----------------------------------------------------------
-- 条件查询
SELECT 列名称 FROM 表名称 WHERE 列 运算符 值

操作符	描述
=	等于
<>	不等于
>	大于
<	小于
>=	大于等于
<=	小于等于
BETWEEN	在某个范围内
LIKE	搜索某种模式

----------------------------------------------------------
---- 引号（文本值可用，数值不可用）
SELECT * FROM Persons WHERE FirstName='Bush'
SELECT * FROM Persons WHERE Year>1965

----------------------------------------------------------
-- AND & OR
如果第一个条件和第二个条件都成立，则 AND 运算符显示一条记录。
如果第一个条件和第二个条件中只要有一个成立，则 OR 运算符显示一条记录。

----------------------------------------------------------
-- ORDER BY 排序(默认升序)
SELECT Company, OrderNumber FROM Orders ORDER BY Company
SELECT Company, OrderNumber FROM Orders ORDER BY Company, OrderNumber

----------------------------------------------------------
-- DESC 降序
SELECT Company, OrderNumber FROM Orders ORDER BY Company DESC
SELECT Company, OrderNumber FROM Orders ORDER BY Company DESC, OrderNumber ASC

----------------------------------------------------------
-- TOP 返回记录数目
SELECT TOP 2 FROM Persons
SELECT * FROM Persons WHERE ROWNUM <= 5
SELECT TOP 50 PERCENT * FROM Persons

----------------------------------------------------------
-- LIKE 用于在 WHERE 子句中搜索列中的指定模式
SELECT column_name(s) FROM table_name WHERE column_name LIKE pattern
//以N开头
SELECT * FROM Persons WHERE City LIKE 'N%'
//以g结尾
SELECT * FROM Persons WHERE City LIKE '%g'
//包含lon
SELECT * FROM Persons WHERE City LIKE '%lon%'
//NOT LIKE
SELECT * FROM Persons WHERE City NOT LIKE '%lon%'

----------------------------------------------------------
-- 通配符
通配符	    					描述
%	        					替代一个或多个字符
_	    						仅替代一个字符
[charlist]						字符列中的任何单一字符
[^charlist]\[!charlist]			不在字符列中的任何单一字符

SELECT * FROM Persons WHERE City LIKE 'Ne%'
SELECT * FROM Persons WHERE City LIKE '%lond%'
SELECT * FROM Persons WHERE FirstName LIKE '_eorge'
SELECT * FROM Persons WHERE LastName LIKE 'C_r_er'
//以A、L、N开头
SELECT * FROM Persons WHERE City LIKE '[ALN]%'
//不以A、L、N开头
SELECT * FROM Persons WHERE City LIKE '[!ALN]%'
----------------------------------------------------------
-- IN操作符（在 WHERE 子句中规定多个值）
SELECT column_name(s) FROM table_name WHERE column_name IN (value1,value2,...)
SELECT * FROM PersonsWHERE LastName IN ('Adams','Carter')

----------------------------------------------------------
-- BETWEEN ... AND ...
SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value1 AND value2
SELECT * FROM Persons WHERE LastName BETWEEN 'Adams' AND 'Carter'
```

# 更新数据

```aidl
//普通
UPDATE 表名称 SET 列名称 = 新值 WHERE 列名称 = 某值
UPDATE Person SET FirstName = 'Fred' WHERE LastName = 'Wilson' 
UPDATE Person SET Address = 'Zhongshan 23', City = 'Nanjing' WHERE LastName = 'Wilson'

```










