# HTML 笔记

## HTML实例

- `<!DOCTYPE html>`声明为HTML5文档
- `<html>`元素是HTML5页面的根元素
- `<head>`元素包含了文档的元<meta>数据，如`<meta charset="UTF-8">`定义网页编码格式为UTF-8
- `<title>`元素描述了文档的标题
- `<body>`元素包含了可见的页面内容
- `<h1>`元素定义一个大标题
- `<p>`元素定义一个段落

## 什么是HTML?

HTML是用来描述网页的一种语言

- HTML指的是超文本标记语言
- HTML不是编程语言，而是一种**标记**语言
- 标记语言是一套**标记标签**
- HTML使用标记标签来**描述**网页
- HTML包含了HTML**标签**及**文本**内容
- HTML文档也叫**web页面**

## HTML标签

HTML标记标签称为HTML标签

- HTML标签是由尖括号包围的关键词，比如`<html>`
- HTML标签成对出现，比如`<p>和</p>`
- 标签对中第一个是开始标签，第二个是结束标签
- 开始标签和结束标签也称为开放标签和闭合标签

## HTML元素

一个HTML元素包含了开始标签和结束标签

- HTML元素以**开始标签**起始
- HTML元素以**结束标签**终止 
- **元素的内容**是开始标签与结束标签之间的内容
- 某些HTML元素具有**空内容**（empty content）
- 空元素**在开始标签中进行关闭**（已开始标签的结束而结束）
- 大多数HTML元素可拥有**属性**

## HTML属性

属性是HTML元素提供的附加信息

```HTML
<a href="https://www.baidu.com/">this is a link</a>
```

- HTML元素可以设置**属性**
- 属性可以在元素中添加**附加信息**
- 属性一般描述与**开始标签**
- 属性总是以名称/值对形式出现，比如name="value"
- 属性值应该始终被包括在引号内（单引号或双引号都可以，特殊情况使用单引号）

## HTML标题

`<h1>`定义最大标题，`<h6>`定义最小标题
浏览器会自动在标题前后添加空行（块级元素）

```HTML
<h1>标题1</h1>
```

## HTML水平线

`<hr />`

## HTML注释

`<!--注释-->`

## HTML段落

`<p>段落</p>`

## HTML换行

`<br />`

## HTML输出-使用提醒

显示页面时，所有的空格和空行都会被算作一个空格

## HTML格式化

使用标签对输出文本进行格式化，这种标签被称为格式化标签

### 文本格式化

- `<b>`：定义粗体文本
- `<strong>`：显示粗体文本，呈现的文本是重要的，突出显示
- `<i>`：定义斜体文本
- `<em>`：显示斜体文本，呈现的文本是重要的，突出显示
- `<big>`：文本字体放大
- `<small>`：文本字体缩小
- `<sub>`：文本包含下标，常用来表示化学公式
- `<sup>`：文本包含上标，常用来表示注脚
- `<ins>`：定义被插入文本
- `<del>`：定义被删除文本
- `<mark>`：定义带有记号的文本

### 预格式文本

- `<pre>`：对空行和空格进行控制，都会正常显示

### 计算机输出

- `<code>`：定义计算机代码
- `<kbd>`：定义键盘码,表示文本是从键盘上键入的
- `<tt>`：定义打字机文本
- `<samp>`：定义计算机代码样本
- `<var>`：定义变量

### 引文，引用，标签定义

- `<abbr>`：用来表示缩写词或者首字母缩略词
- `<address>`：定义文档作者/所有者的联系信息
- `<bdo>`：定义文字方向
- `<blockquote>`：定义一个长引用（会缩进）
- `<q>`：定义短引用（周围会插入引号）
- `<cite>`：定义（书籍、电影、绘画等）的标题
- `<dfn>`：定义一个定义项目

```HTML
<abbr title="xuehuicong">xhc</abbr>
<bdo dir="rtl">right to left</ bdo>
```

## HTML链接

```HTML
<a href="https://www.baidu.com/" target="_blank" rel="noopener noreferrer">Link baidu</a>
```

window.opener值变为null，让网站更安全：`rel="noopener noreferrer"`<br />
target属性可以定义被链接的文档在何处显示

- _blank:新的窗口中打开
- _self:在相同的框架或窗口中打开链接
- _parent:在父窗口中打开链接
- _top:清除所有被包含的框架，打开链接

使用id属性创建书签标记

```HTML
<a id="tips">有用的提示</a>
<a href="#tips">访问有用的提示</a>
<a href="index.html#tips">访问有用的提示</a>
```

始终将正斜杠添加到子文件夹，不然会产生两次HTTP请求

