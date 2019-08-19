# JS第 6 周第 5 天

## 1. Sass

> ***前端工程化***

### 1.1. Sass-嵌套

```SAS
#main p {
  color: #00ff00;
  width: 97%;

  .redbox {
    background-color: #ff0000;
    color: #000000;
  }
}
```

````SAS
.funky {
  font: {
    family: fantasy;
    size: 30em;
    weight: bold;
  }
}
````

```sas
.example {
  color: red;
}

#main {
  @import "example";
}
```

### 1.2. Sass-变量定义

```sas
$width: 5em;
#main {
  width: $width;
}
```

### 1.3. Sass-判断语句 

```sas
p {
  @if 1 + 1 == 2 { border: 1px solid; }
  @if 5 < 3 { border: 2px dotted; }
  @if null  { border: 3px double; }
}
```

### 1.4. Sass-循环语句

```sas
@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}
```

###  1.5. Sass-mixin函数

```sas
@mixin large-text {
  font: {
    family: Arial;
    size: 20px;
    weight: bold;
  }
  color: #ff0000;
}
```

```sas
.page-title {
  @include large-text;
  padding: 4px;
  margin-top: 10px;
}
```

### 1.5. Sass-function介绍

```sas
$grid-width: 40px;
$gutter-width: 10px;

@function grid-width($n) {
  @return $n * $grid-width + ($n - 1) * $gutter-width;
}

#sidebar { width: grid-width(5); }
```

## 2. Gulp

> ***前端工程化***
>
> 解决了什么样的问题 ?
>
> - 代码审查；
> - 压缩打包；
> - 增量更新；
> - 单元测试；
>
> gulp具体工作：
>
> - 把一个文件拷贝到另一个位置
> - 把多个js或css文件合并成一个文件，以减少网络请求数
> - 对js文件和css文件进行压缩合并 以减少网络流量
> - 压缩图像文件，以减少网络流量
> - 创建一个可以实时刷新页面内容和本地服务器等等

