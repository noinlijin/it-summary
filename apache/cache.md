# 全站无cache
需要在返回请求头里面加上:
```
Cache-Control:no-cache, no-store
Header merge Cache-Control no-cache
Header merge Cache-Control no-store
```
需要打开apache模块
```bash
sudo a2enmod headers

