# 安装apache2的fastcgi
```bash
sudo apt-get install libapache2-mod-fastcgi
sudo a2enmod fastcgi
```
# fastcgi有多种模式,目前仅会使用一种
## External 模式
* 先用某种办法运行那个fastcgi的程序 监听 某个tcp端口
* 在apache2里面配置如下,比较奇怪的是那个DocumentRoot 不需要存在,但是必须有..

```
<VirtualHost *:80>
    ServerName go-play.sxz.dashu.us
    DocumentRoot /home/xxx/dev/golang/play/fcgi
    FastCgiExternalServer /home/xxx/dev/golang/play/fcgi -host 127.0.0.1:8082
</VirtualHost>
```

# 注意:
实践结果表明:
* 这个东西比较不容易配置成功
* 这个东西性能和反向代理差不多...
* 建议使用反向代理...
