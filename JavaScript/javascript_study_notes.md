# JavaScript 笔记

## JavaScript 基础

### Script 标签

- 在HTML文档中使用`Script`标签插入JavaScript程序；

    ```html
    <html>
        <body>
            <script>
                alert("Hi");
            </script>
        </body>
    </html>
    ```
    
### 外部脚本

- 通过`src`特性将JavaScript代码添加到HTML中；

    ```html
    <script src="/path/to/script.js"></script>
    ```

一个单独的`<script>`不能同时使用`src`特性和内部包裹代码

## JavaScript 代码结构

### 语句

- 语句之间用分号进行分割,每条语句独占一行；

    ```javascript
    alert('Hello');
    alert('World');
    ```
    
### 注释

- 单行注释；

    `//这是单行注释`

- 多行注释；

    <pre>/*这是
    多行注释
    */</pre>

## 现代模式

### strict

- `"use strict"`一般处于脚本最顶部,如处于函数主体开头,则只在该函数中生效；

    ```javascript
    "use strict"
    ```
    
## 变量

变量是数据的"命名存储",使用`let`创建变量

- 创建一个名称为'message'的变量,使用`=`为它赋值,并通过变量名称访问它；

    ```javascript
    let message = 'Hello';
    alert(message);
    ```
- 改变变量的值；

    ```javascript
    let message = 'Hello';
    message = 'World';
    ```

- 将变量的值拷贝给另一个变量；

    ```javascript
    let A = 'Hello';
    let B = 'World';
    B = A;
    ```

### 变量命名

1.变量名称必须仅包含字母,数字,符号`$`和`_`<br />
2.首字母必须非数字

- 命名包括多个单词,采用驼峰式命名法:除了第一个单词,都以大写字母开头；

    ```javascript
    let myVeryLongName = xuehuicong;
    ```
    
- 未采用"use strict"时,可以直接赋值来创建变量(**不推荐**)；

    ```javascript
    num = 5;
    ```

### 常量

- 使用`const`来创建一个常量(**无法重新赋值**)；

    ```javascript
    const num = 1.12;
    ```
    
#### 大写形式的常数

1.使用大写字母和下划线来命名这种常量<br />
2.在执行之前就已知的常量可以用这种方法来命名

- 创建COLOR_RED常量,并使用color变量选择这个常量的值；

    ```javascript
    const COLOR_RED = "#F00";
    let color = COLOR_RED;
    alert(color);
    ```
    
## 数据类型

javascript是动态类型编程语言,变量可以保存任何数据类型

### Number类型

1.`number`类型代表整数和浮点数<br />
2.特殊数值:`Infinity`、`-Infinity`、`NaN`

- `Infinity`代表无穷大,比任何数字都大（通过除以0等到它）；

    ```javascript
    alert(1 / 0);
    alert(Infinity);
    ```
    
- `NaN`代表一个计算错误（粘性的）；

    ```javascript
    alert('abc' / 12);
    ```
    
### BigInt类型

- `Number`类型有大小限制,使用`BigInt`类型表示任意长度的整数(**在整数末尾添加n**)；

    ```javascript
    const bigInt = 11111111111233333333333333n;
    ```
### String类型

三种包含字符串的方式,单引号、双引号和反引号<br />

- 反引号是**功能扩展**引号,可以通过将变量和表达式包装在`${...}`中,来嵌入到字符串中；

    ```javascript
    let name = 'xue';
    alert(`my name is ${name}`);
    alert(`num is ${1 + 2}`);
    ```
    
### Boolean类型

- `boolean`类型只包含两个值:`true`和`false`,也可作为比较的结果；

    ```javascript
    let nameFieldChecked = true;
    let num = 2 > 3;//false
    ```
    
### null值

- `null`仅仅代表这是一个**无、空**或者**值未知**的特殊值；

    ```javascript
    let age = null;
    ```
### undefined值

