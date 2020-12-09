# CSS笔记

## 语法

**选择器**（需要改变的HTML元素）+一条或多条**声明**（一个属性:一个值）

## 注释

`/* */`

## id选择器

- 为标有特定id的HTML元素指定样式,选择器以`#`定义

```CSS
#h1{background-color:red;}
```

## class选择器

- 用于描述一组元素的样式，可在多个元素中使用，以一个`·`表示

```CSS
.center{text.align:center;}
```

- 特定HTML元素使用class

```CSS
p.center{text-align:center;}
```

## 多重样式表

- 优先级：内联样式>内部样式>外部样式>浏览器默认样式

- 如果外部样式放在内部样式的后面，则外部样式将覆盖内部样式

## 背景颜色

```CSS
body {background-color:red;}
```

## 背景图像

水平平铺：`repeat-x`
垂直平铺：`repeat-y`
不平铺：`no-repeat`
改变图片位置：`background-position:right top`

```CSS
body {background-image:url('image.jpg');
      background-repeat:repeat-x;
      background-position:right top;}
```

## 文本

- 文本对齐
  - 居中/左右对齐：`center/left/right`
  - `justify`：每一行宽度相等，左右外边距对齐

```CSS
h1 {text-align:center;}
p {text-align:right;}
body {text-align:justify;}
```

- 文本修饰

- `text-decoration`:设置或删除文本的装饰

```CSS
a {text-decoration:none;}
h1 {text-decoration:overline;}
h2 {text-decoration:line-through;}
h3 {text-decoration:underline;}
```

- 文本转换

用来指定文本中的大写或小写字母

`uppercase`：全部大写  
`lowercase`：全部小写
`capitalize`：首字母大写

```CSS
p.uppercase{text-transform:uppercase;}
```

## 文本缩进

```CSS
p {text-indent:20px;}
```

## 文本间空间

```CSS
p {letter-spacing:2px;}
```

## 行与行间空间

```CSS
p {line-height:150%;}
```

## 元素的文本方向

从右到左书写

```CSS
p {direction:rtl;}
```

## 单词间的空白空间

```CSS
p {word-spacing:30px;}
```

## 文本垂直对齐图像

```CSS
p {vertical-align:text-top};
p {vertical-align:text-bottom;}
```

## 文本阴影

```CSS
p {text-shadow:2px 2px red;}
```

## CSS字体

- 通用字体系列：拥有相似外观字体系统组合
- 特定字体系列：一个特定的字体系列

```CSS
p {font-family:"Times New Roman", Times, Serif;}
p {font-variant:small-caps;} /* 小型大写字体 */
```

## CSS字体样式

```CSS
p {font-style:normal;}
p {font-style:italic;}
p {font-style:oblique;}
```

## CSS字体大小

```CSS
p {font-size:12px;}
p {font-size:2.5em;} /* 40px/16=2.5em */
body {font-size:100%;}
```

## CSS链接

|链接状态|描述|
|:-|:-|
|a:link|正常，为访问过的链接|
|a:visited|已访问过的链接|
|a:hover|鼠标放在链接上时|
|a:active|链接被点击那一刻|

```CSS
a:link {color:black; text-decoration:none;}
a:visited {color:blue; text-decoration:overline;}
a:hover {color:pink; text-decoration:line-through;}
a:active {color:green; text-decoration:underline; background-color:black; font-size:50px; font-family:Georgia, serif;}
```

## CSS 列表样式图像属性

```CSS
ul {
list-style-type:none;
padding:0px;
margin:0px;}

ul li {
background-image:url ('');
background-repeat:no-repeat;
background-position:0px 5px;
padding-left;14px;
}
```

- 移除默认设置

```CSS
ul {
list-style-type:none;
padding:0px;
margin:0px;
}
```

## CSS表格

```CSS
table {border-collapse:collapse;}

table th td {
border:1px solid blue;
}

th {height:20px;}

td{
text-align:center;
vertical-align:bottom;
background-color:white;
color:green;  
}
```

- 标题位置

```CSS
caption {caption-side:bottom;}
```

## CSS边框

- dotted：点线边框
- dashed：虚线边框
- solid：实线边框
- double：两个边框，两个边框的宽度和`border-width`值相同
- groove：3D沟槽边框，取决于边框颜色
- ridge：3D脊边框，取决于边框颜色
- inset：3D嵌入边框，取决于边框颜色
- outset：3D突出边框，取决于边框颜色

```CSS
p {border-style:none;}
```

- 单独设置各边

```CSS
p {
border-top-style:solid;
border-right-style:dotted;
border-bottom-style:solid;
border-left-style:dotted;
}
```

## CSS轮廓

```CSS
p {outline:15px solid red;}
```

## CSS外边距

定义元素周围的空间

```CSS
p {
margin-top:10px;
margin-left:10%;
margin-right:10cm;
}
```

## CSS填充

定义元素边框与元素内容之间的空间

```CSS
p {padding-top:10px;}
```




















