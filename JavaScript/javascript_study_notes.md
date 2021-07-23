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

- 语句之间用分号进行分割，每条语句独占一行；

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

- `"use strict"`一般处于脚本最顶部，如处于函数主体开头，则只在该函数中生效；

    ```javascript
    "use strict"
    ```
    
## 变量

变量是数据**命名存储**，使用`let`创建变量

- 创建一个名称为`message`的变量，使用`=`为它赋值，并通过变量名称访问它；

    ```javascript
    let message = "Hello";
    alert(message);
    ```
- 改变变量的值；

    ```javascript
    let message = "Hello";
    message = "World";
    ```

- 将变量的值拷贝给另一个变量；

    ```javascript
    let A = "Hello";
    let B = "World";
    B = A;
    ```

### 变量命名

1.变量名称必须仅包含字母，数字，符号`$`和`_`<br />
2.首字母必须非数字

- 命名包括多个单词，采用驼峰式命名法:除了第一个单词，都以大写字母开头；

    ```javascript
    let myVeryLongName = "xuehuicong";
    ```
    
- 未采用"use strict"时，可以直接赋值来创建变量(**不推荐**)；

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

- 创建COLOR_RED常量，并使用color变量选择这个常量的值；

    ```javascript
    const COLOR_RED = "#F00";
    let color = COLOR_RED;
    alert(color);
    ```
    
## 数据类型

javascript是动态类型编程语言，变量可以保存任何数据类型

### Number类型

1.`number`类型代表整数和浮点数<br />
2.特殊数值:`Infinity`、`-Infinity`、`NaN`

- `Infinity`代表无穷大，比任何数字都大（通过除以0得到它）；

    ```javascript
    alert(1 / 0);
    alert(Infinity);
    ```
    
- `NaN`代表一个计算错误（粘性的）；

    ```javascript
    alert('abc' / 12);
    ```
    
### BigInt类型

- `Number`类型有大小限制，使用`BigInt`类型表示任意长度的整数(**在整数末尾添加n**)；

    ```javascript
    const bigInt = 11111111111233333333333333n;
    ```
### String类型

三种包含字符串的方式，单引号、双引号和反引号<br />

- 反引号是**功能扩展**引号，可以通过将变量和表达式包装在`${...}`中，来嵌入到字符串中；

    ```javascript
    let name = 'xue';
    alert(`my name is ${name}`);
    alert(`num is ${1 + 2}`);
    ```
    
### Boolean类型

- `boolean`类型只包含两个值:`true`和`false`，也可作为比较的结果；

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

- `typeof`返回参数的类型；<br />
1.函数形式:`typeof(x)`<br />
2.运算符形式:`typeof x`

- 所有数据类型例子；<br />
1.`Math`是一个提供数学运算内建的`object`<br />
2.`null`的数据类型是`object`是错误的<br />
3.`alert`在javascript中是一个函数

    ```javascript
    typeof undefined;//"undefined"
    typeof 0;//"number"
    typeof 111n;//"bigint"
    typeof true;//"bollean"
    typeof "abc";//"string"
    typeof Symbol("id")//"symbol"
    typeof Math;//"object"
    typeof null;//"object"
    typeof alert;//"function"
    ```
    
## 交互

### `alert`

- 弹出带有信息的**模态窗**，必须处理完当前窗口后才可与其他部分交互；

    ```javascript
    alert('Hello');
    ```

### `prompt`

- `prompt`返回用户在`input`框中输入的文本，取消输入则返回`null`；

    ```javascript
    let age = prompt("How old?", '');
    alert(`I am ${age} years old`);
    ```

### `confirm`

- `confirm`显示一个带有问题以及确定和取消两个按钮的模态窗口；
   
    ```javascript
    let isBoss = confirm("Are you the boss?");
    alert(isBoss);//确定为true,取消为false
    ```
    
## 类型转换
   
大多数情况下，运算符和函数会自动将赋予它们的值转换为正确的类型
   
### 字符串转换

