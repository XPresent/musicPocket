##### 1、修改 nginx.conf
```
  # find nginx master process
  [root@x /]# ps aux | grep nginx
  root  28952  0.0  0.0  34708  3016 ? Ss  Apr24  0:00 nginx: master process /home/co/sbin/nginx

  # get nginx.conf path
  [root@x /]# /home/co/sbin/nginx -t
  nginx: the configuration file /home/co/conf/nginx.conf syntax is ok
  nginx: configuration file /home/co/conf/nginx.conf test is successful

  # restart nginx
  [root@x /]# /home/co/sbin/nginx -s reload

```

##### 2、iframe 内嵌第三方页面
```
  # X-Frame-Options SAMEORIGIN;
  为避免点击劫持，改用 frame-ancestors 指定可被内嵌的父级源。
  response header:
  proxy_hide_header X-Frame-Options;
  add_header Content-Security-Policy  "frame-ancestors 'self' example.com example1.com"; 

  # Mix-content
  1. http://insecure.com loads http://also.insecure.com — is not a mixed content request because both origins are insecure.
  2. https://secure.com loads http://insecure.com — is a mixed content request because the insecure resourcehttp://insecure.com is loaded into the secure context https://secure.com.
  
  重定向需使用相同协议传输
  request header:
  "proxy_set_header  X-FORWARDED-PROTO $scheme;" 
  

  # Third-party cookie will be blocked
  response header:
  Set-Cookie  xxx;Secure;SameSite=None

```