- `undefined`的含义是**未被赋值**；

    ```javascript
    let x;
    alert(x);//undefined
    ```
    
### typeof运算符

- `typeof`返回参数的类型<br />
1.函数形式:`typeof(x)`<br />
2.运算符形式:`typeof x`

- 所有数据类型例子;<br />
1.`Math`是一个提供数学运算内建的`object`<br />
2.`null`的数据类型是`object`是错误的<br />
3.`alert`t在javascript中是一个函数

    ```javascript
    typeof undefined;//'undefined'
    typeof 0;//'number'
    typeof 111n;//'bigint'
    typeof true;//'bollean'
    typeof 'abc';//'string'
    typeof Symbol('id')//'symbol'
    typeof Math;//'object'
    typeof null;//'object'
    typeof alert;//'function'
    ```
    
## 交互

### `alert`

- 弹出带有信息的**模态窗**,必须处理完当前窗口后才可与其他部分交互；

    ```javascript
    alert('Hello');
    ```

### `prompt`

- `prompt`返回用户在`input`框中输入的文本,取消输入则返回`null`；

    ```javascript
    let age = prompt('How old?', '');
    alert(`I am ${age} years old`);
    ```

### `confirm`

- `confirm`显示一个带有问题以及确定和取消两个按钮的模态窗口；
   
    ```javascript
    let isBoss = confirm('Are you the boss?');
    alert(isBoss);//确定为true,取消为false
    ```
    
## 类型转换
   
大多数情况下,运算符和函数会自动将赋予它们的值转换为正确的类型
   
### 字符串转换

- `alert(value)`将`value`转换为字符串类型；
   
    ```javascript
    let Value = true;
    alert(typeof 123);//boolean
    
    value = String(value);
    alert(typeof value);//string
    ```
   
### 数字型转换
   
- 在算数函数和表达式中,会自动number类型转换；

    ```javascript
    alert('6' / '2');//3
    
    let str = '123';
    alert(typeof str);//string
    
    let num = Number(str);//变成number类型的123
    alert(typeof num);//number 
    ```
    
- number 类型转换规则；
    
    ```javascript
    alert(Number(true));//1
    alert(Number(false));//0
    alert(Number(undefined));//NaN
    alert(Number(null));//0
    alert(Number(' 123 '));//123(只有字符串由数字和空格组成才能转换成功)
    alert(Number(z123));//NaN
    alert(Number(''));//0(字符串为空,转换结果为0)
    ```
### 布尔型转换

- 为"空"的值(`0`、空字符串、`null`、`undefined`和`NaN`)将变为`false`其他变为`true`；

    ```js
    alert(Boolean(0));//false
    alert(Boolean(''));//false
    alert(Boolean(null));//false
    alert(Boolean(undefined));//false
    alert(Boolean(NaN));//false
    
    alert(Boolean(' '));//true
    alert(Boolean(1));//true
    alert(Boolean('0'));//true
    ```
    
## 运算符

`5 * 2`有两个运算元,左运算元`5`和右运算元`2`

- 一个运算符只有一个运算元称为**一元运算符**

    ```javascript
    let x = 1;
    x = -x;
    alert(x);//-1(一元负号运算符)
    ```
- 一个运算符有两个运算元称为**二元运算符**

    ```javascript
    let a = 1, b = 3;
    alert(b - a);//2
    ```
    
### 字符串连接,二元运算符+

- 加号`+`用于连接各个字符串

    ```javascript
    let s = 'My' + 'string';
    alert(s);//Mystring
    ```
    
- 只要一个运算元是字符串,另一个运算元也将转换为字符串(**只生效与二元运算符+**)

    ```javascript
    alert('1' + 2);//'12'
    
    alert(2 + 2 + '3');//'43'
    ```
- 其他算术运算符只对数字起作用，并将运算元转换为数字

    ```javascript
    alert('6' / 2);//3
    alert(8 - '2');//6
    ```
    
### 数字转化,一元运算符+