- `alert(value)`将`value`转换为字符串类型；
   
    ```javascript
    let value = true;
    alert(typeof value);//boolean
    
    value = String(value);
    alert(typeof value);//string
    ```
   
### 数字型转换
   
- 在算数函数和表达式中，会自动进行number类型转换；

    ```javascript
    alert('6' / '2');//3
    
    let str = "123";
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
    alert(Number(" 123 "));//123(只有字符串由数字和空格组成才能转换成功)
    alert(Number(z123));//NaN
    alert(Number(""));//0(字符串为空,转换结果为0)
    ```
### 布尔型转换

- 为"空"的值(`0`、空字符串、`null`、`undefined`和`NaN`)将变为`false`其他变为`true`；

    ```js
    alert(Boolean(0));//false
    alert(Boolean(""));//false
    alert(Boolean(null));//false
    alert(Boolean(undefined));//false
    alert(Boolean(NaN));//false
    
    alert(Boolean(" "));//true
    alert(Boolean(1));//true
    alert(Boolean("0"));//true
    ```
    
## 运算符

`5 * 2`有两个运算元,左运算元`5`和右运算元`2`

- 一个运算符只有一个运算元称为**一元运算符**；

    ```javascript
    let x = 1;
    x = -x;
    alert(x);//-1(一元负号运算符)
    ```
- 一个运算符有两个运算元称为**二元运算符**；

    ```javascript
    let a = 1, b = 3;
    alert(b - a);//2
    ```
    
### 字符串连接,二元运算符+

- 加号`+`用于连接各个字符串；

    ```javascript
    let s = "My" + "string";
    alert(s);//Mystring
    ```
    
- 只要一个运算元是字符串,另一个运算元也将转换为字符串(**只生效与二元运算符+**)；

    ```javascript
    alert('1' + 2);//'12'
    
    alert(2 + 2 + '3');//'43'
    ```
- 其他算术运算符只对数字起作用，并将运算元转换为数字；

    ```javascript
    alert('6' / 2);//3
    alert(8 - '2');//6
    ```
    
### 数字转化,一元运算符+

- 一元运算符加号`+`应用于单个值,对数字没有任何作用,运算元不是数字则转换为数字（效果和`Number(...)`相同）；

    ```javascript
    let x = 1;
    alert(+x);//1
    
    let y = -2;
    alert(+y);//-2
    
    alert(+true);//1
    alert(+'');//0
    
    alert(+x + +y);//数字1+数字-2等于数字-1
    ```

### 赋值运算符

- 赋值的优先级很低；

    ```javascript
    let a = 2 * 2 + 1;
    alert(a);//5
    ```
    
    ```javascript
    let a = 1;
    let b = 2;
    let c = 3 - (a = 1 + b);
    alert(c);//0
    alert(a);//3
    ```
    
- 链式赋值；

    ```javascript
    let a, b, c;
    a = b = c = 2 + 2;
    alert(a);//4
    alert(b);//4
    alert(c);//4
    ```
    
### 原地修改

- 使用运算符`+=`和`*=`进行缩写；

    ```js
    let n = 2;
    n += 5;//now n = 7(n = n + 5)
    n *= 2;//now n = 14(n = n * 2)
    alert(n);//14
    ```
    
- 简写的优先级和赋值一样,很低；

    ```js
    let n = 2;
    n *= 2 + 5;//14
    ```

### 自增/自减

自增和自减只能应用于变量

- 自增`++`将变量与1相加；

    ```js
    let counter = 2;
    counter++;
    alert(counter);//3
    ```

- 自减`--`将变量与1相减；

    ```js
    let counter = 2;
    counter--;
    alert(counter);//1
    ```
    
- 前置返回一个新值,后置返回原来的值；

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
    
- 自增/自减和其他运算符；

    ```javascript
    let counter = 1;
    alert(2 * ++counter);//4
    
    let a = 1;
    alert(2 * counter++);//2
    ```
### 位运算符

?
    
### 逗号运算符

