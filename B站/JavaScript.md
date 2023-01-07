---

---

# JavaScript基础知识

# 1	初始JavaScript

## 1.1  javaScript是什么

- JavaScript 是世界上最流行的语言之一，是一种运行在客户端的脚本语言 （Script 是脚本的意思）
- 脚本语言：不需要编译，运行过程中由 js 解释器( js 引擎）逐行来进行解释并执行
- 现在也可以基于 Node.js 技术进行服务器端编程

![image-20221222222419272](D:\create\note\B站\images\image-20221222222419272.png)



## 1.2  javaScript的作用

-  表单动态校验（密码强度检测）  （ JS 产生最初的目的 ）
-  网页特效
-  服务端开发(Node.js)
-  桌面程序(Electron)
-  App(Cordova) 
-  控制硬件-物联网(Ruff)
-  游戏开发(cocos2d-js)



##  1.3  浏览器执行 JS 简介

浏览器分成两部分：渲染引擎和 JS 引擎

-  渲染引擎：用来解析HTML与CSS，俗称内核，比如 chrome 浏览器的 blink ，老版本的 webkit
-  JS 引擎：也称为 JS 解释器。 用来读取网页中的JavaScript代码，对其处理后运行，比如 chrome  浏览器的 V8

浏览器本身并不会执行JS代码，而是通过内置 JavaScript 引擎(解释器) 来执行 JS 代码 。JS 引擎执行代码时逐行解释每一句源码（转换为机器语言），然后由计算机去执行，所以 JavaScript 语言归为脚本语言，会逐行解释执行。

![image-20221222222625850](D:\create\note\B站\images\image-20221222222625850.png)



## 1.4  javaScript的组成

### 1 ECMAScript

ECMAScript：ECMAScript 规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。

### 2 DOM ——文档对象模型

文档对象模型（Document Object Model，简称DOM），是W3C组织推荐的处理可扩展标记语言的标准编程接口。通过 DOM 提供的接口可以对页面上的各种元素进行操作（大小、位置、颜色等）。

### 3 BOM ——浏览器对象模型

BOM (Browser Object Model，简称BOM) 是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过BOM可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等。



## 1.5  JS 初体验

JS 有3种书写位置，分别为行内、内嵌和外部。 

### 1 行内式 JS

```
<input type="button" value="点我试试" onclick="alert('Hello World')" />
```

- 可以将单行或少量 JS 代码写在HTML标签的事件属性中（以 on 开头的属性），如：onclick
- 注意单双引号的使用：在HTML中我们推荐使用双引号, JS 中我们推荐使用单引号
- 可读性差， 在html中编写JS大量代码时，不方便阅读；
- 引号易错，引号多层嵌套匹配时，非常容易弄混；
- 特殊情况下使用

### 2 内嵌 JS

```
 <script>
    alert('Hello  World~!');
 </script>
```

- 可以将多行JS代码写到 <script> 标签中
- 内嵌 JS 是学习时常用的方式

### 3 外部 JS文件

```
<script src="my.js"></script>
```

- 利于HTML页面代码结构化，把大段 JS代码独立到 HTML 页面之外，既美观，也方便文件级别的复用
- 引用外部 JS文件的 script 标签中间不可以写代码
- 适合于JS 代码量比较大的情况



## 1.6 JavaScript 注释

### 1 单行注释

//  用来注释单行文字（  快捷键   ctrl  +  /   ）

### 2 多行注释

/* */  用来注释多行文字（ 默认快捷键  alt +  shift  + a ） 
快捷键修改为：   ctrl + shift  +  /  
vscode- 首选项按- 键盘快捷方式 -查找 原来的快捷键-修改为新的快捷键 -回车确认



## 1.7  JavaScript 输入输出语句

| **方法**         | **说明**                       | **归属** |
| ---------------- | ------------------------------ | -------- |
| alert(msg)       | 浏览器弹出警示框               | 浏览器   |
| console.log(msg) | 浏览器控制台打印输出信息       | 浏览器   |
| prompt(info)     | 浏览器弹出输入框，用户可以输入 | 浏览器   |

注意：alert() 主要用来显示消息给用户，console.log() 用来给程序员自己看运行时的消息。

```
<script>
        // 这是一个输入框
        prompt('请输入您的年龄');
        // alert 弹出警示框 输出的 展示给用户的
        alert('计算的结果是');
        // console 控制台输出 给程序员测试用的  
        console.log('我是程序员能看到的');
</script>
```



## 1.8   解释型语言和编译型语言

### 1 概述

计算机不能直接理解任何除机器语言以外的语言，所以必须要把程序员所写的程序语言翻译成机器语言才能执行程序。程序语言翻译成机器语言的工具，被称为翻译器

![image-20221224153930345](D:\create\note\B站\images\image-20221224153930345.png)

-  翻译器翻译的方式有两种：一个是编译，另外一个是解释。两种方式之间的区别在于翻译的时间点不同
-  编译器是在代码执行之前进行编译，生成中间代码文件
-  解释器是在运行时进行及时解释，并立即执行(当编译器以解释方式运行的时候，也称之为解释器)

### 2 执行过程

![image-20221224154014588](D:\create\note\B站\images\image-20221224154014588.png)

类似于请客吃饭：

- 编译语言：首先把所有菜做好，才能上桌吃饭
- 解释语言：好比吃火锅，边吃边涮，同时进行







# 2	变量

## 2.1  变量概述

### 1 什么是变量

白话：变量就是一个装东西的盒子。
通俗：变量是用于存放数据的容器。 我们通过 变量名 获取数据，甚至数据可以修改

![image-20221223133040365](D:\create\note\B站\images\image-20221223133040365.png)

### 2 变量在内存中的存储

本质：变量是程序在内存中申请的一块用来存放数据的空间。
类似我们酒店的房间，一个房间就可以看做是一个变量。

![image-20221223133125665](D:\create\note\B站\images\image-20221223133125665.png)



## 2.2  变量的使用

变量在使用时分为两步： 1. 声明变量   2. 赋值 

### 1 声明变量

```
//  声明变量  
var age; //  声明一个 名称为age 的变量     
```

- var 是一个 JS关键字，用来声明变量( variable 变量的意思 )。使用该关键字声明变量后，计算机会自动为变量分配内存空间，不需要程序员管
- age 是程序员定义的变量名，我们要通过变量名来访问内存中分配的空间

### 2 赋值

```
age = 10; // 给 age  这个变量赋值为 10
```

- = 用来把右边的值赋给左边的变量空间中   此处代表赋值的意思
- 变量值是程序员保存到变量空间里的值

### 3 变量的初始化

```
var age  = 18;  // 声明变量同时赋值为 18          
```

声明一个变量并赋值， 我们称之为变量的初始化。



## 2.3  变量语法扩展

### 1 更新变量

一个变量被重新复赋值后，它原有的值就会被覆盖，变量值将以最后一次赋的值为准。

```
var age = 18;

age = 81;   // 最后的结果就是81因为18 被覆盖掉了 
```

### 2 同时声明多个变量

```
var age = 10,  name = 'zs', sex = 2; 
```

### 3 声明变量特殊情况

| **情况**                      | **说明**               | **结果**  |
| ----------------------------- | ---------------------- | --------- |
| var age ; console.log (age);  | 只声明 不赋值          | undefined |
| console.log(age)              | 不声明 不赋值 直接使用 | 报错      |
| age  = 10; console.log (age); | 不声明 只赋值          | 10        |



## 2.4  变量命名规范

- 由字母(A-Za-z)、数字(0-9)、下划线(_)、美元符号( $ )组成，如：usrAge, num01, _name
- 严格区分大小写。var app; 和 var App; 是两个变量
- 不能 以数字开头。  18age   是错误的
- 不能 是关键字、保留字。例如：var、for、while
- 变量名必须有意义。 MMD   BBD        nl   →     age  
- 遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。 myFirstName
- 推荐翻译网站： 有道    爱词霸







# 3	数据类型

## 3.1  数据类型简介

### 1 为什么需要数据类型

- 在计算机中，不同的数据所需占用的存储空间是不同的，为了便于把数据分成所需内存大小不同的数据，充分利用存储空间，于是定义了不同的数据类型。
- 简单来说，数据类型就是数据的类别型号。比如姓名“张三”，年龄18，这些数据的类型是不一样的

### 2 变量的数据类型

变量是用来存储值的所在处，它们有名字和数据类型。变量的数据类型决定了如何将代表这些值的位存储到计算机的内存中。JavaScript 是一种弱类型或者说动态语言。这意味着不用提前声明变量的类型，在程序运行过程中，类型会被自动确定。

### 3 数据类型的分类

JS 把数据类型分为两类：

-  简单数据类型 （Number,String,Boolean,Undefined,Null）
-  复杂数据类型 （object)