- 一元运算符加号`+`应用于单个值,对数字没有任何作用,运算元不是数字则转换为数字

    ```js
    let x = 1;
    alert(+x);//1
    
    let y = -2;
    alert(+y);//-2
    
    alert(+true);//1
    alert(+'');//0
    
    alert(+x + +y);//数字1+数字-2等于数字-1
    ```

### 赋值运算符

- 赋值的优先级很低

    ```js
    let a = 2 * 2 + 1;
    alert(a);//5
    ```
    
    ```js
    let a = 1;
    let b = 2;
    let c = 3 - (a = 1 + b);
    alert(c);//0
    alert(a);//3
    ```
    
- 链式赋值

    ```js
    let a, b, c;
    a = b = c = 2 + 2;
    alert(a);//4
    alert(b);//4
    alert(c);//4
    ```
    
### 原地修改

- 使用运算符`+=`和`*=`进行缩写

    ```js
    let n = 2;
    n += 5;//now n = 7(n = n + 5)
    n *= 2;//now n = 14(n = n * 2)
    alert(n);//14
    ```
    
- 简写的优先级和赋值一样,很低

    ```js
    let n = 2;
    n *= 2 + 5;//14
    ```

### 自增/自减

自增和自减只能应用于变量

- 自增`++`将变量与1相加

    ```js
    let counter = 2;
    counter++;
    alert(counter);//3
    ```

- 自减`--`将变量与1相减

    ```js
    let counter = 2;
    counter--;
    alert(counter);//1
    ```
    
- 前置返回一个新值,后置返回原来的值

    ```js
    let counter = 1;
    a = counter++;//后置返回旧值
    alert(a);//1
    ```
    
    ```js
    let counter = 1;
    a = ++counter;//前置返回新值
    alert(a);//2
    ```
    
- 自增/自减和其他运算符

    ```javascript
    let counter = 1;
    alert(2 * ++counter);//4
    
    let a = 1;
    alert(2 * counter++);//2
    ```
### 位运算符
    
    
### 逗号运算符



## 值的比较

### 基本比较例子

- 相等：`a == b`
- 不相等：`a != b`

### 比较结果为Boolean类型

- 比较的结果可以赋值给任意变量

    ```javascript
    let result = 5 > 2;
    alert (result);//true
    ```
### 字符串比较

- 根据字符大小进行比较（小写字符大于大写字母）

    ```javascript
    alert ('ABC' > 'AB');//true
    ```
### 不同类型间比较

- 先转换至数字类型

    ```javascript
    alert ('12' > 2);//true
    ```
    
### 严格相等

- 区分`0`和`false`（比较时不会做任何数据类型转换）

    ```javascript
    alert ('' === false);//false
    alert (`abc` !== false);//true
    ```
### null与undefined

- 使用严格相等时，因为不同数据类型不相等
- 使用非严格相等时，它们相等
- 使用数学式或其他比较方法时，`null`转化为`0`，`undefined`转化为`NaN`
- `undefined`在比较中被转换为了`NaN`,`NaN`与任何值比较都会返回`false`
- `undefined`只与`null`相等

## 条件分支`if`和`?`

### if语句

- `if`语句计算括号里的条件表达式，计算结果为`true`则执行对应代码块（使用`{}`包装代码块）

    ```js
    let year = prompt ('How old are you?', '');
    if (year == 20) {
        alert ('yes');
        alert ('ok');
    }
    ```




    
    
    
    
    
    
    
    
    
    
    
    


## JavaScript 布局

- 通常JavaScript代码放在`<head> </head>`中;

    ```JavaScript
    <html>
        <head>
            <script type="text/JavaScript">
                alert('Hello, world');
            </script>
        </head>
        <body>
            ...
        </body>
    </html>
    ```

    > `type`默认属性为:`JavaScript`,不必显示指定。