## HTML创建电子邮箱链接

```HTML
<a href="mailto:xuexhc@outlook?cc=xuexhc@gmail.com&bcc=xuexhc@163.com&subject=Hello%20again&body=Thank%20You" target="_blank">sent mail</a>
```

|参数                  |描述              |
|:-                    |:-               |
|mailto:name@email.com |邮件接收地址      |
|cc=name@email.com     |邮件抄送地址      |
|bcc=name@email.com    |邮件密送地址      |
|subject=subject text  |邮件主题          |
|body=body text        |邮件内容          |
|?                     |第一个参数分隔符   |
|&                     |其他参数分隔符     |
|%20                   |表示一个空格       |
|;                     |多个邮件地址分隔   |

## HTML图像

图像边框：`border="10"`<br />
图像替代文本：`alt="替代文本信息"`<br />
图像延迟请求加载资源，优先加载游览器可视区域内容（懒加载）：`loading="lazy"`<br />
图像默认加载：`loading="eager"`<br />
浮动图像：css:`float:right`

```HTML
<a href="https://www.baidu.com">
<img src="url" width="10" height="10" border="10" alt="smiley" loading="lazy" />
</a>
```

## HTML头部

- `<head>`元素

  `<head>`元素包含了所有头部标签元素:`<title>`、`<style>`、`<meta>`、`<link>`、`<script>`、`<noscript>`、`<base>`

- `<title>`元素

  `<title>`标签定义不同文档的标题

- `<base>`元素

  `<base>`标签描述了基本的链接地址/目标目标，该标签作为HTML中所有链接标签的默认链接,放在`<head>`元素中的第一个位置
  
  ```HTML
  <base href="C:\Users\xuexh\OneDrive\Myproject\.vscode\index.html" target="_blank">
  ```

- `<link>`元素

  `<link>`标签定义文档与外部资源之间的关系
  `<link>`标签通常用于链接到样式表
  
  ```HTML
  <link rel="stylesheet" type="text/css" href="mystyle.css">
  ```
  
  `<link>`标签显示图片
  
  ```HTML
  <link rel="shortcut icon" href="img url">
  <link rel="icon" href="image url" type="image/x-icon">
  ```

- `<style>`元素
  `<style>`标签定义了HTML文档的样式文件引用地址
  `<style>`元素中可以直接添加样式
  
  ```HTML
  <style type="text/css">
    body {background-color:black}
    p {color:yellow}
  </style>
  ```

- `<meta>`元素

  `<meta>`标签描述了基本的元数据（网页描述、关键词、作者等）
  
  - 为搜索引擎定义关键词
  
  ```HTML
  <meta name="keywords" content="HTML, CSS, JAVASCRIPT">
  ```
  
  - 为网页定义描述内容
  
  ```HTML
  <meta name="description" content="TEST">
  ```
  
  - 定义网页作者
  
  ```HTML
  <meta name="author" content="xhc">
  ```
  
  - 每30秒刷新当前页面
  
  ```HTML
  <meta http-equiv="refresh" content="30">
  ```
  
- `<script>`元素

  `<script>`标签用于加载脚本文件

## CSS

CSS可以通过以下方式添加到HTML中
**大部分**标签中，修改父级标签样式，子级标签样式也会改变

- 内联样式:在HTML元素中使用`<style>`属性

  ```HTML
  <p style="color:blue;">蓝色的段落</p>
  ```

- 内部样式表:在HTML文档头部<head>区域使用<style>元素来包含CSS
  
  ```HTML
  <head>
    <style type=text/css>
      body {background-color:white}
      p {color:blue}
    </style>
  </head>
  ```
  
- 外部引用:使用外部CSS文件

  ```HTML
  <head>
    <link rel="stylesheet" type=text/css href="C:\Users\xuexh\OneDrive\Myproject\.vscode\mystyle.css">
  </head>
  ```
  
## 表格
  
- `<table>`:表格，`<tr>`：表格行，`<td>`：单元格
- `<th>`：表格表头，`<caption>`：定义标题，`cellpadding`定义单元格边距，`cellspacing`定义单元格间距，`rowspan`定义跨行合并，`colspan`定义跨列合并
- `<thead>`组合表格表头内容，`<tbody>`组合表格主体内容，`<tfoot>`组合表格页脚内容
- `<colgroup>`元素对表格中的列进行组合，`<col>`规定每一列的列属性，`<span>`规定列组横跨的列数

```HTML
<table border="1" cellpadding="10">
  <caption>Table Title</caption>
  <colgroup>
    <col span="2" style="background-color:red;">
  </colgroup>
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row1 Cell1</td>
      <td>Row1 Cell2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Row2 Cell1</td>
      <td>Row2 Cell2</td>
    </tr>
  </tfoot>
</table>
```