-  简单数据类型 （Number,String,Boolean,Undefined,Null）
-  复杂数据类型 （object)

## 3.2  简单数据类型

### 基本数据类型

| 简单数据类型 | 说明                                               | 默认值    |
| ------------ | -------------------------------------------------- | --------- |
| Number       | 数字型，包含整型值和浮点型值，如21、0.21           | 0         |
| Boolean      | 布尔值类型，如true, false,等价于1和0               | false     |
| String       | 字符串类型，如”张三”注意咱们js里面，字符串都带引号 | ""        |
| Undefined    | var a;声明了变量a但是没有给值，此时a = undefined   | undefined |
| Null         | var a = null;声明了变量a为空值                     | null      |



#### 数字型Number

```
var age = 21;       // 整数
var Age = 21.3747;  // 小数 

数字型进制
  // 1.八进制数字序列范围：0~7
 var num1 = 07;   // 对应十进制的7
 var num2 = 019;  // 对应十进制的19
 var num3 = 08;   // 对应十进制的8
  // 2.十六进制数字序列范围：0~9以及A~F
 var num = 0xA;   

数字型范围
alert(Number.MAX_VALUE); // 1.7976931348623157e+308
alert(Number.MIN_VALUE); // 5e-324

数字型三个特殊值
alert(Infinity);  // Infinity，代表无穷大，大于任何数值
alert(-Infinity); // -Infinity，代表无穷小，小于任何数值
alert(NaN);       // NaN，代表一个非数值

isNaN()
用来判断一个变量是否为非数字的类型，返回 true 或者 false
var usrAge = 21;
var isOk = isNaN(userAge);
console.log(isNum);            // false ，21 不是一个非数字
var usrName = "andy";
console.log(isNaN(userName));  // true ，"andy"是一个非数字
```



