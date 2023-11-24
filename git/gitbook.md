##### #、命令

安装gitbook  

`npm install gitbook-cli -g`

初始化书籍  

`gitbook init`

安装依赖  

`gitbook install`

预览  

`gitbook serve`

编译打包  

`gitbook build`

##### #、问题

1、使用 `gitbook build`（node v13.14.0）打包報錯 `Error: ENOENT: no such file or directory, stat xxx`

A：解决方式如下

```
C:\Users\admin\.gitbook\versions\3.2.3\lib\output\website\copyPluginAssets.js
修改 
confirm: true
為
confirm: false
```
