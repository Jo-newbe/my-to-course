# JS第 2 周第 5 天

## 1. DOM下

### 1.1. 节点类型

![](https://images0.cnblogs.com/blog2015/645526/201508/011527440322088.png)

### 1.2. 节点属性

- nodeType:节点种类，返回值是数字；

- nodeValue: 获取（文字）节点的文本内容；

- nodeName：返回node节点名称（#text，注释， 标签....）；

- childNodes：获取当前元素的所有子节点；

  > 请注意子节点只算第一层的，孙子节点不在子节点的范畴内。

- children

- parentNode

- nextElementSibling (678不支持)

- previousElementSibling (678不支持)

- firstElementChild

- lastElementChild

### 1.3. 节点创建

- `var oDiv=document.createElement('div')`
-  `var oText=document.createTextNode('dddd');`

### 1.4. 节点添加

- `oDiv.appendChild(oText)`
- `box.insertBefore(newNode, existNode)`

### 1.5. 节点删除

`box.removeChild(oText)`  删除节点

### 1.6. 其他

1. 获取非行内样式（兼容问题）

   ```
   function getStyle(obj,attr){    //获取非行间样式，obj是对象，attr是值
             if(obj.currentStyle){   //针对ie获取非行间样式
                 return obj.currentStyle[attr];
             }else{
                 return getComputedStyle(obj,false)[attr];   //针对非ie
             };
   };
   ```

2. offsetWidth/offsetHeight

3. offsetLeft/offsetTop

## 2. 作业

1. 点击按钮换图片
2. tab切换案例