#### 字符串型String

```
字符串型可以是引号中的任意文本，其语法为 双引号 "" 和 单引号''
因为 HTML 标签里面的属性使用的是双引号，JS 这里我们更推荐使用单引号。

字符串引号嵌套
JS 可以用单引号嵌套双引号 ，或者用双引号嵌套单引号 (外双内单，外单内双)
var strMsg = '我是"高帅富"程序猿';   // 可以用''包含""
var strMsg2 = "我是'高帅富'程序猿";  // 也可以用"" 包含''

字符串转义符
| **转义符**  | **解释说明**             	
| \n         | 换行符，n 是 newline 的意思  
| \ \        | 斜杠 \                     
| \'         |  单引号                     
| \"         | ”双引号                     
| \t         | tab 缩进                    
| \b         | 空格 ，b 是 blank 的意思    



字符串长度
var strMsg = "我是帅气多金的程序猿！";
alert(strMsg.length); // 显示 11

字符串拼接
//1.1 字符串 "相加"
alert('hello' + ' ' + 'world'); // hello world
//1.2 数值字符串 "相加"
alert('100' + '100'); // 100100
//1.3 数值字符串 + 数值
alert('11' + 12);     // 1112 

字符串拼接加强
console.log('pink老师' + 18);           // 只要有字符就会相连 
var age = 18;
// console.log('pink老师age岁啦');       // 这样不行哦
console.log('pink老师' + age);          // pink老师18
console.log('pink老师' + age + '岁啦');  // pink老师18岁啦
```



#### 布尔型 Boolean

```
布尔类型有两个值：true 和 false ，其中 true 表示真（对），而 false 表示假（错）。
布尔型和数字型相加的时候， true 的值为 1 ，false 的值为 0。

console.log(true + 1);  // 2
console.log(false + 1); // 1
```



#### Undefined 和 Null

```
一个声明后没有被赋值的变量会有一个默认值 undefined ( 如果进行相连或者相加时，注意结果）
var variable;
console.log(variable);           // undefined
console.log('你好' + variable);  // 你好undefined
console.log(11 + variable);     // NaN
console.log(true + variable);   //  NaN

一个声明变量给 null 值，里面存的值为空（学习对象时，我们继续研究null)
var vari = null;
console.log('你好' + vari);  // 你好null
console.log(11 + vari);     // 11
console.log(true + vari);   //  1
```



## 3.3  获取变量数据类型

### 1 获取检测变量的数据类型(typeof)

```
var num = 18;
console.log(typeof num) // 结果 number 

不同类型的返回值
类型			例				结果
String		typeof ”小白”		 	"string"
Number		typeof 18		   	 "number"
Boolean		typeof true	      	 "boolean"
Undefined	typeof undefined	 "undefined"
Null		typeof null			 "object"

```

### 2 字面量

字面量是在源代码中一个固定值的表示法，通俗来说，就是字面量表示如何表达这个值。

- 数字字面量：8, 9, 10
- 字符串字面量：'黑马程序员', "大前端"
- 布尔字面量：true，false



- 数字字面量：8, 9, 10
- 字符串字面量：'黑马程序员', "大前端"
- 布尔字面量：true，false

## 3.4  数据类型转换

### 1 什么是数据类型转换

使用表单、prompt 获取过来的数据默认是字符串类型的，此时就不能直接简单的进行加法运算，而需要转换变量的数据类型。通俗来说，就是把一种数据类型的变量转换成另外一种数据类型。
我们通常会实现3种方式的转换

- 转换为字符串类型
- 转换为数字型
- 转换为布尔型

### 2 转换为字符串

| 方式             | 说明                         | 案 例                              |
| ---------------- | ---------------------------- | ---------------------------------- |
| toString()       | 转成字符串                   | var num=1;alert(num.toString());   |
| String()强制转换 | 转成字符串                   | var num=1;alert(String(num));      |
| 加号拼接字符串   | 和字符串拼接的结果都是字符串 | var num=1;alert(num+"我是字符串"); |

注意：

- toString() 和 String()  使用方式不一样。
- 三种转换方式，我们更喜欢用第三种加号拼接字符串转换方式， 这一种方式也称之为隐式转换

