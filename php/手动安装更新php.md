未完待续
### 安装方法
```
sudo apt-get update
sudo apt-get install apache2-prefork-dev # 如果这个装不上 apt-get里面的某些包的版本有问题...
sudo apt-get install libxml2-dev make autoconf
wget http://www.php.net/distributions/php-5.5.1.tar.xz # 官网上的连接,如果失效,上官网自己找去...
tar -xf php-5.5.1.tar.xz
cd php-5.5.1
./configure --with-apxs2=/usr/bin/apxs2 --with-mysql
make
sudo make install
pecl install apc
```

### 分析安装方法
* 搞到apt-get安装的apache2的apxs文件路径

```
sudo apt-get install apt-file
sudo apt-file update
sudo apt-file list apache2 | grep apx
```
* 这个地方有2个包,php的安装说明里面建议不要用threaded MPM,就选择 apache2-prefork-dev: /usr/bin/apxs2
/usr/bin/apxs2