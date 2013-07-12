# 手动查询dkim设置是否成功
使用设置好的应用向某个gmail帐号发送邮件,在gmail里面打开这封邮件,点开"原始邮件",查看在header里面是否有dkim=pass

### dkim配置的dns样例
s1024-2011-q2._domainkey.facebookmail.com       text = "k=rsa\; t=s\; h=sha256\; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDLWnmo7aFBKfL4+mogTe/cXx6D4MUF7VUM9O+nmXAcUP6jJh1RDgZuSJ/KKxo+KMpDiF5xnawr4p3N4eFruSZWFB1vtHgDiy3iPke/u0lmXB2PDQphFRJU4Raghm9e2duPfuSExbvSu9COWIoaz1vH/T+8zc0vuonClGuPfxoqhQIDAQAB"