### 3 转换为数字型(重点)

| 方式                   | 说明                         | 案例                |
| ---------------------- | ---------------------------- | ------------------- |
| parselnt(string)函数   | 将string类型转成整数数值型   | parselnt('78')      |
| parseFloat(string)函数 | 将string类型转成浮点数数值型 | parseFloat('78.21') |
| Number()强制转换函数   | 将string类型转换为数值型     | Number('12')        |
| js隐式转换(-*/)        | 利用算术运算隐式转换为数值型 | '12'-0              |

注意：

- 注意 parseInt 和 parseFloat 单词的大小写，这2个是重点
- 隐式转换是我们在进行算数运算的时候，JS 自动转换了数据类型

### 4 转换为布尔型

| 方式          | 说明               | 案例             |
| ------------- | ------------------ | ---------------- |
| Boolean()函数 | 其他类型转成布尔值 | Boolean('true'); |

- 代表空、否定的值会被转换为 false  ，如 ''、0、NaN、null、undefined  
- 其余值都会被转换为 true

```
console.log(Boolean('')); // false
console.log(Boolean(0)); // false
console.log(Boolean(NaN)); // false
console.log(Boolean(null)); // false
console.log(Boolean(undefined)); // false
console.log(Boolean('小白')); // true
console.log(Boolean(12)); // true
```



## 3.5 扩展

- **标识符**就是指开发人员为变量、属性、函数、参数取的名字。
  标识符不能是关键字或保留字。

- **关键字**：是指 JS本身已经使用了的字，不能再用它们充当变量名、方法名。

  包括：break、case、catch、continue、default、delete、do、else、finally、for、function、if、in、instanceof、new、return、switch、this、throw、try、typeof、var、void、while、with 等。

- **保留字**：实际上就是预留的“关键字”，意思是现在虽然还不是关键字，但是未来可能会成为关键字，同样不能使用它们当变量名或方法名。

  包括：boolean、byte、char、class、const、debugger、double、enum、export、extends、fimal、float、goto、implements、import、int、interface、long、mative、package、private、protected、public、short、static、super、synchronized、throws、transient、volatile 等。







# 4	运算符

## 4.1  运算符

运算符（operator）也被称为操作符，是用于实现赋值、比较和执行算数运算等功能的符号。



JavaScript中常用的运算符有：

-  算数运算符
-  递增和递减运算符
-  比较运算符
-  逻辑运算符
-  赋值运算符



-  算数运算符
-  递增和递减运算符
-  比较运算符
-  逻辑运算符
-  赋值运算符



## 4.2  算数运算符

### 1 算术运算符概述

概念：算术运算使用的符号，用于执行两个变量或值的算术运算。

### 2 浮点数的精度问题

浮点数值的最高精度是 17 位小数，但在进行算术计算时其精确度远远不如整数。

var result = 0.1 + 0.2;    // 结果不是 0.3，而是：0.30000000000000004
console.log(0.07 * 100);   // 结果不是 7，  而是：7.000000000000001

### 3 表达式和返回值

表达式：是由数字、运算符、变量等以能求得数值的有意义排列方法所得的组合(简单理解：是由数字、运算符、变量等组成的式子)

表达式最终都会有一个结果，返回给我们，我们称为**返回值**



## 4.3  递增和递减运算符

### 1 前置递增运算符

++num 前置递增，就是自加1，类似于 num =  num + 1，但是 ++num 写起来更简单。
使用口诀：先自加，后返回值

var  num = 10;
alert(++num + 10);   // 21

### 2 后置递增运算符

num++ 后置递增，就是自加1，类似于 num =  num + 1 ，但是 num++ 写起来更简单。
使用口诀：先返回原值，后自加 

var  num = 10;
alert(10 + num++);  // 20



## 4.4  比较运算符

概念：比较运算符（关系运算符）是两个数据进行比较时所使用的运算符，比较运算后，会返回一个布尔值（true / false）作为比较运算的结果。

## 4.5  逻辑运算符

概念：逻辑运算符是用来进行布尔值运算的运算符，其返回值也是布尔值。后面开发中经常用于多个条件的判断



## 4.6  赋值运算符

概念：用来把数据赋值给变量的运算符。



## 4.7  运算符优先级







# 5	JavaScript流程控制

## 5.1  流程控制-分支

在一个程序执行的过程中，各条代码的执行顺序对程序的结果是有直接影响的。很多时候我们要通过控制代码的执行顺序来实现我们要完成的功能。(简单理解： 流程控制就是来控制我们的代码按照什么结构顺序来执行)
流程控制主要有三种结构，分别是顺序结构、分支结构和循环结构，这三种结构代表三种代码执行的顺序

![image-20221231161117594](D:\create\note\B站\images\image-20221231161117594.png)



### 1 三元表达式

1. 语法结构

​		表达式1 ? 表达式2 : 表达式3;

