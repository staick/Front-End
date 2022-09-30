# JavaScript

JavaScript简称JS，是一种运行在客户端的脚本语言，不需要编译，运行过程中由js解释器(js引擎)逐行来解释并执行。JavaScript也可以基于Node.js进行服务器端编程。

## JavaScript概述

### JavaScript的应用

- 表单动态检测(JS产生最初的目的)
- 网页特效
- 服务端开发(Node.js)
- 桌面程序(Electron)
- App(Cordova)
- 控制硬件-物联网(Ruff)
- 游戏开发(cocos2d-js)

### 浏览器执行JavaScript

浏览器分成两部分：渲染引擎和JS引擎。

- 渲染引擎：用来解析HTML和CSS，俗称内核，如blink和webkit；
- JS引擎：也成JS解释器，用来读取网页中的JavaScript代码，对其处理后运行，如Chrome浏览器的V8。

**浏览器本身不会执行JS代码，而是通过内置JavaScript引擎来执行JS代码。JS引擎执行代码时逐行解释每一句源码(转换为机器语言)，然后由计算机去执行，所以JavaScript归为脚本语言，会逐行解释执行。**

### JavaScript组成

JavaScript由ECMAScript、DOM和BOM组成。

- ECMAScript：**规定了JS的编程语法和基础核心知识**；
- DOM：文档对象模型，对页面上的各种元素进行操作；
- BOM：浏览器对象模型，对浏览器窗口进行操作。

## 引入JavaScript

示例：[02-JS初体验](./JavaScript/day01/example/02-JS初体验.html)

### 行内式

行内式的JS位于body标签之内：

```html
<!-- 行内式的js，直接卸载元素内部 -->
<input type="button" value="唐伯虎" onclick="alert('秋香姐')">
```

- 可以将单行或少量JS代码卸载HTML标签的事件属性中(以on开头的属性)，如onclick；
- **在HTML中推荐使用双引号，在JS中推荐使用单引号**；
- 可读性差，不方便阅读；
- 引号易错，当引号多层嵌套时，容易弄混。

### 内嵌式

内嵌式的JS位于head标签之内，使用script标签包含JS代码：

```html
<!-- 2.内嵌式的js -->
<script>
    alert('沙漠骆驼');
</script>
```

- 可以将多行JS代码写到script标签中；
- 内嵌JS是学习时时常使用的方式。

### 外部

外部的JS，建立以.js为扩展名的JS文件，在其中写入JS代码，在HTML的head标签中通过script标签引入JS文件：

```html
<!-- 外部js，script双标签 -->
<script src="js/my.js"></script>
```

- 引入外部JS文件的script标签中不可以写代码；
- 适合与JS代码量比较大的情况。

## JavaScript语法

### 注释

示例：[03-JS注释](./JavaScript/day01/example/03-JS注释.html)

单行注释

```js
// 单行注释，默认VSCode快捷键 ctrl + /
```

多行注释

```js
/*
	多行注释
    默认VS Code快捷键 shift + alt + a
*/
```

可以修改多行注释快捷键为ctrl + shift + /。

### 输入输出

示例：[04-JS输入输出语句](./JavaScript/day01/example/04-JS输入输出语句.html)

#### 输出

- `alert(msg)`：浏览器弹出警示框；

  ```js
  // prompt，这是一个输入框
  prompt('请输入您的年龄');
  ```

- `console.log(msg)`：浏览器控制台打印输出信息。

  ```js
  // alert，弹出警示框，输出的，展示给用户的
  alert('计算的计算果是');
  ```

#### 输入

`prompt(info)`：浏览器弹出输入框，用户可以输入。

```js
// console，控制台输出，给程序员测试用的
console.log('我是程序员能看到的');
```

### 变量

#### 变量的使用

示例：[05-变量](./JavaScript/day01/example/05-变量.html)

变量的使用分为两步：

1. 声明变量；

   ```js
   // 声明变量
   var age;  // 声明一个名为age的变量
   ```

   - var是一个JS关键字，用来声明变量，使用该关键字声明变量后，计算机会自动为变量分配内存空间，不需要程序员管；
   - age是程序员定义的变量名，我们要通过变量名来访问内存中分配的空间。

