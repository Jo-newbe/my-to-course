# JavaScript 第 1 周 第 1 天

## 1. JavaScript 简介

**JavaScript 是世界上最流行的编程语言。**

**这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备。**

## 2. JavaScript 是脚本语言

> 由于JS不可以独立执行，必须有运行环境或平台才可以，因此被叫做“脚本语言”。

JavaScript 是一种轻量级的编程语言。

JavaScript 是可插入 HTML 页面的编程代码。

JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。

JavaScript 很容易学习。

## 3. JavaScript 可以做什么？

### 3.1. JavaScript：写入 HTML 输出

实例

```js
document.write("<h1>This is a heading</h1>");
document.write("<p>This is a paragraph</p>");
```

提示：在文档加载后使用该方法，会覆盖整个文档。

### 3.2. JavaScript：对事件作出反应

实例

```js
<button type="button" onclick="alert('Welcome!')">点击这里</button>
```

alert() 函数在 JavaScript 中并不常用，但它对于代码测试非常方便。

### 3.3. JavaScript：改变 HTML 内容

使用 JavaScript 来处理 HTML 内容是非常强大的功能。

实例

```

```

 document.getElementByID("*some id*")这个方法是 HTML DOM 中定义的。

### 3.4. JavaScript：改变 HTML 图像



### 3.5. JavaScript：改变 HTML 样式

改变 HTML 元素的样式，属于改变 HTML 属性的变种。

```js
x=document.getElementById("demo")  //找到元素
x.style.color="#ff0000"; 
```

### 3.5. JavaScript：验证输入

JavaScript 常用于验证用户的输入。

实例

```js
if (isNaN(x)){alert("Not Numeric")};
```

## 4. 数据类型

## 5. 变量

## 6. 类型转换