2. 执行思路 

   - 如果表达式1为 true ，则返回表达式2的值，如果表达式1为 false，则返回表达式3的值

   - 简单理解： 就类似于  if  else （双分支） 的简写

   - 如果表达式1为 true ，则返回表达式2的值，如果表达式1为 false，则返回表达式3的值

   - 简单理解： 就类似于  if  else （双分支） 的简写


### 2 分支流程控制 switch 语句

```
switch( 表达式 ){ 
    case value1:
        // 表达式 等于 value1 时要执行的代码
        break;
    case value2:
        // 表达式 等于 value2 时要执行的代码
        break;
    default:
        // 表达式 不等于任何一个 value 时要执行的代码
}
```



## 5.2  流程控制-循环

在程序中，一组被重复执行的语句被称之为**循环体**，能否继续重复执行，取决于循环的终止条件。由循环体及循环的终止条件组成的语句，被称之为**循环语句**

在Js 中，主要有三种类型的循环语句：

-  for 循环
-  while 循环
-  do...while 循环





# 6	函数

## arguments的使用

当我们不确定有多少个参数传递的时候，可以用 arguments 来获取。在 JavaScript 中，arguments 实际上它是当前函数的一个内置对象。所有函数都内置了一个 arguments 对象，arguments 对象中存储了传递的所有实参。

arguments展示形式是一个伪数组，因此可以进行遍历。伪数组具有以下特点：

- 具有 length 属性
- 按索引方式储存数据
- 不具有数组的 push , pop 等方法

```
function fn(){
	console.log(arguments);
}
fn(1,2,3);
```







# 7	作用域

## 7.1  作用域概述

通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而限定这个名字的可用性的代码范围就是这个名字的作用域。作用域的使用提高了程序逻辑的局部性，增强了程序的可靠性，减少了名字冲突。

JavaScript（es6前）中的作用域有两种：

- 全局作用域
- 局部作用域（函数作用域）



## 7.2  作用域

**全局作用域**：作用于所有代码执行的环境(整个 script 标签内部)或者一个独立的 js 文件。

**局部作用域 （函数作用域）**：作用于函数内的代码环境，就是局部作用域。 因为跟函数有关系，所以也称为函数作用域

**注意**： JS 没有块级作用域



## 7.3  作用域链

-  只要是代码，就至少有一个作用域
- 写在函数内部的局部作用域
-  如果函数中还有函数，那么在这个作用域中就又可以诞生一个作用域
-  根据在内部函数可以访问外部函数变量的这种机制，用链式查找决定哪些数据能被内部函数访问，就称作作用域链



## 7.4  案例

**案例一**

```
function f1() {
    var num = 123;
    function f2() {
        console.log( num );
    }
    f2();
}
var num = 456;
f1();
```

**案例二**

```
var a = 1;
function fn1() {
    var a = 2;
    var b = '22';
    fn2();
    function fn2() {
        var a = 3;
        fn3();
        function fn3() {
            var a = 4;
            console.log(a); //a的值 ?
            console.log(b); //b的值 ?
        }
    }
}
fn1();
```







# 8	预解析

## 8.1  预解析

JavaScript 代码是由浏览器中的 JavaScript 解析器来执行的。JavaScript 解析器在运行 JavaScript 代码的时候分为两步：预解析和代码执行。

- 预解析：在当前作用域下, JS 代码执行之前，浏览器会默认把带有 var 和 function 声明的变量在内存中进行提前声明或者定义。
- 代码执行： 从上到下执行JS语句。

预解析只会发生在通过 var 定义的变量和 function 上。学习预解析能够让我们知道为什么在变量声明之前访问变量的值是 undefined，为什么在函数声明之前就可以调用函数。



## 8.2  案例

**案例一**

```
var num = 10;
fun();
function fun() {
  console.log(num);
  var num = 20;
}
//相当执行了以下操作
var num;
function fun() {
  var num;
  console.log(num);
  num = 20;
}
num = 10;
fun();
```

**案例二**

```
var num = 10;
function fn(){
    console.log(num);
    var num = 20;
    console.log(num);
} 
fn();
//相当执行了以下操作
var num;
function fn(){
	var num;
    console.log(num);
    num = 20;
    console.log(num);
} 
num = 10;
fun();
```

**案例三**

```
var a = 18;
f1();
function f1() {
  var b = 9;
  console.log(a);
  console.log(b);
  var a = '123';
}
//相当执行了以下操作
var a;
function f1() 
  var b;
  var a;
  b = 9;
  console.log(a);
  console.log(b);
  a = '123';
}
a = 18;
f1();
```

**案例四**

```
f1();
console.log(c);
console.log(b);
console.log(a);
function f1() {
  var a = b = c = 9;
  //b,c直接赋值，没有var，当全局变量看
  //集体声明 var a = 9,b = 9,c = 9;
  console.log(a);
  console.log(b);
  console.log(c);
}
//相当执行了以下操作
function f1() {
  var a;
  a = b = c = 9;
  console.log(a);
  console.log(b);
  console.log(c);
}
f1();
console.log(c);
console.log(b);
console.log(a);
```