- 处理多个语句，只有最后的语句结果会被返回（优先级最低）；

    ```javascript
    let a =(1 + 2, 4 + 2);
    alert (a);//6
    ```

## 值的比较

### 基本比较例子

- 相等：`a == b`
- 不相等：`a != b`

### 比较结果为Boolean类型

- 比较的结果可以赋值给任意变量；

    ```javascript
    let result = 5 > 2;
    alert (result);//true
    ```
### 字符串比较

- 根据字符大小进行比较（小写字母大于大写字母）；

    ```javascript
    alert ('ABC' > 'AB');//true
    ```
### 不同类型间比较

- 先转换至数字类型；

    ```javascript
    alert ('12' > 2);//true
    ```
    
### 严格相等

- 区分`0`和`false`（比较时不会做任何数据类型转换）；

    ```javascript
    alert ('' === false);//false
    alert ('abc' !== false);//true
    ```
### null与undefined

- 使用严格相等时，因为不同数据类型不相等；
- 使用非严格相等时，它们相等；
- 使用数学式或其他比较方法时，`null`转化为`0`，`undefined`转化为`NaN`；
- `undefined`在比较中被转换为了`NaN`，`NaN`与任何值比较都会返回`false`；
- `undefined`只与`null`相等；

## 条件分支`if`和`?`

### if语句

- `if`语句计算括号里的条件表达式，计算结果为`true`则执行对应代码块（使用`{}`包装代码块）；

    ```javascript
    let year = prompt ("How old are you?", '');
    if (year == 20) {
        alert ('yes');
        alert ('ok');
    }
    ```

### 布尔转换

- `if`语句计算圆括号内的表达式，将计算结果转换为布尔型；

    ```javascript
    if (0) {...}//不执行代码块
    if (1) {...}//执行代码块
    ```
    
    ```javascript
    let cond = (year == 2015);
    if (cond) {...}//将未计算的布尔值传入`if`语句
    ```

### else语句

- 判断不成立，则执行`else`内部代码；

    ```javascript
    if (year == 2015) {
        alert ('Good');
    } else {
        alert ('Bad');
    }
    ```

### 多个条件：else if

- 例

    ```javascript
    if (year < 2015) {
        alert ('Too early');
    } else if (year > 2015) {
        alert ('Too late');
    } else {
        alert ('Exactly');
    }
    ```

### 条件运算符`?`

- 例

    ```javascript
    let accessAllowed = (age > 18) ? true : false;
    ```
    
### 多个`?`

- 例

    ```javascript
    let message = (age < 3) ? 'Hi, baby' :
    (age < 18) ? 'Hello' :
    (age < 100) ? 'Greetings' :
    'What an unusual age';
    ```
    
### `if`的非常规使用

- 使用`?`代替if语句；

    ```javascript
    let company = prompt("Which company created JavaScript?", '');
    
    (company == 'Netscape') ?
        alert('Right!') : alert('Wrong.');
    ```

## 逻辑运算符

### `||`或

- 参与运算的任意一个参数为`true`，返回的结果就为`true`,否则为`false`；
- 如果操作数不是布尔值，则转化为布尔值进行运算；

    ```javascript
    let hour = 9;
    if (hour < 10 || hour > 18) {
        alert ('The office is closed.');
    }
    ```

#### 或运算寻找第一个真值

- 一个或运算`||`的链，将返回第一个真值，如果没有真值就返回最后一个值（原始值）；

    ```javascript
    alert (null || 1);//1
    alert (null || undefined || 0);//0
    ```
    
- 获取变量列表或表达式第一个真值（没有设置则用`'Anonymous'`）；

    ```javascript
    let firstName = '';
    let lastName = '';
    let nickName = 'SuperCoder';
    alert (firstName || lastName || nickName || 'Anonymous');//SuperCoder
    ```

- 达到第一个真值后不处理其他参数直接返回该值，这称为**短路求值**；

    ```javascript
    true || alert ('no print');
    false || alert ('print');//print
    ```

### `&&`与

