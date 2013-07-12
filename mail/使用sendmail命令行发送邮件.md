只有正文的一个邮件,标题是undefined
```
echo test.mail | sendmail -v tt01@yopmail.com
```

制定发件人,和收件人
```
echo test.mail | sendmail -f test@yopmail.com -v tt01@yopmail.com
```