* 下面的信息都是参考mysql手册:http://dev.mysql.com/doc,
* 只作为便于记忆用.具体含义请看手册


## WHERE语法:
在update delete select 这3个命令上面可以使用select
### 常用:
```
SELECT * FROM pet WHERE name = 'Bowser'
SELECT * FROM pet WHERE birth >= '1998-1-1'
SELECT * FROM pet WHERE species = 'dog' AND sex = 'f'
SELECT * FROM pet WHERE species = 'snake' OR species = 'bird'
SELECT * FROM pet WHERE (species = 'cat' AND sex = 'm') OR (species = 'dog' AND sex = 'f')
SELECT * FROM pet WHERE death IS NOT NULL
```
某个值是不是null

## 搜索 like
使用like一般会把所有的数据都扫描一遍
```
SELECT * FROM pet WHERE name LIKE 'b%'
```
在所有的name里面搜索以'b'开头的字符串
```
SELECT * FROM pet WHERE name LIKE '%w%';
```
在所有的name里面搜索包含'w'的字符串
```
SELECT * FROM pet WHERE name LIKE '_____';
```
在所有的name里面搜索长度为5的字符串
```
set @next=1;
INSERT INTO table (current,name) VALUES (1,'a')
  ON DUPLICATE KEY UPDATE current = (@next := current + 1);
SELECT @next;
```
## 外键
### 忽略外键检查
```
SET foreign_key_checks = 0;
```
### 开启外键检查
```
SET foreign_key_checks = 1;