- 两个操作数都为真值时，与运算返回`true`，否则返回`false`；

    ```javascript
    alert (true && true);//true
    alert (false && true);//false
    
    if (12 < 13 && 2 > 1) {
        alert ('YES');
    }//YES
    ```

#### 与运算寻找第一个假值

- 如果结果是`false`就停止计算返回初始值，如果都是`true`则返回最后一个操作数；

    ```javascript
    alert (1 && 0);//0
    alert (null && 1);//null
    ```

### `!`非

- 将操作数转化为布尔类型并返回相反的值
- 第一个非运算将该值转化为布尔类型并取反，第二个非运算再次取反，最后得到一个任意值到布尔值的转化

    ```javascript
    alert (!0);//true
    alert (!!null);//false
    alert (Boolean (null))//false
    ```
    
## 空值合并运算符`??`

- 值既不是`null`也不是`undefined`的表达式称为**已定义的**
- 如果第一个参数不是`null/undefined`则`??`返回第一个参数，否则返回第二个参数
- `??`为可能是未定义的变量提供一个默认值

    ```javascript
    let user;
    alert (user ?? 'john');//john
    ```

    ```javascript
    let firstName = null;
    let lastName = undefined;
    let nickName = 'supercoder';
    
    alert (firstName ?? lastName ?? nickName ?? 'Anonymous');
    ```
   
- 可以使用`||`替换`??`，两者有区别
1.`||`返回第一个**真**值
2.`??`返回第一个**已定义**的值

### 优先级

- `??`运算符比`*`运算符等级低

    ```javascript
    let height = null;
    let width = null;
    let area = height ?? 100 * width ?? 50;
    alert (area);//错误的结果
    ```

### `??`与`&&`和`||`使用需要添加括号明确优先级

 - 例
 
    ```javascript
    let x = (1 && 2) ?? 3;
    alert (x);//2
    ```

## 循环：while和for

### `while`循环

- 需要重复一些操作时使用`while`循环

    ```javascript
    let i = 0;
    while (i < 3) {
    alert (i);
    i++;
    }
    ```

- 单行循环体不需要大括号

    ```javascript
    let i = 3;
    while (i) alert (i--);
    ```

### `do...while`循环

- 循环首先执行循环体，然后检查条件，当条件为真时，重复执行循环体

    ```javascript
    let i = 0;
    do {
    alert (i);
    i++;
    } while (i < 3);
    ```
    
### `for`循环

- `begin`执行一次，然后进行迭代，每次检查`condition`后，执行`body`和`step`

|                |                |                                             |
|:-              |:-              |:-                                           |
|begin           |`i = 0`         |进入循环时执行一次。                           |
|condition       |`i < 3`         |在每次循环迭代之前检查，如果为 false，停止循环。 |
|body（循环体）   |`alert(i)`      |条件为真时，重复运行。                         |
|step            |`i++`           |在每次循环体迭代后执行。                       |

    ```javascript
    for (let i = 0; i < 3; i++) {
    alert (i);
    }
    ```
### 内联变量声明

- 在循环体内声明的变量只在循环体内可见

    ```javascript
    for (let i = 0; i < 3; i++) {
        alert (i);//0, 1, 2
    }
    alert (i);//错误，没有这个变量
    ```
    
- 在循环体外声明变量

    ```javascript
    let i = 0;
    for (; i < 3; i++) {
        alert (i);//0, 1, 2
    }
    alert (i);//3
    ```

### 省略语句段

- `for`循环的任何语句都可以被省略

    ```javascript
    let i = 0;
    for (; i < 3;) {
        alert (i++);
    }
    ```

### 跳出循环

- 使用`break`指令可以随时终止循环

    ```javascript
    let sum = 0;
    while (true) {
        let value = +prompt ('Enter a number', '');
        if (!value) break;
        sum += value;
    }
    alert ('Sum:' + sum);
    ```
    
### 继续下一次迭代

- `continue`不会停掉整个循环，而是停止当前这一次迭代，并强制启动新一轮循环

    ```javascript
    for (let i = 0; i < 10; i++) {
        if (i % 2 == 0) continue;
        alert (i);
    }//1,3,5,7,9
    ```
    
