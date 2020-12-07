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
?
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

