2. 赋值。

   ```js
   // 2.赋值，把值存入这个变量中
   age = 18;
   ```

此外还可以使用变量的初始化来声明变量：

```js
var my_name = 'pink老师';
```

变量案例：

1. [06-变量案例](./JavaScript/day01/example/06-变量案例.html)
2. [07-变量案例弹出用户名](./JavaScript/day01/example/07-变量案例弹出用户名.html)

#### 变量更新

可以对变量重新赋值:

示例：[08-变量的语法扩展](./JavaScript/day01/example/08-变量的语法扩展.html)

```js
var my_name = 'pink老师';
console.log(my_name);
my_name = '迪丽热巴';
console.log(my_name);
```

#### 声明多个变量

多个变量之间用逗号隔开：

示例：[08-变量的语法扩展](./JavaScript/day01/example/08-变量的语法扩展.html)

```js
// 声明多个变量
var age = 18,
    address = '火影村',
    salary = 2000;
```

#### 声明变量的特殊情况

示例：[08-变量的语法扩展](./JavaScript/day01/example/08-变量的语法扩展.html)

- 只声明，不赋值：变量是undefined，未定义的；

  ```js
  var sex;
  console.log(sex);  // undefined
  ```

- 不声明，不赋值，直接使用变量会报错；

  ```js
  console.log(tel);
  ```
  报错如下：
  > Uncaught ReferenceError: tel is not defined
  >     at 08-变量的语法扩展.html:26:21

- 不声明，直接赋值，可以使用，但不推荐使用。

  ```js
  qq = 110;
  console.log(qq);
  ```
  

#### 变量的命名规范

示例：[09-变量命名规范](./JavaScript/day01/example/09-变量命名规范.html)

- 由字母(A-Za-z)、数字(0-9)、下划线(_)、美元符号($)组成，如usrAge, num01, _name；
- 严格区分大小写；
- 不能以数字开头；
- 不能是关键字、保留字；
- 变量名必须有意义；
- 遵循驼峰命名法：首字母小写，后面单次的字母需要大写，如myFirstName。

==注意：name在大多数浏览器中有含义，不要用于变量命名。==

课堂案例：[10-交换两个变量的值](./JavaScript/day01/example/10-交换两个变量的值.html)

### 数据类型

示例：[11-变量的数据类型](./JavaScript/day01/example/11-变量的数据类型.html)

**JavaScript是一种弱类型或者说动态语言**，不用提前声明变量的类型，在程序运行过程中，类型会被自动确定。

**相同的变量可以用作不同的类型**。

```js
// js是动态语言，变量的数据类型是可以变化的
var x = 10;  // x是数字型
x = 'pink';  // x是字符串型
```

#### 简单(基本)数据类型

| 简单数据类型 | 说明                                | 默认值    |
| ------------ | ----------------------------------- | --------- |
| Number       | 数字型，包含整型和浮点型            | 0         |
| Boolean      | 布尔类型，如true和false，等价于1和0 | false     |
| String       | 字符串类型                          | ""        |
| Undefined    | 变量声明，但未赋值，即为undefined   | undefined |
| Null         | var a = null；声明了变量a为空值     | null      |

##### 数字型 Number

示例：[12-数字型Number](./JavaScript/day01/example/12-数字型Number.html)

整型和浮点型在JS中都属于数字型。

```js
var num = 10;  // num 数字型
var PI = 3.14;  // PI 数字型
```

###### 数字型进制

示例：[12-数字型Number](./JavaScript/day01/example/12-数字型Number.html)

- 八进制，在数字前面加0

  ```js
  // 1. 八进制，0~7，在数字前面加0
  var num1 = 010;
  console.log(num1);
  ```

- 十六进制，在数字前面加0x

  ```js
  // 2. 十六进制，0 ~ 9 a ~ f，数字前面加0x表示十六进制
  var num3 = 0x9;
  console.log(num3);
  var num4 = 0xa;
  ```

###### 数字型的范围

示例：[12-数字型Number](./JavaScript/day01/example/12-数字型Number.html)

- 最大值：`Number.MAX_VALUE`

  ```js
  console.log(Number.MAX_VALUE);  // 1.7976931348623157e+308
  ```

