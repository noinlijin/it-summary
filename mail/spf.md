# 手动查询spf设置
```
nslookup -q=txt _spf.google.com
```

# 手动查询spf设置是否有效
使用设置好的应用向某个gmail帐号发送邮件,在gmail里面打开这封邮件,点开"原始邮件",查看在header里面是否有spf=pass