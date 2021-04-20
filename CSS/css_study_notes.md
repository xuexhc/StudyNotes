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

## 包含选择器

- 指定目标选择器必须处在某个选择器对应的元素内部(允许多层嵌套标签匹配相应样式)

```CSS
div p {text-align:center;}
```

- 使class名为first的标签里面所有名为p的标签设定样式

```CSS
.first p {text-align:center;}
```

## 子选择器

- 与**包含选择器**相同，但嵌套标签并不适用

```CSS
div>p {
text-align:center;
}
```

## 补充子选择器

- 使class名为first的标签里面所有名为p的子代标签设定样式

```CSS
.first>p {text-align:center;}
```

## 兄弟选择器

- A元素后面所有B元素设置样式

```CSS
h1 ~ p {
    color:red;
}
```

## 相邻兄弟选择器

- A元素后面第一个B元素设置样式

```CSS
h1 + p {
    color:red;
}
```

## 通用选择器

- 匹配HTML中所有元素标签

```CSS
<style>
  * {text-align:center;}
</style>
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
背景图像是否固定或随着页面的其余部分而滚动：`background-attachment`

```CSS
body {background-image:url('image.jpg');
      background-repeat:repeat-x;
      background-position:right top;}
```

背景简写(color-image-repeat-attachment-position)

```CSS
body {background:red url('image.jpg') no-repeat fixed top;}
```

## 文本

- 文本对齐
  - 居中/左右对齐：`center/left/right`
  - `justify`（两端对齐）：每一行宽度相等，左右外边距对齐

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

`uppercase`：全部大写<br />
`lowercase`：全部小写<br />
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

## 元素内禁用文字环绕

```CSS
p {white-space:nowrap;}
```
## 文本垂直对齐图像

```CSS
p {vertical-align:text-top;}
p {vertical-align:text-bottom;}
```

## 文本阴影

```CSS
p {text-shadow:2px 2px 2px red;}
```

## CSS字体

- 通用字体系列：拥有相似外观字体系统组合
- 特定字体系列：一个特定的字体系列
- 字体名称超一个字，必须用引号，多个字体之间用逗号隔开

```CSS
p {font-family:"Times New Roman", Times, Serif;}
```

## CSS字体样式

```CSS
p {font-style:normal;}//正常
p {font-style:italic;}//斜体
p {font-style:oblique;}//斜体，当字体没有`italic`属性时使用
```

## CSS字体大小

```CSS
p {font-size:12px;}
p {font-size:2.5em;} /* 40px/16=2.5em */
body {font-size:100%;}
```

## CSS字体粗细

```CSS
p {font-weight:bold;}
```

## CSS字体变形

- 以小型大写字体显示文本 

```CSS
p {font-variant:small-caps;}
```

## CSS字体属性简写

(font-style font-variant font-weight font-size/line-height font-family)

```CSS
p {font:italic small-caps bold 30px/100px Georgia, serif;}
```

## CSS链接

|链接状态|描述|
|:-|:-|
|a:link|正常，未访问过的链接|
|a:visited|已访问过的链接|
|a:hover|鼠标放在链接上时|
|a:active|链接被点击那一刻|

```CSS
a:link {color:black; text-decoration:none;}
a:visited {color:blue; text-decoration:overline;}
a:hover {color:pink; text-decoration:line-through;}
a:active {color:green; text-decoration:underline; background-color:black; font-size:50px; font-family:Georgia, serif;}
```

## CSS 不同列表项标记

```CSS
ul {list-style-type:circle;}
ol {list-style-type:lower-alpha;}
```

## CSS列表样式图像属性(浏览器兼容方案)

```CSS
ul {
list-style-type:none;
padding:0px;
margin:0px;}

