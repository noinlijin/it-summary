# Windows下为go程序加入图标资源
引用:http://www.golang.tc/t/50b58150320b52067e00000f

### 准备资源
* 准备图标资源如demo.ico，适用WindowsXP的图标可以选择32x32或48x48。这步找设计人员...
* 建立rc文件，如demo.rc 内容如下

```
IDI_ICON1 ICON "demo.ico"       
```

### 编译脚本
注意:windres 来自wingw
```
windres -o demo-res.syso demo.rc
go build -gcflags '-H windowsgui'
del demo-res.syso
```