更新
### 安装方法
```
sudo apt-get install apache2-prefork-dev # 如果这个装不上 apt-get里面的某些包的版本有问题...
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