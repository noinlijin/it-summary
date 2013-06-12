反向代理,简单使用
# 注意事项
1.不要自己代理回到自己.->会大量消耗机器的性能相当于ddos了...这个机器上的其他站也访问不了了.

# 配置apache2
sudo a2enmod proxy
sudo a2enmod proxy_http

# 正向代理 forward proxy

<VirtualHost *:11111>
ProxyRequests On
ProxyVia On

<Proxy *>
Order deny,allow
Deny from all
Allow from internal.example.com
</Proxy>
</VirtualHost>

# 反向代理 reverse proxy
## 用户访问a.com就像访问了b.com
在b.com那台机器上获得的host为b.com
<VirtualHost *:80>
ProxyPass / http://b.com/
ProxyPassReverse / http://b.com/
ServerName a.com
    <Location />
        Allow from all
    </Location>
</VirtualHost>

## 用户访问a.com就像访问了b.com
在b.com那台机器上获得的host为a.com
<VirtualHost *:80>
ProxyPass / http://b.com/
ServerName a.com
ProxyPreserveHost On
    <Location />
        Allow from all
    </Location>
</VirtualHost>

## 链式代理,用户访问a.com,apache2访问b.com,b.com作为代理再访问c.com
<VirtualHost *:80>
ServerName a.com
ProxyRemote * http://b.com/
ProxyPass / http://c.com/
    <Location />
        Allow from all
    </Location>
</VirtualHost>