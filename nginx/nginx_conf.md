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