# 9	对象

## 9.1  创建对象的三个方式

在 JavaScript 中，现阶段我们可以采用三种方式创建对象（object）：

- 利用字面量创建对象 
- 利用 new Object 创建对象 
- 利用构造函数创建对象 



**利用字面量创建对象**

```
var star = {
    name : 'pink',
    age : 18,
    sex : '男',
    sayHi : function(){
        alert('大家好啊~');
    }
};
```

**利用new Object创建对象**

```
var andy = new Obect();
andy.name = 'pink';
andy.age = 18;
andy.sex = '男';
andy.sayHi = function(){
    alert('大家好啊~');
}
```

**利用构造函数创建对象**

```
function Person(name, age, sex) {
     this.name = name;
     this.age = age;
     this.sex = sex;
     this.sayHi = function() {
      alert('我的名字叫：' + this.name + '，年龄：' + this.age + '，性别：' + this.sex);
    }
}
var bigbai = new Person('大白', 100, '男');
var smallbai = new Person('小白', 21, '男');
console.log(bigbai.name);
console.log(smallbai.name);
```



## 9.2  遍历对象属性

```
for (var k in obj) {
    console.log(k);      // 这里的 k 是属性名
    console.log(obj[k]); // 这里的 obj[k] 是属性值
}
```







# 10	内置对象

## 10.1  内置对象

-  JavaScript 中的对象分为3种：自定义对象 、内置对象、 浏览器对象
- 前面两种对象是JS 基础 内容，属于 ECMAScript；  第三个浏览器对象属于我们JS 独有的，我们JS API 讲解
-  内置对象就是指 JS 语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是最基本而必要的功能（属性和方法）
- 内置对象最大的优点就是帮助我们快速开发
-  JavaScript 提供了多个内置对象：Math、 Date 、Array、String等



## 10.2  查文档

MDN:   https://developer.mozilla.org/zh-CN/



**如何学习对象中的方法**

1. 查阅该方法的功能
2. 查看里面参数的意义和类型
3. 查看返回值的意义和类型
4. 通过 demo 进行测试



## 10.3  Math对象

### 1 封装自己的数学对象

```
var myMath = {
            PI:3.141592653,
            max:function(){
                var max = arguments[0];
                for(var i =1;i<arguments.length;i++){
                    if(arguments[i] > max){
                        max = arguments[i];
                    }
                }
                return max;
            }
        }
console.log(myMath.PI);
console.log(myMath.max(1,5,9));
```

### 2 Math的数学方法

Math 对象不是构造函数，它具有数学常数和函数的属性和方法。跟数学相关的运算（求绝对值，取整、最大值等）可以使用 Math 中的成员。

```
Math.PI		 			 // 圆周率
Math.floor() 	 		 // 向下取整
Math.ceil()        		 // 向上取整
Math.round()       		 // 四舍五入版 就近取整   注意 -3.5   结果是  -3 
Math.abs()		 		 // 绝对值
Math.max()/Math.min()	 // 求最大和最小值 
```

### 3 随机数方法(Math.random())

**`Math.random`**（） 函数返回一个浮点数，伪随机数在范围从0 到小于1，也就是说，从 0（包括 0）往上，但是不包括 1（排除 **1**），然后您可以缩放**到**所需的范围。实现将初始种子选择到随机数生成算法;它不能被用户选择或重置。

```
console.log(Math.random());

//得到一个两数之间的随机整数，包括两个数在内
//Math.floor(Math.random() * (max - min + 1)) + min;
function getRandom(min,max){
return Math.floor(Math.random() * (max - min + 1)) + min;
}
console.log(getRandom(1,10));

//随机点名
var arr =['李妍','周狗','周志狗'];
console.log(arr[getRandom(0,arr.length-1)]);
```



## 10.4  日期对象

### 1 创建一个Date日期对象

```
var date = new Date();
console.log(date); 
```

### 2 创建一个日期对象的几种方法

```
var today = new Date();
var birthday = new Date('December 17, 1995 03:24:00');
var birthday = new Date('1995-12-17T03:24:00');
var birthday = new Date(1995, 11, 17);
var birthday = new Date(1995, 11, 17, 3, 24, 0);
```

### 3 日期格式化

