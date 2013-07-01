# tar的用法
## 打包目录
### 不压缩(速度快)
```
tar -cf xxx目标目录.tar ./xxxx打包目录名
```
### 压缩(体积可能会小)
```
tar -czf xxx目标目录.tar.gz ./xxxx打包目录名
```

压缩包中会包含./xxxx打包目录名
## 解压(解包)目录
```
tar -xzf xxx.tar.gz -C ./目标目录
```
## 查看tar包里面的文件
使用tar.vim
```
vim xxx.tar.gz
```
## 配合ssh做流式打包传输
### 从目录开始,到远程的一个tar文件(运行在源)
```
tar -cf - /input_folder |ssh user_name@output_ip "dd of=/backup/git.1.6/$name.tar"
```
### 从目录开始,到远程的一个tar文件(运行在目标)
```
ssh user_name@input_ip "tar -czf - /input_folder" | dd of=/backup/git.1.6/$name.tar
ssh sunshine@222.197.183.78 "tar -czf - ~/firefox" | dd of=./src.tar.gz
```
### 从目录开始,到远程的一个目录
```
ssh sunshine@222.197.183.78 "tar -czf - ~/firefox" | tar -xzf -C /tmp/1
```
