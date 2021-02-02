# npm安装操作及问题处理

1. 安装及操作

   + ```
     npm install X:
     
     会把X包安装到node_modules目录中
     不会修改package.json
     之后运行npm install命令时，不会自动安装X
     npm install X –save:
     
     会把X包安装到node_modules目录中
     
     会在package.json的dependencies属性下添加X
     
     之后运行npm install命令时，会自动安装X到node_modules目录中
     
     之后运行npm install
     –production或者注明NODE_ENV变量值为production时，会自动安装msbuild到node_modules目录中
     
     npm install X –save-dev:
     
     会把X包安装到node_modules目录中
     
     会在package.json的devDependencies属性下添加X
     
     之后运行npm install命令时，会自动安装X到node_modules目录中
     
     之后运行npm install
     –production或者注明NODE_ENV变量值为production时，不会自动安装X到node_modules目录中
     
     使用原则:
     
     运行时需要用到的包使用–save，否则使用–save-dev。
     ```
     
   + 卸载安装安装

     ```
     npm uninstall xxx -g
     ```

   + 查看全局安装

     ```
     npm list -g --depth 0
     ```

     

2. 问题及处理

   + ```
     npm WARN npm npm does not support Node.js vX.X.X NPM
     npm版本和node版本不匹配
     ```

     ```
     解决办法：升级npm
     npm install -g npm
     ```
     
     [参考](https://nodejs.org/zh-cn/download/releases/)
     
   + ```
     Unexpected end of JSON input while parsing near
     ```
   
     ```
     解决方案：
     npm cache clean --force
     ```
   
   + ```
     npm WARN saveError ENOENT: no such file or directory, open 'C:\Users\Administrator\package.json'
     ```
   
     ```
     解决方案：
     先运行下 npm init -f 初始化一下，就好了
     ```
   
     
   
   + 
   
3. 设置代码 

   + ```
     npm config set https-proxy http://11.8.39.14:3128
     yarn
     yarn config set proxy http://XX
     yarn config set https-proxy http://XX
     ```

   + 


