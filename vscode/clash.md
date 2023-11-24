#### clash for windows

##### #、error: unmarshal errors cannot unmarshal map into string ...

可能是vpn过期，订阅链接解析不到正确的节点，导致语法错误。

##### #、error: sublime text is launching for editing ...

未安装 sublime，可修改 clash 配置 Settings Editor = CFW / vscode

##### #、mixin 指定代理

General => Mixin  开启
Settings => Mixin => YAML  编辑

```
mixin: # 注意下面缩进
  rules:
    - "DOMAIN-SUFFIX,bing.com,🚀 节点选择"
    - "DOMAIN,www.bing.com,🚀 节点选择" # proxies.name 按 profile 填写，如 '🚀 节点选择'
```