| 方法名        | 说明                     | 代码               |
| ------------- | ------------------------ | ------------------ |
| getFullYear() | 获取当年                 | dObj.getFullYear() |
| getMonth(     | 获取当月(0-11)           | dObj.getMonth()    |
| getDate()     | 获取当天日期             | dObj.getDate()     |
| getDay()      | 获取星期几(周日0到周六6) | dObj.getDay()      |
| getHours()    | 获取当前小时             | dObj.getHours()    |
| getMinutes(   | 获取当前分钟             | dObj.getMinutes()  |
| getSeconds()  | 获取当前秒钟             | dObj.getSeconds()  |

### 4 获取日期的总的毫秒形式

```
//我们距离1970.1.1总的毫秒数
var date = new Date();
console.log(date.valueOf());
console.log(date.getTime());

//返回的就是总的毫秒数(简单写法)
var date1 = +new Date();
console.log(date1);

//H5新增的方法
console.log(Date.now());
```



## 10.5  数组对象

### 1 创建数组对象的两种方式				

-  字面量方式
-  new Array()

```
//1.利用数组字面量
var arr = [1,2,3];
console.log(arr[0]);

//2.利用new Array()
//(1)创建了一个空的数组
var arr1 = new Array();

//(2)这个表示创建了一个长度为2的数组
var arr2 = new Array(2);
console.log(arr2);

//(3)创建一个数组，里面有2，3这两个元素
var arr3 = new Array(2,3);
console.log(arr3);
```

### 2 检测是否为数组

检测是否为数组

-  instanceof 运算符，可以判断一个对象是否属于某种类型
-  Array.isArray()用于判断一个对象是否为数组，isArray() 是 HTML5 中提供的方法

```
//1.instanceof运算符
var arr = [];
var obj = {};
console.log(arr instanceof Array);
console.log(obj instanceof Array);

//2.Array.isArray(参数),h5新增的方法
console.log(Array.isArray(arr));
console.log(Array.isArray(obj));
```

### 3 添加删除数组元素方法

| 方法名        | 说明                     | 代码               |
| ------------- | ------------------------ | ------------------ |
| getFullYear() | 获取当年                 | dObj.getFullYear() |
| getMonth(     | 获取当月(0-11)           | dObj.getMonth()    |
| getDate()     | 获取当天日期             | dObj.getDate()     |
| getDay()      | 获取星期几(周日0到周六6) | dObj.getDay()      |
| getHours()    | 获取当前小时             | dObj.getHours()    |
| getMinutes(   | 获取当前分钟             | dObj.getMinutes()  |
| getSeconds()  | 获取当前秒钟             | dObj.getSeconds()  |

```
var arr = [1,2,3];
//1.push()在数组末尾添加元素
var length = arr.push(4,'pink');//返回的结果是新数组的长度5
//2.unshift()在数组开头添加元素
var length1 = arr.unshift('red','purple');//返回的也是新数组的长度

//3.pop()它可以删除数组的最后一个元素
console.log(arr.pop());//返回结果是最后一个元素
//4.shift()它可以删除数组的第一个元素
console.log(arr.shift());//返回结果是第一个元素

console.log(arr);
```

### 4 数组翻转和排序

| 方法名    | 说明                         | 是否修改原数组                   |
| --------- | ---------------------------- | -------------------------------- |
| reverse() | 颠倒数组中元素的顺序，无参数 | 该方法会改变原来的数组返回新数组 |
| sort()    | 对数组的元素进行排序         | 该方法会改变原来的数组返回新数组 |

```
//1.翻转数组
var arr = ['pink','red','blue'];
arr.reverse();
console.log(arr);

//2.数组排序
var arr1 = [13,4,77,1,7];
arr1.sort(function(a,b){
return a-b;//升序的顺序排序
});
console.log(arr1);
```

### 5 数组索引方法

| 方法名        | 说明                           | 返回值                                   |
| ------------- | ------------------------------ | ---------------------------------------- |
| indexOf()     | 数组中查找给定元素的第一个索引 | 如果存在返回索引号如果不存在，则返回-1。 |
| lastIndexOf() | 在数组中的最后一个的索引       | 如果存在返回索引号如果不存在，则返回-1。 |

```
//indexOf,作用就是返回该数组元素第一个出现的索引号;如果没有,返回-1。
//lastIndexOf,作用就是返回该数组元素最后一个出现的索引号;如果没有,返回-1。
var arr = ['red','green','blue','pink','blue'];
console.log(arr.indexOf('blue'));
console.log(arr.lastIndexOf('blue'));
```

### 6 数组转换为字符串

| 方法名         | 说明                                         | 返回值         |
| -------------- | -------------------------------------------- | -------------- |
| toString()     | 把数组转换成字符串，逗号分隔每一项           | 返回一个字符串 |
| join('分隔符') | 方法用于把数组中的所有元素转换为一个字符串。 | 返回一个字符串 |

```
//1.toString()将我们的数组转换为字符串
var arr = [1,2,3];
console.log(arr.toString());

//2.join(分隔符)
var arr1 = ['green','blue','pink'];
console.log(arr1.join());
console.log(arr1.join('-'));
console.log(arr1.join('&'));
```



## 10.6  字符串对象

### 1 基本包装类型

为了方便操作基本数据类型，JavaScript 还提供了三个特殊的引用类型：String、Number和 Boolean。

```
// 1. 生成临时变量，把简单类型包装为复杂数据类型
var temp = new String('andy');
// 2. 赋值给我们声明的字符变量
str = temp;
// 3. 销毁临时变量
temp = null;
```

### 2 字符串不可变

```
//字符串的不可变性，不要大量的拼接字符串
var str = 'andy';
console.log(str);
str = 'red';
console.log(str);
```

### 3  根据字符返回位置

| 方法名                             | 说明                                                         |
| ---------------------------------- | ------------------------------------------------------------ |
| indexOf('要查找的字符',开始的位置) | 返回指定内容在元字符串中的位置，如果找不到就返回-1,开始的位置是 index索引号 |
| lastlndexOf()                      | 从后往前找，只找第一个匹配的                                 |

```
var str = '改革春风锤满地，春天来了';
console.log(str.indexOf('春'));		//2
console.log(str.lastIndexOf('春'));	//8
```

### 4 根据位置返回字符

| 方法名            | 说明                                     | 使用                         |
| ----------------- | ---------------------------------------- | ---------------------------- |
| charAt(index)     | 返回指定位置的字符(index字符串的索引号)  | str.charAt(0)                |
| charCodeAt(index) | 获取指定位置处字符的ASCII码(index索引号) | str.charCodeAt(0)            |
| str[index]        | 获取指定位置处字符                       | HTML5,IE8+支持和charAt()等效 |

```
//1.chatAt(index)根据位置返回字符
var str = 'andy';
console.log(str.charAt(3));

//2.遍历所有的字符
for(var i = 0;i<str.length;i++){
console.log(str.charAt(i));
}

//3.charCodeAt(index)指定位置处的ASCLL码,目的：判断用户按下了那个键
console.log(str.charCodeAt(0));

//4.str[index],h5新增的
console.log(str[0]);
```

### 5 字符串操作方法

| 方法名                  | 说 明                                                        |
| ----------------------- | ------------------------------------------------------------ |
| concat(str1,str2,str3…) | concat()方法用于连接两个或多个字符串。拼接字符串，等效于+,+更常用 |
| substr(start,length)    | 从start位置开始(索引号),length取的个数重点记住这个           |
| slice(start, end)       | 从start位置开始，截取到end位置，end取不到(他们俩都是索引号)  |
| substring(start, end)   | 从start位置开始，截取到end位置，end取不到。基本和slice相同，但是不接受负值 |





# 11	简单类型与复杂类型

## 11.1  简单类型与复杂类型

简单类型又叫做基本数据类型或者值类型，复杂类型又叫做引用类型。

-  值类型：简单数据类型/基本数据类型，在存储时变量中存储的是值本身，因此叫做值类型string ，number，boolean，undefined，null
-  引用类型：复杂数据类型，在存储时变量中存储的仅仅是地址（引用），因此叫做引用数据类型。通过 new 关键字创建的对象（系统对象、自定义对象），如 Object、Array、Date等



## 11.2  堆和栈

堆栈空间分配区别：
　　1、栈（操作系统）：由操作系统自动分配释放存放函数的参数值、局部变量的值等。其操作方式类似于数据结构中的栈；
简单数据类型存放到栈里面
　　2、堆（操作系统）：存储复杂类型(对象)，一般由程序员分配释放，若程序员不释放，由垃圾回收机制回收。
复杂数据类型存放到堆里面

![image-20230106133132007](D:\create\note\B站\images\image-20230106133132007.png)

注意：简单数据类型 null 返回的是一个空的对象(object)



## 11.3  简单类型的内存分配

-  值类型（简单数据类型）： string ，number，boolean，undefined，null
-  值类型变量的数据直接存放在变量（栈空间）中

![image-20230106133500024](D:\create\note\B站\images\image-20230106133500024.png)



## 11.4  复杂类型的内存分配

-  引用类型（复杂数据类型）：通过 new 关键字创建的对象（系统对象、自定义对象），如 Object、Array、Date等
-  引用类型变量（栈空间）里存放的是地址，真正的对象实例存放在堆空间中

![image-20230106133545417](D:\create\note\B站\images\image-20230106133545417.png)



## 11.5  简单类型传参

函数的形参也可以看做是一个变量，当我们把一个值类型变量作为参数传给函数的形参时，其实是把变量在栈空间里的值复制了一份给形参，那么在方法内部对形参做任何修改，都不会影响到的外部变量。

```
function fn(a) {
    a++;
    console.log(a); 
}
var x = 10;
fn(x);
console.log(x)；
```



## 11.6  复杂类型传参

函数的形参也可以看做是一个变量，当我们把引用类型变量传给形参时，其实是把变量在栈空间里保存的堆地址复制给了形参，形参和实参其实保存的是同一个堆地址，所以操作的是同一个对象。

```
function Person(name) {
    this.name = name;
}
function f1(x) { // x = p
    console.log(x.name); // 2. 这个输出什么 ?     刘德华 
    x.name = "张学友";
    console.log(x.name); // 3. 这个输出什么 ?     张学友
}
var p = new Person("刘德华");
console.log(p.name);    // 1. 这个输出什么 ?   	刘德华
f1(p);
console.log(p.name);    // 4. 这个输出什么 ?	  	张学友
```