- 禁止`break`和`continue`在`?`右边

    ```javascript
    (i > 5) ? alert(i) : continue;
    ```
    
### `break/continue`标签

- 从多层嵌套中跳出来，需要使用标签（循环之前带有冒号的标识符）
- 标签不能跳到代码的任意位置

    ```javascript
    outer: for (let i = 0; i < 3; i++) {
        for (let j = 0; j < 3; j++) {
            let input = prompt (`Value at coords (${i}, ${j})`, '');
            if (!input) break outer; 
        }
    }
    alert ('Done!');
    ```
    
## `Switch`语句

- `switch`语句至少有一个`case`代码块和一个可选的`default`代码块

### 语法

- 比较`a`值与第一个`case`（也就是3）是否严格相等，然后第二个`case`
- 如果相等，`switch`语句就执行相应`case`下的代码块，直到遇到`break`语句
- 如果没有符合的`case`，则执行`default`代码块
- **如果没有`break`, 程序将不经过任何检查就会继续执行下一个`case`**

    ```javascript
    let a = 2 + 2;
    
    switch (a) {
        case 3:
            alert ("Too small");
            break;
        case 4:
            alert ("Exactly!");
            break;
        case 5:
            alert ("Too large");
            break;
        default:
            alert ("I don't know such values");
    }
    ```

### `case`分组

- 共享同一段代码的几个`case`分支可以被分为一组并执行同样的代码

    ```javascript
    let a = 3;
    
    switch (a) {
        case 4:
            alert ('Right!');
            break;
            
        case 3:
        case 5:
            alert ('Wrong!');
            alert ("Why don't you take a math class?");
            break;
            
        default:
        alert ('The result is strange. Really.');
    }
    ```
    
## 函数

- 函数是程序的主要`构建模块`，函数可以使代码多次被调用不需要重复写

### 函数声明

- `function`是关键字，`showMessage`是函数名，`（）`之间是参数，`{}`之间是函数体,通过`showMessage()`调用函数

    ```javascript
    function showMessage() {
        alert ('Hello');
    }
    
    showMessage();
    ```
    
### 局部变量

- 在函数中声明的变量只在该函数内部可见
- 函数外声明的变量称为全局变量

    ```javascript
    function showMessage () {
        let message = 'Hello';
        alert (message);
    }
    
    showMessage ();//Hello
    alert (message);//错误，变量是函数内部变量
    ```
    
### 外部变量

- 函数对外部变量拥有全部的访问权限，函数也可以修改外部变量

    ```javascript
    let userName = 'John';
    
    function showMessage() {
        userName = "Bob";
        
        let message = 'Hello, ' + userName;
        alert (message);
    }

    alert (userName);//John
    showMessage();//Hello, Bob
    alert (userName);Bob
    ```
    
- 如果在函数内部声明了同名变量，那么函数会遮蔽外部变量

    ```javascript
    let userName = 'John';

    function showMessage() {
    let userName = "Bob";
    
    let message = 'Hello,' + userName;
    alert (message);
    }
    
    showMessage();//Hello, Bob
    alert (userName);//John,函数没有访问外部变量
    ```

### 参数

- 使用参数将任意数据传递给函数

    ```javascript
    function showMessage(from, text) {
        alert (from + ': ' + text);
    }
    showMessage('Ann', 'Hello!');//Ann: Hello!
    ```
    
- 变量`from`传递给函数，（函数会修改`from`变量） ，但在函数外部看不到更改，函数修改的是复制的变量值副本

    ```javascript
    function showMessage(from, text) {
        from = '*' + ':' + '*';
        alert (from + ': ' + text);
    }
    let from = 'Ann';
    
    showMessage(from, "Hello");//*Ann*: Hello
    alert (from);//Ann
    ```

### 默认值

- 如果未提供参数，那么其默认值则是`undefined`，提供的默认值是字符串也可以是表达式

    ```javascript
    function showMessage(from, text = 'no text given') {
        alert (from + ': ' + text);
    }
    
    showMessag('Ann');// Ann: no text given
    ```
    
