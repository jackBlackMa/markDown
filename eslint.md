# 代码规范

## Eslint意义

1. 提供代码规范
2. 提供代码检查的工具，并打印结果。错误具体到某一行代码，并提供简单的修复命令



## 安装依赖包

```
npm i eslint --save-dev
安装模块到devDependenies
```



## 设置package.json

```
 "scripts": {
    "lint": "eslint --fix src",
    "lint:create": "eslint --init" 
  },
  npm run lint: 检查代码，并简单修复代码
  npm run lint:create: 生成.eslintrc.jc
```



## 创建.eslintrc.js文件

```
$ npm run lint:create

> 20170811@0.1.0 lint:create D:\code\test\20170811
> eslint --init

? How would you like to configure ESLint? Answer questions about your style // 以问答的形式创建配置文件
? Are you using ECMAScript 6 features? Yes      // 是否校验 Es6 语法
? Are you using ES6 modules? Yes                // 是否校验 Es6 模块语法
? Where will your code run? Browser             // 代码运行环境，Browser 指浏览器
? Do you use CommonJS? Yes                      // 是否校验 CommonJs 语法
? Do you use JSX? Yes                           // 是否校验 JSX 语法
? Do you use React? Yes                         // 是否校验 React 语法
? What style of indentation do you use? Tabs    // 首行空白选择 Tab 键还是 Space
? What quotes do you use for strings? Double    // 字符串使用单引号 'string' 还是双引号 "string"
? What line endings do you use? Windows         // 操作系统
? Do you require semicolons? Yes                // 每行代码结尾是否校验加分号 ;
? What format do you want your config file to be in? JavaScript     // 以 .js 格式生成配置文件
Installing eslint-plugin-react@latest   // 因为要校验 Reac 语法，所以这里需要下载一个 React 语法规则的包
```



## 校验代码

```
$ npm run lint

    1:7   error  'lint' is assigned a value but never used  no-unused-vars
    1:14  error  Strings must use doublequote               quotes
    1:22  error  Missing semicolon                          semi

    3 problems (3 errors, 0 warnings)
    2 errors, 0 warnings potentially fixable with the `--fix` option.
    
   展示校验的结果，并指定到具体位置的错误
```



## 配置文件讲解

```
module.exports = {
	"env": {
		"browser": true,
		"es2021": true
	},
	"extends": [
		"eslint:recommended",
		"plugin:vue/essential"
	],
	"parserOptions": {
		"ecmaVersion": 12,
		"sourceType": "module"
	},
	"plugins": [
		"vue"
	],
	"rules": {
		// 空格
		"indent": [
			"error",
			"tab"
		],
		// 换行采用windows
		"linebreak-style": [
			"error",
			"windows"
		],
		// 改成字符串必须由单引号括起来而不是双引号，'string'不报错，"string"报错
		"quotes": [
			"error",
			"double"
		],
		// 改成代码结尾不再加分号，加了分号报错，不加分号不报错
		"semi": [
			"error",
			"always"
		],
		"no-unused-vars": 0,
		"quote-props": [
			"error", 
			"always"
		],
		"comma-dangle": [1,"always-multiline"],  // 对象或数组多行写法时，最后一个值加逗号
	},
	// "globals": {
	// 	"window": true
	// }
};

```

### env、parserOptions、plugins 

配置参数，仅需了解进行

### extends

编码规范最佳实践 在 [eslint](http://eslint.cn/docs/rules/)规则表 中查看被标记为 √ 的规则项

## rules

自定义编码规则

修改规则应遵循如下要求

"off" 或 0 - 关闭规则

"warn" 或 1 - 开启规则，使用警告级别的错误：warn (不会导致程序退出)

"error" 或 2 - 开启规则，使用错误级别的错误：error (当被触发的时候，程序会退出)

## 单行跳过 lint 校验

```
const apple = "apple";  // eslint-disable-line
```

