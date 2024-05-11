##### #、npm publish

登录需要邮箱接收验证码；以 package.json name 命名发布；
私有包命名带统一 namespace 前缀 @xpresent/[pkg name]。

npm config set registry https://registry.npmjs.org

npm adduser // node 18.18.0 跳浏览器验证

npm publish .

npm unpublish xpresent-editor --force