### 后备的默认参数

- 将参数默认值放在函数执行而不是函数声明也行

    ```javascript
    function showMessage(text) {
        if (text === undefined) {
            text = 'empty message';
        }
        alert (text);
    }
    
    showMessage();//empty message
    ```
- 使用`||`运算符

    ```javascript
    function showMessage(text) {
        text = text || 'empty';
        alert (text);
    }
    
    showMessage();//empty
    ```

- 使用空值合并运算符`??`，`0`会被视为正常值不被合并

    ```javascript
    function showCount(count) {
        alert (count ?? 'unknown');
    }

    showCount(0);//0
    showCount(null);//unknown
    showCount();//unknown
    ```
    
### 返回值

- 函数可以将一个值返回到调用代码中作为结果

    ```javascript
    function sum(a, b) {
        return a + b;
    }
    let result = sum(2, 3);
    alert (result);//5
    ```
    
- 空值的`return`或没有`return`的函数返回值为`undefined`

    ```javascript
    function doNothing() {}
    alert (doNothing() === undefined);// true
    ```
    
    ```javascript
    function doNothing() {
        return;
    }
    
    alert (doNothing() === undefined);//true
    ```
    
- `return`应与表达式在同一行，或者使用`()`

    ```javascript
    return
    (some + long)//error

    return;
    (some + long)//error

    return (
        some + long
        + or
    )//将表达式放在多行
    ```

### 函数命名

- 用动词前缀开始一个函数

- `"get..."`：返回一个值
- `"calc..."`：计算某些内容
- `"create..."`：创建某些内容
- `"check..."`：检查某些内容并返回boolean值

    ```javascript
    showMessage()  //显示信息
    getAge()  //返回age（gets it somehow）
    calcSum()  //计算求和并返回结果
    createForm()  //创建表格（通常会返回它）
    checkPermission()  //检查权限并返回 true/false
    ```

- 一个函数一个行为，如需多个功能请创建更多函数

### 函数 == 注释

- 如果函数功能复杂，请拆分成几个函数

    ```javascript
    function showPrimes() {}
    ```
    
## 函数表达式

- 创建函数并分配给了一个变量

    ```javascript
    let sayHi = function() {
        alert ("Hello");
    };
    ```
- 函数是一个特殊值，我们可以复制它到其他变量

    ```javascript
    function sayHi() {
        alert ('Hello');
    }
    
    let func = sayHi;
    func();//Hello
    sayHi();//Hello
    ```

### 回调函数

- `ask`的两个参数值`showOk`和`showCancel`称为回调函数

    ```javascript
    function ask(question, yes, no) {
        if (confirm(question)) yes()
        else no();
    }

    function showOk() {
        alert ("You agreed.");
    }

    function showCancel() {
        alert ("You canceled the execution.");
    }
    
    ask("Do you agree?", showOk, showCancel);
    ```
    
- 直接在`ask()`内进行函数声明，称为匿名**函数**（没有分配变量），在`ask`外无法访问

    ```javascript //简写
    function ask(question, yes, no) {
        if (confirm(question)) yes()
        else no();
    }

    ask(
        "Do you agree?",
        function() {alert ("You agreed.");},
        function() {alert ("You canceled the execution.");}
    );
    ```
    
### 函数表达式 vs 函数声明

- 函数表达式：在代码执行到达时被创建，并且仅从那一刻可用
- 函数声明：在函数声明被定义前，就可以被调用

- 严格模式下，当一个函数声明在一个代码块内时，它在该代码块内的任何位置都是可见的，但在代码块外不可见

    ```javascript
    "use strict"
    let age = 16;
    
    if (age < 18) {
        welcome();//Hello

        function welcome() {
            alert ("Hello!");
        }
    welcome();//Hello
    } else {

        function welcome() {
            alert ("Greetings!");
        }
    }

    welcome();//Error
    ```
    
    ```javascript
    "use strict"
    let age = prompt ("What is your age?", 18);

    let welcome = (age < 18) ?
        function welcome() {alert ("Hello!");} :
        function welcome() {alert ("Greetings!");};

    welcome();
    ```
    
