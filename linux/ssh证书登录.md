## ssh login with cert 用证书登录ssh 可以不提供密码
* https://help.ubuntu.com/community/SSH/OpenSSH/Keys

### 客户端生成证书
```
mkdir ~/.ssh
chmod 700 ~/.ssh
ssh-keygen -t rsa
```

### 在客户端上 上传证书到服务器
#### 方法1(需要能登录上去,需要客户端是ubuntu)
```
ssh-copy-id <username>@<host>
```

#### 方法2
##### 先把你的证书的公钥 scp 到服务器上(在客户端执行)
```
scp ~/.ssh/id_rsa.pub xxx@xxx:~/
```

##### 再把你的证书的公钥 追加到服务的某个用户的证书列表的后面(在服务器端执行)
```
cat ~/id_rsa.pub >> /home/xxx/.ssh/authorized_keys
```

* 注意:一定是追加,不要把别人的证书覆盖了
* 没有权限时可以用`sudo bash`提权
