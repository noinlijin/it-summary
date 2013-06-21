# service任务
优势:
  * 开机启动
  * service service_name restart
在建立一个叫 /etc/init/service_name.conf的文件,内容如下:

```
description     "xxxx whatever"
author          "xxxx whatever"

start on (net-device-up
          and local-filesystems
          and runlevel [2345])

stop on runlevel [016]

respawn

exec /xxx/path/to/bin
```