## 箭头函数

- 使用参数对`=>`右侧求值并返回结果

    ```javascript
    let sum = (a, b) => a + b;
    alert ( sum(1, 2) );//3
    ```
- 只有一个参数和无参数

    ```javascript
    let double = n => n * 2;
    alert ( double(3) );//6
    ```
    
    ```javascript
    let sayHi = () => alert ("Hello!");
    sayHi();//Hello!
    ```

- 动态创建一个函数

    ```javascript
    let age = prommpt ("What is your age?", 18);
    
    let welcome = (age < 18) ?
        () => alert ("Hello!") :
        () => alert ("Greetings!");

    welcome();
    ```
    
### 多行的箭头函数

- 使用花括号开始一个多行函数，使用一个`return`将需要返回的值进行返回

    ```javascript
    let sum = (a, b) => {
        let result = a + b;
        return result;
    };

    alert ( sum(2, 4) );//6
    ```
    
## 对象

- 通过带有可选**属性列表**的`{}`来创建对象
- 一个属性是一个键值对`(key:value)`,`key`是一个字符串（属性名），`value`可以是任何值

    ```javascript
    let user = new Object();//构造函数
    let user = {};//字面量
    ```
    
### 文本和属性

- 建位于冒号左边，值位于冒号右面，使用`.`符号访问属性值
- `.`符号要求`key`是有效变量标识符：不包含空格，不以数字开头，不包含特殊符号（除`$`和`_`）

    ```javascript
    let user = {
        name: "John",//name是建，John是值
        age: 30,
    };
    
    alert (user.age);//30
    ```
    
- 属性的值可以是任意类型

    ```javascript
    user.isAdmin = true;
    ```

- 使用`delete`操作符移除属性

    ```javascript
    delete user.age;
    ```

- 多字词属性名必须加`""`

    ```javascript
    let user = {
        name: "John",
        age: 30,
        "likes birds": true,
    };
    ```
    
- 用`const`声明的对象能修改值但不是修改绑定

    ```javascript
    const user = {
        name: "John",
    };
    
    user.name = "xue";
    alert (user.name);//xue
    
    user = {
        name: "xxx",        
    };//Error
    ```
    
### 方括号

- 对于多词属性，使用`[]`

    ```javascript
    let user = {};
    
    user["likes birds"] = true;
    
    alert (user["likes birds"]);//true
    
    delete user["likes birds"];
    ```
    
- 通过任意表达式获取属性名

    ```javascript
    let key = "likes birds";

    user[key] = true;
    ```
    
- 通过用户输入的`key`值，对变量`key`进行访问（`.`符号不能使用这种方式）

    ```javascript
    let user ={
        name: "John",
        age: 30,
    };

    let key = prompt ("What do you want to know about the user?", "name");
    alert ( user[key] );//John
    ```
    
### 计算属性

- 当创建对象时，在对象字面量中使用方括号，这叫**计算属性**
- `[fruit]`含义是属性名应该从`fruit`变量中获取
- 如果输入`"apple"`，`bag`将变为`{apple: 5}`

    ```javascript
    let fruit = prompt ("Which fruit to buy?", "apple");
    
    let bag = {
        [fruit]: 5,
    };
    
    alert (bag.apple);//5
    ```
   
    ```javascript
    let fruit = prompt ("Which fruit to buy?", "apple");
    let bag = {};
    bag[fruit] = 5;

    alert ( bag[fruit] ); 
    ```
    
- 方括号中使用表达式

    ```javascript
    let fruit = 'apple';
    let bag = {
        [fruit + 'Computers']: 5,//bag.appleComputers = 5
    };
    ```

### 属性值简写

- 使用已存在的变量当做属性名

    ```javascript
    function makeUser(name, age) {
        return {
            name: name,
            age: age,
        };
    }

    let user = makeUser("John", 30);
    alert (user.name);//John
    ```
    
