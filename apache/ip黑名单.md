在apache2的配置里面禁止某一个ip访问
<VirtualHost *:80>
    ServerName xxx.com
    DocumentRoot /var/xxx/
<Location />
order allow,deny
deny from 192.168.1.5
deny from 192.168.1.6
allow from all
</Location>