ul li {
background-image:url ('');
background-repeat:no-repeat;
background-position:0px 5px;
padding-left:14px;
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

- 列表属性简写（list-style-type list-style-position list-style-image）

```CSS
ul {list-style:square inside url("#");}
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
padding:2px;
}
```

- 标题位置

```CSS
caption {caption-side:bottom;}
```
## CSS盒子模型

- Margin：清除边框外的区域
- Border：围绕在内边距和内容外的边框
- Padding：清楚内容周围区域
- Content：盒子的内容

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

轮廓是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用(不占用空间)

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

## CSS分组选择器

```CSS
h1, h2, h3 {color:red;}
```

## CSS嵌套选择器

- `p{}`：为所有p元素指定一个样式
- `.marked{}`：为所有class="marked"的元素指定一个样式
- `.marked p{}`：为所有class="marked"元素中的p元素指定一个样式
- `p.marked{}`：为所有class="marked"的p元素指定一个样式

## CSS尺寸

```CSS
P {
max-height:20px;
max-width:50%;
min-height:20px;
}
```

## CSS隐藏元素

`display:none`:不会占用任何空间
`visibility:hidden`:仍占用空间，影响布局
```CSS
h1.hidden {
display:none;
visibility:hidden;
}
```

## CSS块元素和内联元素转换

```CSS
li {display:inline;}
span {display:block;}
p {display:inline-block;}
```

## CSS定位

- `static`：静态定位，无任何变化

```CSS
p {position:static;}
```

- `fixed`：相对于浏览器窗口固定，鼠标滚动不会移动

```CSS
p {
position:fixed;
top:12px;
right:20px;
}
```

- `relative`：相对正常位置做出调整进行定位

```CSS
h1 {
position:relative
left:-20px;//设置在左边缘向左移动20px
}
```

- `absolute`：绝对定位的元素的位置相对于最近已定位父元素（父元素定位不能为static），如果没有已定位父元素、那就相对于`<html>`

```CSS
p {
position:absolute;
left:20px;}
```

- `sticky`：基于用户滚动来定位（在跨域特定阈值之前为相对定位，之后为固定定位）

```CSS
div {
border:2px solid red;
position: -webkit-sticky; /* Safari */
position:sticky;
top:0;}
```

## CSS重叠元素

`z-index`：属性指定一个元素的堆叠顺序<br />
如果两个定位元素重叠且没有指定z-index，最后定位在HTML中的元素显示在最前面

```CSS
img {
position:absolute;
z-index:-1}
```

## CSS裁剪元素外形

top和bottom是表示距离元素上边界的距离，left和right是表示距离元素左边界的距离

```CSS
img {
clip:rect(0px,200px,120px,0px;)
}
```

## CSS使用滚动条显示溢出内容

`overflow`只工作于指定高度的块元素上

```CSS
p {
overflow:scroll;//内容会被修剪，显示滚动条
overflow:hidden;//内容会被修剪，其余内容不可见
overflow:auto;//如果内容被修剪，则显示滚动条
overflow:visible;//内容不会被修剪，显示在元素框外
}
```

## CSS浮动

使元素向左或向右移动，周围元素也会被重新排列（浮动元素之前的元素不受影响，之后的元素将围绕它）

```CSS
img {float:left;}
```

`clear`属性清除浮动,元素两侧不能出现浮动元素

```
img {float:left;}
.text_line {clear:both;}
```

## CSS对齐

- 元素居中

```CSS
div {margin:auto;}
```

- 文字居中

```CSS
p {text-align:center;}
```

- 图片居中

```CSS
img {
display:block;
margin:auto;
}
```

- 使用定位左右对齐(`body`元素设置`margin`和`padding`)

```CSS
.right {
position:absolute;
right:0px;
width:10px;
padding:10px;
border:1px solid red;
}
```

- 使用float左右对齐

如果子元素高度大于父元素，且子元素设置了浮动，那么子元素将溢出，在父元素添加`overflow:auto;`样式清除浮动

```CSS
.clearfix {overflow:auto;}

.img {float:right;}
```

- 使用padding水平垂直居中对齐

```CSS
 div {
 border:1px solid red;
 padding:70px 0px;
 text-align:center;
 }
```

- 使用`line-height`水平垂直居中对齐

```CSS
.center {
line-height:100px;
height:100px;
border:1px solid red;
text-align:center;
}

.center p {
line-height:1.5;
dispaly:inline-block;
vertical-align:middle;
}
```

- 使用`position`和`transform`水平垂直居中对齐

```CSS

```

## CSS组合选择符

- 后代选择器

选择某元素中所有子元素

```CSS
div p {background-color:black;}
```

- 子元素选择器

选择某元素中所有直接子元素

```CSS
div>p {text-align:center;}
```

- 相邻兄弟选择器

选择紧接在另一元素后的元素，二者由相同的父元素

```CSS
div+p {background-color:yellow;}/*选择在div元素后的第一个p元素*/
```

- 后续兄弟选择器

选择指定元素之后的所有相邻兄弟元素

```CSS
div~p {background-color;}
```

## CSS伪类

伪类用于向某些选择器添加特殊效果

- 选择器:伪类 {属性:值;}

```CSS
a:visited {color:red;}
```

- 伪类+CSS类配合使用

```CSS
a.red:visited {color:red;}
```

- 使用first-child伪类来选择父元素的第一个子元素

```CSS
p:first-child {color:red;}
```

- 匹配所有`p`元素中第一个`i`元素

```CSS
p > i:first-child {color:red;}
```

- 匹配所有作为第一个子元素的`p`元素中的所有`i`元素

```CSS
p:first-child i {color:red;}
```

- `:focus`伪类：用于选择具有焦点的元素

```CSS
input:focus {color:red;}

```


## CSS伪元素

伪元素用于将特殊效果添加到某些选择器

- 选择器:伪元素 {属性:值;}

-`first-line`伪元素用于向文本首行设置特殊样式，只能用于块级元素

```CSS;
p:first-line {color:red;}
```

- `first-letter`伪元素用于向文本的首字母设置特殊样式，只能用于块级元素

```CSS
p:first-letter {text-decoration:underline;}
```

- 伪元素+CSS类配合使用

```CSS
p.red:first-letter {color:red;}
```

- 多个伪元素组合

```CSS
p:first-line {color:blue;}
p:first-letter {color:red;}
```

- `before`伪元素和`after`伪元素可以在元素前后插入新的内容

```CSS
h1:before {
content:url("1.jpg");}

h1:after {
content:"123";}
```

- `p > i:first-child`选择相匹配的所有`p`元素中的第一个`i`元素

```CSS
p > i:first-child {color:blue;}
```

-`p:first-child i`选择所有第一个子元素`p`元素中的所有`i`元素

```CSS
p:first-child i {color:blue;}
```

## CSS导航栏

- 

```CSS

```

## CSS下拉菜单

```CSS

```










补充

margin:auto 0; 只对块级元素起作用


