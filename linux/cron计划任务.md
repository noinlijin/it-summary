## 全局cron
```
sudo vim /etc/cron  #修改cron配置
sudo service cron restart #重启cron(刷新配置)
```
下面文章来自:https://help.ubuntu.com/community/CronHowto

## 常用crontab
### 当可用内存小于1G时,清除linux的文件缓存
```
*  *    * * *   root    if [ `/usr/bin/free -m |/bin/grep Mem|/usr/bin/awk '{print $4}'` -lt 1000 ] ; then /bin/echo 1 > /proc/sys/vm/drop_caches ; fi
```

### backup db every 20 min
```
*/20 * * * * bak /home/bak/backup/xxx/db/backup.sh
```
### backup web every day
```
0 2 * * * bak /home/bak/backup/xxx/web/backup.sh
```
### crontab可用性测试
```
* * * * * root /bin/date +%Y%m%d-%H%M%S >> /tmp/1.txt
```
