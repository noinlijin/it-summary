# 手动查询spf设置
```
nslookup -q=txt google.com
```

# 手动查询spf设置是否有效
使用设置好的应用向某个gmail帐号发送邮件,在gmail里面打开这封邮件,点开"原始邮件",查看在header里面是否有spf=pass

### spf配置的dns样例
facebookmail.com        text = "v=spf1 ip4:69.63.178.128/25 ip4:69.63.184.0/25 ip4:66.220.144.128/25 ip4:66.220.155.128/25 ip4:69.171.232.128/25 ip4:66.220.157.0/25 -all"