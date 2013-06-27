## 更新软件
如果你想用apt-get安装软件,必须apt-get update..
* 获取最快的/etc/apt/sources.list 文件
* sudo apt-get update
* sudo apt-get upgrade

## 添加cron table
```
vim /etc/crontab
```
### 定时更新服务器时间
```
44 6    * * *   root ntpdate ntp.ubuntu.com
```