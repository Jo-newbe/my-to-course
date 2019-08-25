# JS第 2 周第 4 天

> ECMAScript：标准，规范
>
> DOM：Document Object Model （文本对象）兼容性：部分不兼容
>
> BOM：Browser Object Model （浏览器对象）兼容性：不兼容（例如IE，谷歌，火狐，不可能兼容）

## 1. BOM 

1. window对象介绍

   - 什么是window对象那？ window对象就是浏览器内置的一个对象

2. window内置对象(location/navigator)及方法

   - window.innerHeight - 浏览器窗口的内部高度

   - window.innerWidth - 浏览器窗口的内部宽度

   - `window.open()` 打开新窗口 不传参数就是打开空白页面

   - `window.close()`  ff不兼容

   - `window.location` 地址信息 typeof

   - `window.location.href=""` 跳转链接

   - `window.location.reload()` 刷新页面

   - `navigator.userAgent` 返回浏览器信息

     > window.navigator.userAgent.indexOf('MSIE')

     - `navigator.appName` 获取当前浏览器的名称
     - `navigator.appVersion` 获取当前浏览器的版本号
     - `navigator.platform` 获取当前计算机的操作系统

   - `alert()`

   - `confirm()`

     ```
     var i=confirm("对话框的提示文字");
       if(i){
           document.write('你确定了')
       }else{
           document.write('你否定了')
       }
     ```

   - history.forward()  // 前进一页

   - history.back()  // 后退一页

## 2. DOM

1. - 可视区

     - document.documentELement.clientWidth
     - document.documentELement.clientHeight
       1. window.innerHeight/innerWidth
     - 第一种方式获取的是可视区的宽高，包括了滚动条的宽度
     - ps:IE 8 及更早 IE版本不支持这两个属性。

     2. document.body.clientHeight/clientWidth

     　　　第二种方式获取的是 body对象宽度

     3. document.documentElement.clientHeight/clientWidth

     　　　第三种方式获取的是可视区的宽高，不包括了滚动条的宽度

   - 滚动距离

     - document.documentELement.scrollTop 
     - document.documentELement.scrollLeft
     - document.body.scrollTop ==> chrome

   ```
   document.documentElement.scrollTop  代表垂直的滚动条，向下滚动的距离
     document.body.scrollTop  //chrome  代表垂直的滚动条，向下滚动的距离
     document.documentElement.scrollLeft
     document.body.scrollLeft
   ```

2. onload事件

   - onload 加载事件网页加载完毕后执行
   - onscroll 滚动事件

3. window.onscroll事件

   - 当鼠标滚轮滚动的时候
   - 当进度条被拖动的时候

4. 定时器

## 3. 广告弹出窗(自动关闭)

## 4. DOM的基本操作(查询、修改、创建、删除)

- 选择器
- 属性操作

## 5. DOM 相关属性

- agName 返回值是当前元素的标签名(即可获得，又可设置)
- innerHTML || innerText  返回值是当前元素的内容(即可获得，又可设置)
- id 返回值是当前元素的ID(即可获得，又可设置)
- title 获取title标签值； 这个title是从Document中获取的(即可获得，又可设置)
- className 返回值是当前元素的Class(即可获得，又可设置)
- href 返回当前的href值;

## 6. 练习

1. 顶部悬浮
2. 回到顶部
3. 动态创建表格