- 属性值缩写(可以和正常方式混用)

    ```javascript
    function makeUser(name, age) {
        return {
            name,
            age,
        };
    }
    ```
    
### 属性名称限制

- 属性命名不受任何限制，其他类型会被自动转换为字符串

    ```javascript
    let obj = {
        0: "test",
    };
    alert (obj[0]);//test
    alert (obj["0"]);//test
    ```
    
### 属性存在性测试，`in`操作符

- `javascript`能够访问任何属性，即使属性不存在也不会报错，读取不存在的属性只会得到`undefined`
- `in`左边是**属性名**(带引号的字符串)

    ```javascript
    let user = {};

    alert (user.age === undefined);//true
    alert ("age" in user);//false
    ```
    
- 省略引号，`in`左边是一个变量

    ```javascript
    let user = {age: 30,};
    
    let key = "age";
    alert (key in user);//true
    ```

- 当属性存在，但存储的值是`undefined`时，需要使用`in`运算符

    ```javascript
    let obj = {
        test: undefined,
    };

    alert (obj.test);//undefined
    alert ("test" in obj);//true
    alert (obj.test === undefined);//true
    ```

### `for...in`循环

- 遍历一个对象中所有的建(key)，可以使用`for...in`循环

    ```javascript
    let user = {
        name: "John",
        age: 30,
        isAdmin: true,
    };
    
    for (let key in user) {
        alert (key);
        alert ( user[key] );
    };
    ```

### 像对象一样排序

- 整数属性会被进行排序，其他属性按照创建的顺序显示

    ```javascript
    let codes = {
        "49": "Germany",
        "41": "Switzerland",
        "1": "USA",
    };

    for (let code in codes) {
        alert (code);//1, 41, 49
    };
    ```
    
- 整数属性是指一个可以在不做任何更改的情况下与一个整数进行相互转换的字符串
    
    ```javascript
    alert ( String(Math.trunc(Number("49"))) );//"49"
    alert ( String(Math.trunc(Number("+49"))) );//"49"
    alert ( String(Math.trunc(Number("1.2"))) );//1
    alert ( String(Math.trunc(Number("-49"))) );//"-49"
    ```
    

## 对象引用和复制

- 赋值了对象的变量存储的不是对象本身，而是该对象**在内存中的地址**，是对该对象的引用


    ```javascript
    let user = {
        name: "John",
    };
    
    let admin = user;
    admin.name = "Pete";
    alert (user.name);//Pete
    ```
    
### 通过引用来比较

- 仅当两个对象为同一对象时，两者才相等
- 两者引用同一对象时，它们相等
- 两个对象独立时，它们不相等

    ```javascript
    let a = {};
    let b = a;
    
    alert (a == b);//true
    alert (a === b);//true
    ```
    
    ```javascript
    let a = {};
    let b = {};
    
    alert (a == b);//false
    ```

### 克隆与合并，Object.assign

- 通过创建一个新的对象，遍历现有属性结构，在原始类型值的层面，将其复制到新对象

    ```javascript
    let user = {
        name: "John",
        age: 30,
    };

    let clone = {};

    for (let key in user) {
        clone[key] = user[key];
    }
    
    clone.name = "Pete";
    
    alert (user.name);//原来对象中的`name`属性依然是`John`
    ```
    
- 使用`Object.assign`方式

    ```javascript
    let user = { name: "John", };
    
    let permissions1 = { canView: true, };
    let permissions2 = { canEdit: true, };
    
    Object.assign(user, permissions1, permissions2);
    ```

- 被拷贝的属性的属性名已经存在，那么它会被覆盖

    ```javascript
    let user = { name: "John", };

    Object.assign(user, {name: "Pete",})
    
    alert (user.name);//Pete
    ```

### 深层克隆


## 垃圾回收


### 可达性



## 对象方法,`this`

- 创建对象来表示真实世界中的实体

## 构造器和操作符`new`


### 构造函数































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