- 最小值：`Number.MIN_VALUE`

  ```js
  console.log(Number.MIN_VALUE);  // 5e-324
  ```

###### 数字型三个特殊值

示例：[12-数字型Number](./JavaScript/day01/example/12-数字型Number.html)

- `Infinity`：代表无穷大，大于任何数值

  ```js
  console.log(Number.MAX_VALUE*2);  // Infinity 无穷大
  ```

- `-Infinity`：代表无穷小，小于任何数值

  ```js
  console.log(-Number.MAX_VALUE*2)  // -Infinity 无穷小
  ```

- `NaN`：Not a number，代表一个非数值

  ```js
  console.log('pink老师' - 100)  // NaN
  ```

###### isNaN()方法

示例：[13-isNaN](./JavaScript/day01/example/13-isNaN.html)

用于判断是否为非数字，如果非数字，返回true，如果是数字，返回false。

```js
console.log(isNaN(12))  // false
console.log(isNaN('pink老师'))  // true
```

##### 字符串型 String

字符串可以使用**双引号**或**单引号**，推荐使用单引号。

###### 引号嵌套

示例：[14-字符串型String](./JavaScript/day01/example/14-字符串型String.html)

外单内双，外双内单。

```js
// 外单内双
var str = '我是一个"高富帅"的程序员';
console.log(str)
// 外双内单
str = "我是一个'高富帅'的程序员";
console.log(str)
```

###### 转义字符

- `\n`：换行符
- `\\`：斜杠
- `\'`：单引号
- `\"`：双引号
- `\t`：制表符
- `\b`：退格

课堂案例：[弹出网页警示框](./JavaScript/day01/example/14-字符串型String.html)

###### 字符串长度

示例：[16-字符串拼接](./JavaScript/day01/example/16-字符串拼接.html)

可以使用length获取字符串的长度：

```js
var str = 'my name is andy';
console.log(str.length);  // 11
```

###### 字符串拼接

示例：[16-字符串拼接](./JavaScript/day01/example/16-字符串拼接.html)

可以使用+来拼接字符串：

```js
console.log('沙漠' + '骆驼');  // 沙漠骆驼
console.log('pink老师' + 18);  // pink老师18
console.log('pink' + true);  // pinktrue
console.log(12 + 12);  // 24
console.log('12' + 12);  // 1212
```

可以使用+来链接字符串和变量：

示例：[17-字符串拼接加强](./JavaScript/day01/example/17-字符串拼接加强.html)

```js
var age = 18;
console.log('pink老师' + age + '岁');
```

案例：[18-显示年龄案例](./JavaScript/day01/example/18-显示年龄案例.html)

##### 布尔型 Boolean

示例：[19-布尔型Boolean](./JavaScript/day01/example/19-布尔型Boolean.html)

布尔值有两个值：`true`和`false`。

```js
var flag = true;
var flag1 = false;
```

布尔值类型在参与算数运算时，`true`当成1，`false`当成0。

```js
console.log(flag + 1);  // 2
console.log(flag1 + 1);  // 1
```

##### Undefined

示例：[20-undefined和null](./JavaScript/day01/example/20-undefined和null.html)

一个声明后没有被赋值的变量会有一个默认值undefined。

```js
var str;
console.log(str);  // undefined
```

undefined与字符串使用+连接，相当于拼接字符串：

```js
console.log(variable + 'pink');  // undefinedpink
```

undefined与数字类型相加：

```js
console.log(variable + 1);  // NaN
```

##### Null

示例：[20-undefined和null](./JavaScript/day01/example/20-undefined和null.html)

可以将变量声明为null：

```js
var space = null;
```

null与字符串使用+连接，相当于拼接字符串：

```js
console.log(space + 'pink');  // nullpink
```

null与数字类型相加：

```js
console.log(space + 1);  // 1
```

#### typeof变量获取数据类型

示例：[21-获取变量数据类型](./JavaScript/day01/example/21-获取变量数据类型.html)

可以使用`typeof`运算符来获取变量的数据类型：

