# Git操作及问题处理

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

2. 问题及处理

   + ```
     npm WARN npm npm does not support Node.js vX.X.X NPM
     npm版本和node版本不匹配
     ```

     ```
     解决办法：升级npm
     npm install -g npm
     
     参考 https://nodejs.org/zh-cn/download/releases/
     ```

   + ```
     fatal: Not a git repository (or any of the parent directories): .git 
     没有git目录
     解决：
     git init
     ```

     