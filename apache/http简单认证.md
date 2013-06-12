用户http简单认证auth:
可以防止一般用户进入网站.
缺点: 一旦被劫包 就会搞到帐号密码
生成包含帐号密码的文件:
htpasswd -c /home/xxx/auth/www.xxx.com.htpwd(文件名) xxx(用户名)
通过url限制
<Location />
    Order Allow,Deny
    Allow from all
    AuthType Basic
    AuthName "Authenticated proxy"
    AuthUserFile /home/xxx/auth/www.xxx.com.htpwd
    Require user xxx
</Location>
通过文件目录限制
<Directory /home/xxx/www/>
    Order Allow,Deny
    Allow from all
    AuthType Basic
    AuthName "Authenticated proxy"
    AuthUserFile /home/xxx/auth/www.xxx.com.htpwd
    Require user xxx
</Directory>