- 将JavaScript代码单独放在`.js`文件中;

    ```JavaScript
    <html>
        <head>
            <script src="/static/js/abc.js"></script>
        </head>
        <body>
            ...
        </body>
    </html>
    ```
    
    > 多个页面可以同时引用一个`.js`文件
    
## JavaScript 基础
    
### 基本语法
    
JavaScript每个语句以`;`结尾,语句块用`{...}`
    
- 赋值语句;
    
    `var x = 1;`

- 一个字符串;

    `'Hello, world';`

- 代码包含两个语句,用`;`表示语句结束;

    `var x = 1; var y = 2;`

- 语句块是一组语句的集合,下面代码先做了一个判断,如判断成立,则执行`{...}`中所有语句;

    `if (2 > 1) {
        x = 1;
        y = 2;
        z = 3;
    }`

- `{...}`进行嵌套,形成层级结构;

    ```JavaScript
    if (2 > 1) {
        x = 1;
        y = 2;
        z = 3;
        if (x < y) {
        z = 4;
        }
        if (x > y) {
        z = 5;
        }
    }
    ```
    
- JavaScript注释;

    ```JavaScript
    //这是一行注释
    
    /*这
    是
    一块
    注释*/
    ```
    
### 数据类型和变量
    
#### Number

- JavaScript不区分浮点数和整数,统一用Number表示;
    
    ```JavaScript
    123; // 整数
    0.456; // 浮点数
    1.2345e3; // 科学计数法表示1.2345x1000,等同于1234.5
    -99; // 负数
    NaN; // NaN表示Not a Number,当无法计算时用NaN表示
    Infinity; // Infinity表示无限大,数值超过JavaScript的Number最大值时,表示为Infinity
    ```
    
- JavaScript四则运算

    ```JavaScript
    1 + 2; // 3
    (1 + 2) * 5 / 2; // 7.5
    2 / 0; // Infinity
    0 / 0; // NaN
    10 % 3; // 1
    ```
#### 字符串

字符串是以`'`或`""`括起来的任意文本,比如`'abc'`,`"efg"`

#### 布尔值

- 一个布尔值只有`true`、`false`两种值

    ```JavaScript
    true; // true值
    false; // false值
    2 > 1; // true值
    2 >= 3; // false值
    ```

- `&&`运算是与运算,只有都为`true`,结果才能是`true`

    ```JavaScript
    true && true; // 计算结果为true
    true && false; // 计算结果为false
    false && true && true // 计算结果为false
    ```
    
- `||`运算是或运算,只要其中一个为`true`,运算结果为`true`

    ```JavaScript
    false || false; //计算结果为false
    false || true; // 计算结果为true
    false || false || true; //计算结果为true
    ```
    
- `!`运算是非运算,它是一个单目运算符,把`true`变成`false`,把`false`变成`true`

    ```JavaScript
    ! true; // 结果为false
    ! false; // 结果为true
    ```
    
- 布尔值用在条件判断中
    
    ```JavaScript
    var age = 15;
    if (age >= 18) {
        alert('adult');
    } else {
        alert('teenager');
    }
    ```
    
#### 比较运算符

- `==`比较会自动转换数据类型再比较

    ```JavaScript
    false == 0; // true
    2 > 5; // false
    7 == 7; // true
    ```
    
- `===`比较不会自动转换数据类型,如不一致返回`false`,如一致再比较

    ```JavaScript
    false === 0; // false
    1 + 2 === 4 - 1; // true
    ```
    
- `NaN`与其他值都不相等,包括自己,只有`isNaN()`函数能判断`NaN`

    ```JavaScript
    NaN === NaN; // false
    isNaN(NaN); //不确定*不是Number所有返回true
    ```

- 浮点数相等比较

    ```javaScript
    1 / 3 === (1 - 2 / 3); // false
    ```


#### 数组

- 数组是一组按顺序排列的集合,集合的每个值为元素

    ```JavaScript
    [1, 2, 3.14, 'Hello', null,true];
    ```
