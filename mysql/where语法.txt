# WHERE语法:
在update delete select 这3个命令上面可以使用select
## 常用:
** SELECT * FROM pet WHERE name = 'Bowser'
** SELECT * FROM pet WHERE birth >= '1998-1-1'
** SELECT * FROM pet WHERE species = 'dog' AND sex = 'f'
** SELECT * FROM pet WHERE species = 'snake' OR species = 'bird'
** SELECT * FROM pet WHERE (species = 'cat' AND sex = 'm') OR (species = 'dog' AND sex = 'f')
** SELECT * FROM pet WHERE death IS NOT NULL
某个值是不是null