# JS第 7 周第 1 天

## 1. 什么是Node.js

> Node.js® is a JavaScript runtime built on [Chrome's V8 JavaScript engine](https://v8.dev/).

JS是脚本语言，脚本语言都需要一个解析器才能运行。对于写在HTML页面里的JS，浏览器充当了解析器的角色。而对于需要独立运行的JS，Node.js 就是一个解析器。

每一种解析器都是一个运行环境，不但允许JS定义各种数据结构，进行各种计算，还允许JS使用运行环境提供的内置对象和方法做一些事情。例如运行在浏览器中的JS的用途是操作DOM，浏览器就提供了`document`之类的内置对象。而运行在NodeJS中的JS的用途是操作磁盘文件或搭建HTTP服务器，NodeJS就相应提供了`fs`、`http`等内置对象。

## 2. 用处

> Node.js的作者说，他创造NodeJS的目的是为了实现高性能Web服务器。

## 3. 安装

> 俗话说：“一个好汉三个帮”。

- NVM
- NPM
- NRM

## 4. First Node.js App

## 5. 模块 & CommonJS

> 编写稍大一点的程序时一般都会将代码模块化。在NodeJS中，一般将代码合理拆分到不同的JS文件中，每一个文件就是一个模块，而文件路径就是模块名。
>
> 在编写每个模块时，都有`require`、`exports`、`module`三个预先定义好的变量可供使用。

### 5.1. require

> `require`函数用于在当前模块中加载和使用别的模块，传入一个模块名，返回一个模块导出对象。

### 5.2. exports

> `exports`对象是当前模块的导出对象，用于导出模块公有方法和属性。别的模块通过`require`函数使用当前模块时得到的就是当前模块的`exports`对象。

### 5.3. module

> 通过`module`对象可以访问到当前模块的一些相关信息，但最多的用途是替换当前模块的导出对象。例如模块导出对象默认是一个普通对象，如果想改成一个函数的话，可以使用以下方式。

```js
module.exports = function () {
    console.log('Hello World!');
};
```

### 5.4. 模块路径解析规则

1. 内置模块

   如果传递给`require`函数的是Node.js内置模块名称，不做路径解析，直接返回内部模块的导出对象，例如`require('fs')`。

2. node_modules目录

   Node.js定义了一个特殊的`node_modules`目录用于存放模块。例如某个模块的绝对路径是`/home/user/hello.js`，在该模块中使用`require('foo/bar')`方式加载模块时，则Node.js依次尝试使用以下路径。

   ```markdown
   /home/user/node_modules/foo/bar
   /home/node_modules/foo/bar
   /node_modules/foo/bar
   ```

3. NODE_PATH环境变量

   与PATH环境变量类似，Node.js允许通过NODE_PATH环境变量来指定额外的模块搜索路径。NODE_PATH环境变量中包含一到多个目录路径，路径之间在Linux下使用`:`分隔，在Windows下使用`;`分隔。例如定义了以下NODE_PATH环境变量：

   ```
    NODE_PATH=/home/user/lib:/home/lib
   ```

   当使用`require('foo/bar')`的方式加载模块时，则Node.js依次尝试以下路径。

   ```
    /home/user/lib/foo/bar
    /home/lib/foo/bar
   ```

## 6. 包（package）

> ​		我们已经知道了JS模块的基本单位是单个JS文件，但复杂些的模块往往由多个子模块组成。为了便于管理和使用，我们可以把由多个子模块组成的大模块称做`包`，并把所有子模块放在同一个目录里。

在组成一个包的所有子模块中，需要有一个入口模块，入口模块的导出对象被作为包的导出对象。例如有以下目录结构。

```
- /home/user/lib/
    - cat/
        head.js
        body.js
        main.js
```

其中`cat`目录定义了一个包，其中包含了3个子模块。`main.js`作为入口模块，其内容如下：

```js
var head = require('./head');
var body = require('./body');

exports.create = function (name) {
    return {
        name: name,
        head: head.create(),
        body: body.create()
    };
};
```

## 7. 工程目录

```
- /home/user/workspace/node-project/   # 工程目录
    - bin/                          # 存放命令行相关代码
        node
    - doc/                          # 存放文档
    - lib/                          # 存放API相关代码
        echo.js
    - node_modules/                 # 存放三方包
        - express/
    - test/                         # 存放测试用例
    package.json                    # 元数据文件
    README.md                       # 说明文件
```

## 8. 文件操作

### 8.1. 普通文件

- 创建
- 删除
- 读取内容
- 写入内容
- 拷贝

### 8.2. 文件夹

- 创建
- 删除
- 读取

## 9. 网络操作

## 9.1. url模块

### 9.2. path模块

### 9.3. query string模块

###  9.4. http模块

- 查询参数
- post数据

### 9.5. 基础案例

## 10. Express

## 11. 案例

## 12. Socket编程