```js
var num = 10;
console.log(typeof num);  // number
var str = 'pink';
console.log(typeof str);  // string
var flag = true;
console.log(typeof flag);  // boolean
var undefi = undefined;
console.log(typeof undefi); // undefined
var timer = null;
console.log(typeof timer);  // object
```

可以用来检测`prompt()`函数获取的值的数据类型：

```js
var age = prompt('请输入您的年龄');
console.log(age);
console.log(typeof age);  // string
```

可以发现JS中的`prompt()`类似于Python中的`input()`，获取的输入值都是字符串类型的。

**在Chrome的调试窗口中，字符串都是用黑色字体表示的。**

#### 字面量

- 数字字面量：8，9，10
- 字符串字面量：'黑马程序员', '大前端'
- 布尔字面量：true，false

#### 数据类型转换

JS中可以按需求，将一种数据类型的变量转换为另一种数据类型。

常用的三种转换方式：

- 转换为字符串类型
- 转换为数字型
- 转换为布尔型

##### 转换为字符串

示例：[22-转换为字符串型](./JavaScript/day01/example/22-转换为字符串型.html)

| 方式                     | 说明                         | 案例                                      |
| ------------------------ | ---------------------------- | ----------------------------------------- |
| toString()               | 转成字符串                   | `var num = 1; alert(num.toString());`     |
| String()强制转换         | 转成字符串                   | `var num = 1; alert(String(num));`        |
| **加号拼接字符串(常用)** | 和字符串拼接的结果都是字符串 | `var num = 1; alert(num + '我是字符串');` |

```js
// 把数字型转换为字符串型
// 1.变量.toString()
var num = 10;
var str = num.toString();
console.log(str);  // 10
console.log(typeof str);  // string
// 2.利用String(变量)
console.log(String(num));  // string
// 3.利用+拼接字符串，隐式转换
console.log(num+'');  // string
```

##### 转换为数字型(重点)

示例：[23-转换为数字型](./JavaScript/day01/example/23-转换为数字型.html)

| 方式                       | 说明                         | 案例                |
| -------------------------- | ---------------------------- | ------------------- |
| **parseInt(string)函数**   | 将string类型转成整数数值型   | parseInt('78')      |
| **parseFloat(string)函数** | 将string类型转成浮点数数值型 | parseFloat('78.21') |
| Number()强制类型转换       | 将string类型转成数值型       | Number('12')        |
| js隐式转换(. * /)          | 利用算数运算隐式转换为数值型 | '12' - 0            |

```js
var age = prompt('请输入您的年龄');
// 1.parseInt(变量) 可以把字符型转换为数字型 得到的是整数
console.log(parseInt(age));
console.log(parseInt('3.14'));  // 3，会取整
console.log(parseInt('3.96'));  // 3，会取整
console.log(parseInt('120px'));  // 120，会去掉px单位
console.log(parseInt('rem120px'));  // NaN
// 2.parseFloat(变量) 可以把字符型转换为数字型，得到的是浮点数
console.log(parseFloat('3.14'));
console.log(parseFloat('120px'));  // 120，会去掉px单位
console.log(parseFloat('rem120px'));  // NaN
// 3.利用Number(变量)
var str = '123';
console.log(Number(str))
console.log(Number('12'));
// 4.利用算数运算- * / 隐式转换
console.log('12' - 0);
console.log('123' - '120');  // 3
console.log('123' * 1);  // 123
```

案例

1. [24-计算年龄案例](./JavaScript/day01/example/24-计算年龄案例.html)
2. [25-简单加法器案例](./JavaScript/day01/example/25-简单加法器案例.html)

##### 转换为布尔型

示例：[26-转换为布尔型](./JavaScript/day01/example/26-转换为布尔型.html)

使用`Boolean()`函数将其他类型转换成布尔值。

- 代表空、否定的值会被转换为`false`，如`''`、`0`、`NaN`、`null`、`undefined`
- 其余值转换为`true`

```js
console.log(Boolean(''));  // false
console.log(Boolean(0));  // false
console.log(Boolean(NaN));  // false
console.log(Boolean(null));  // false
console.log(Boolean(undefined));  // false
```

课后作业：[27-课后作业](./JavaScript/day01/example/27-课后作业.html)