# NewBie
## 从零开始学习git
### GitHub

1. ***使用https协议上传,但是每次都需要输入用户名及密码***

https 无法连接:
出现:
```
SSL certificate problem: unable to get local issuer certificate
```
则输入
```
git config --global http.sslVerify false
```
即可,但每次都需要输入用户名及密码



2. ***使用ssh协议上传,但是不用每次输入用户名及密码***

ssh 无法连接: 
错误代码为:
```
ssh: connect to host github.com port 22: Connection refused
```
则在~/.ssh文件夹下创建config文件
内容为:
```
Host github.com
User sample@sample.com # 你的邮箱地址
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 443
```
错误代码为:
```
The authenticity of host '[ssh.github.com]:443 ([18.141.90.153]:443)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

输入yes之后仍不可用,则使用命令
```
ssh -vT git@github.com
```
一串debug完成之后在使用命令
```
ssh -T git@github.com
```
就正常连接了.

### Gitee

两个协议都可正常使用