## 列表

列表项内部可以使用段落、换行符、图片、链接、其他列表等

- 有序列表

```HTML
<ol start="50">
  <li>Coffee</li>
  <li>Tea</li>
</ol>
```

- 无序列表

```HTML
<ul style="list-style-type:square">
  <li>Coffee</li>
  <li>Tea</li>
</ul>
```

- 自定义列表，是项目及其注释的组合
- `<dl>`定义一个描述列表，`<dt>`定义一个描述列表的名字，`<dd>`对描述列表中的名字进行描述

```HTML
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

- 嵌套列表

```HTML
<ul>
  <li>Coffee</li>
  <li>Tea</li>
    <ul>
      <li>CN</li>
      <li>US</li>
    </ul>
</ul>
```

## 区块元素

块级元素在浏览器显示时，会以新行来开始和结束<br />
eg：`<h1>`、`<p>`、`<ul>`、`<table>`



## 内联元素

内联元素一般不会以新行开始
eg：`<b>`、`<td>`、`<a>`、`<img>`

## `<div>`元素

`<div>`元素是块级元素，用于组合其他元素

## `<span>`元素

`<span>`元素是内联元素，可用于为部分文本设置样式属性

## 表单

表单是一个包含表单元素的区域，使用表单标签`<form>`来设置
输入标签：`<input>`

- 文本域

默认宽度20个字符

```HTML
<form>
  First Name:<input type="text" name="firstname">
</form>
```

- 密码字段

```HTML
<form>
  Password:<input type="password" name="pwd">
</form>
```

- 单选按钮

```HTML
<form>
  Male<input type="radio" name="sex" value="male"><br />
  Female<input type="radio" name="sex" value="female">
</form>
```

- 复选框
- 预选`<input>`元素：`checked`

```HTML
<form>
  Coffee<input type="checkbox" name="drink" value="coffee">
  Milk<input type="checkbox" name="drink" value="milk" checked="checked">
</form>
```
- 提交按钮

？

- （预选）下拉列表框
- `<select>`创建下拉列表，`<option>`定义下拉列表中的一个选项

```HTML
<form>
  <select name="drink">
    <option value="Coffee">Coffee</option>
    <option value="Tea" selected>Tea</option>
    <option value="milk">Milk</option>
  </select>
</form>
```

- 多行文本域

```HTML
<form>
  <textarea cols="10" rows="10"></textarea>
</form>
```

- 按钮

```HTML
  <input type="button" value="YES">
```

- 带边框表单

`<fieldset>`标签对表单内元素进行分组，在表单周围绘制边框<br />
`<legend>`标签定义表单标题

```HTML
<form>
  <fieldset>
    <legend style="text-align:center">Title</legend>
    Name:<input type="text" size="10">
    Email:<input type="text" size="10">
    Tele:<input type="text" size="10">
  </fieldset>
</form>
```

- 定义重置按钮

```HTML
<input type="reset">
```

- `<optgroup>`标签用于把选项组合在一起，`label`属性为选项组规定描述标签

```HTML
<form>
  <select>
      <optgroup label="groupA">
        <option value="audi">Audi</option>
      </optgroup>
  </select>
</form>
```

- `<datalist>`标签定义了`input`元素可能的选项列表

```HTML
<form>
  <input list="bowsers" name="bowser">
  <datalist id="bowsers">
    <option value="Chrome">
    <option value="IE">
  </datalist>
</form>
```

## 框架

`frameborder="0\1"`：是否开启边框

```HTML
<iframe src="url" width="200" height="200" frameborder="0"></iframe>
```

- 链接页面显示在iframe框架中

```HTML
<iframe src="layout.html" height="100" width="100" frameborder="0" name="iframe_a"></iframe>
<a href="https://www.baidu.com" target="iframe_a"></a>
```

## 脚本

使用`<script>`标签定义脚本

```HTML
<script>document.write("Hello World");</script>
```

`<noscript>`标签提供无法使用脚本时的替代内容

```HTML
<noscript>抱歉，浏览器不支持javascript</noscript>
```

## 字符实体

不间断空格:`&nbsp`







## 补充

- `href`用于建立这个标签与外部资源之间的关系
- `src`用于替代这个元素，src 指向的内容会嵌入到文档中当前标签所在的位置
- `header`标签用于定义文档的页眉
- `title`属性值可以为元素提供额外的描述信息
- `tr`、`td`、`th`中文字对齐：`<tr valign="top\middle\bottom">`
- `title`属性规定元素的额外信息




