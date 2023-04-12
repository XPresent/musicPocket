###### 1、同时连接github和gitlab

```
cd ~/.ssh
ssh-keygen -t rsa -C "github邮箱地址" -f ~/.ssh/github_rsa
ssh-keygen -t rsa -C "其他邮箱地址" -f ~/.ssh/id_rsa
```

###### 2、新建config文件

```
# gitlab
Host gitlab
    HostName git.xxx.com #这里填gitlab的Host
    User git
    IdentityFile ~/.ssh/id_rsa
# github
Host github
    HostName github.com
    IdentityFile ~/.ssh/github_rsa
```

###### 3、测试连接

```
ssh -T git@gitlab
ssh -T git@github
```

###### 4、更换ssh agent的私钥（agent: 代理，只在当前终端窗口生效）
如果测试连接失败，Permission denied (publickey).原因是我们自定义了 id_rsa_github 钥匙名，默认情况下，连接会搜索 id_rsa 钥匙名，所以这里会报错

```
ssh-agent  // 查看ssh-agent环境参数，登录主机时通过这些环境参数才能从ssh-agent中取得私钥
eval $(ssh-agent)  // 用eval执行ssh-agent，设定ssh-agent的环境参数
ssh-add ~/.ssh/github _rsa  // 添加新的私钥
ssh-add -l  // 查看是否添加成功
```
