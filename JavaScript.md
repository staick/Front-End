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

### 运算符

#### 算数运算符

算数运算符使用的符号，用于执行两个变量或值的算数运算。

| 运算符 | 描述 | 实例           |
| ------ | ---- | -------------- |
| +      | 加   | `10 + 20 = 30` |
| -      | 减   |                |
| *      | 乘   |                |
| /      | 除   |                |
| %      | 取模 |                |

#### 自增自减运算符

与C语言一致。

- `a++`
- `a--`
- `++a`
- `--a`

#### 比较运算符

较C语言新增了两个元素符：`===`和`!==`，而且`==`和稍有不同

- `==`：等于，值相等，数据类型不要求相等，如：

  ```js
  console.log(1 == '1');  // true
  ```

- `===`：全等，要求值和数据类型都一致。

  ```js
  console.log(18===18);  // true
  console.log(18==='18');  // false
  ```

- `!==`：不全等

#### 逻辑运算符

JS有三个逻辑运算符，与C语言一致：`&&`、`||`、`!`，也具有短路的性质。

#### 赋值运算符

与C语言类似，有`=`、`+=`、`-=`、`*=`、`/=`、`%=`。

#### 运算符优先级

| 优先级 | 运算符     | 顺序            |
| ------ | ---------- | --------------- |
| 1      | 小括号     | ()              |
| 2      | 一元运算符 | ++ -- !         |
| 3      | 算数运算符 | 先 * / % 再 + - |
| 4      | 关系运算符 | > >= < <=       |
| 5      | 相等运算符 | == != === !\==  |
| 6      | 逻辑运算符 | 先&& 后 \|\|    |
| 7      | 赋值运算符 | =               |
| 8      | 逗号运算符 | ,               |

### 流程控制

#### 分支语句

##### if语句

##### 三元运算符

##### switch语句

#### 循环语句

##### for循环

##### while循环

##### do-while循环

##### continue和break

### 函数

#### arguments的使用

当我们不确定有多少个参数传递的时候，可以用arguments来获取。在JavaScript中，arguments实际上它是当前函数的一个内置对象。所有函数都内置了一个对象arguments对象，arguments对象中存储了传递的所有实参。

arguments是以伪数组的形式展示的。伪数组并不是真正的数组，它有一下三个特性：

1. 具有数组的`length`属性
2. 按照索引的方式进行存储
3. 没有真正数组的一些方法，如`pop()`、`push()`等

### 作用域

ES6之前JavaScript中没有块级作用域，只有全局作用域和局部作用域(由于没有块级作用域，所有只有函数作用域)。

#### 作用域链

内部函数访问外部函数的变量，采取的是链式查找的方式来决定取哪个值，这种结构称为作用域链。

### 预解析

JavaScript代码是由浏览器中的JavaScript解析器来执行的。JavaScript解析器在运行JavaScript代码的时候分为两步：预解析和代码执行。

```js
f1();
console.log(c);
console.log(b);
console.log(a);

function f1() {
    var a = b = c = 9;
    // 相当于 var a = 9; b = 9; c = 9; b和c直接赋值，没有声明，当全局变量看
    console.log(a);
    console.log(b);
    console.log(c);
}
// 相当于
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

### 对象

在JavaScript，对象是一组无序的属性和方法的集合，所有的事物都是对象，例如字符串、数值、数组、函数等。

#### 创建对象

在JavaScript中，现阶段可以采用三种方式创建对象：

- 利用字面量创建对象

- 利用`new Object` 创建对象

- 利用构造函数创建对象

##### 利用字面量创建对象

```js
var obj = {
    uname: '张三丰',
    age: 18,
    sex: '男',
    sayHi: function() {
        console.log('hi~');
    }
}
```

- 里面的属性或方法我们采用键值对的形式，`键: 值;`
- 多个属性或者方法之间用逗号隔开
- 方法冒号后面跟的是一个匿名函数

##### 利用new Object创建对象

```js
var obj = new Object();  // 创建了一个空的对象
obj.uname = '张三丰';
obj.age = 18;
obj.sex = '男';
obj.sayHi = function() {
    console.log('hi~');
}
```

##### 利用构造函数创建对象

上面两种方式一次只能创建一个对象。

```js
function Star(uname, age, sex) {
    this.name = uname;
    this.age = age;
    this.sex = sex;
}

var ldh = new Star('刘德华', 18, '男');
```

- 构造函数名字首字母要大写
- 构造函数不需要`return`就可以返回结果
- 要调用构造函数，必须使用`new`
- 只要`new Star()`调用函数就创建一个对象

#### 使用对象

调用对象的属性，有两种方式：

- 采用`对象名.属性名`

  ```js
  console.log(obj.uname);
  ```

- 采用`对象名['属性名']`

  ```js
  console.log(obj['age']);
  ```

调用对象的方法`对象名.方法名()`

```js
obj.sayHi();
```

`new`的执行过程：

1. `new`构造函数在内存中创建了一个空的对象
2. `this`指向刚才创建的空对象
3. 执行构造函数里面的代码，给这个空对象添加属性和方法
4. 返回这个对象

### 内置对象

#### Math

#### Date

#### Array

##### 添加数组元素

- `Array.push()`：在末尾添加一个或多个元素
- `Array.unshift()`：在开头添加一个或多个元素

##### 删除数组元素

- `Array.pop()`：删除数组的最后一个元素
  - 删除数组的最后一个元素，一次只能删除一个元素
  - 没有参数
  - 返回值是删除的那个元素
  - 原数组也会发生变化
- `Array.shift()`：删除数组的第一个元素
  - 删除数组的第一个元素，一次只能删除一个元素
  - 没有参数
  - 返回值是删除的那个元素
  - 原数组也会发生变化

##### 翻转数组

##### 数组排序

##### 获取数组元素索引

`indexOf`：返回数组的索引号

`lastIndexOf()`：从后面开始查找

##### 数组转换为字符串

`toString()`

`join()`





`concat()`

`slice()`

`splice()`

### 基本包装类型

为了方便操作基本数据类型，JavaScript还提供了三个特殊的引用类型：`String`、`Number`、`Boolean`。

基本包装类型就是把简单数据类型包装成为复杂数据类型，这样基本数据类型就有了属性了方法。

```js
var 
```

#### String

字符串的不可变：指的是字符串里面的值是不可变的，虽然看上去可以改变内容，但其实是地址变了，内存中新开辟了一个内存空间。

##### 根据字符返回位置

`indexof()`

##### 根据位置返回字符

- `charAt(index)`：返回指定位置的字符(index为字符串的索引号)，`str.charAt(0)`
- `charCodeAt(index)`：获取指定位置处字符的ASCII码(index索引号)，`str.charCodeAt(0)`
- `str[index]`：获取指定位置处字符，H5新增，和`charAt()`等效

#### Number

#### Boolean

# Web API

API是给程序员提供的一种工具，以便能更轻松的实现想要完成的功能。

Web API是浏览器提供的一套操作浏览器功能和页面元素的API(BOM和DOM)。

## DOM

文档对象模型(Document Object Model)，是处理可扩展标记语言(HTML或XML)的标准接口。

W3C定义了一系列的DOM接口，通过这些DOM接口可以改变网页的内容、结构和样式。

### DOM树

- 文档：document，一个页面就是一个文档
- 元素：element，页面中的所有标签都是元素
- 节点：node，网页中的所有内容都是节点

**DOM把以上内容都看作对象**

### 获取元素

因为文档页面从上往下加载，得先有标签，所以script写在标签的下面

#### 根据ID获取

#### 根据标签名获取

还可以获取某个元素内部的所有指定标签名的子元素，父元素必须是单个对象(必须指明是哪一个元素对象)，获取的时候不包括父元素自己。

```js
```



#### H5新增

#### 特殊元素获取

#### 排他思想

##### 案例：百度换肤

##### 案例：全选与反选

#### 自定义属性操作

在开发中有时候需要自定义属性。对于自定义属性有相关操作。

```html
<div id="demo" index="1">
    
</div>
```

##### 获取属性值

使用`element.getAttribute(属性名)`来获取属性值(此方法也可用于内置属性)

```js
var div = document.querySelector('div');
div.getAttribute('index');
div.getAttribute('id');
```

##### 设置属性

使用`element.setAttribute(属性名, 属性值)`来设置属性(此方法也可用于内置属性)

```js
div.setAttribute('index', 2);
div.setAttribute('class', 'footer');
```

##### 删除属性

使用`element.removeAttribute(属性名)`来删除属性(此方法也可用于内置属性)

```js
div.removeAttribute('index');
div.removeAttribute('id');
```

##### H5自定义属性

在H5中规定自定义属性以`data-`开头，如前面的`index`属性应该设置为`data-index`，`list-name`应该设置为`data-list-name`。

```html
<div data-index="2", data-list-name="staick"></div>
```

在H5中，可以使用`element.dataset`来获取存放所有`data`开头的自定义属性。

```js
div.dataset.index = 5;
div.dataset.listName = 'Micheal';  // 注意要采用驼峰命名法
div.dataset['listName'] = 'Mike';  // 注意要采用驼峰命名法 
```

##### 案例：tab栏切换

### 节点

一般的，节点至少拥有`nodeType`(节点类型)、`nodeName`(节点名称)和`nodeValue`(节点值)这三个基本属性。

- 元素节点`nodeType`为 1
- 属性节点`nodeType`为2
- 文本节点`nodeType`为3(文本节点包含文字、空格、换行等)

==在实际开发中，节点操作主要操作的是**元素节点**==

#### 获取节点

##### 父节点

可以使用`element.parentNode`获取父节点。

- 上述方法获取的是离元素最近的父级节点
- 找不到，返回空

##### 子节点

可以使用`element.childNodes`或`element.children`两种方法获取字节点。

- `element.childNodes`获取的子节点包含文本节点等，需要判断`nodeType`，比较麻烦，所以不常用
- `element.children`获取的子节带点不包括文本节点，常用

可以使用`element.firstChild`获得第一个子节点，但是包含文本节点，使用`element.firstElementChild`也可以获得第一个子节点，只包含元素节点。

同样的使用`element.lastChild`和`element.lastElementChild`获取最后一个子节点。

##### 兄弟节点

可以使用`element.nextSibling`和`element.nextElementSibling`获取兄弟节点，同样的，常使用`element.nextElementSibling`获取兄弟节点。

#### 创建节点和添加节点

使用`document.createElement(节点名)`来创建节点

```js
var li = document.createElement('li');
```

创建的节点需要通过`node.appendChild(child)`来追加到指定位置

```js
ul.appendChild(li);
```

也可以使用`node.indertBefore(child, 指定元素)`在任意位置添加节点

```
ul.insertBefore(li, ul.children[0]);
```

#### 删除节点

示例：[01-节点操作之删除节点](./JavaScript/day09/example/01-节点操作之删除节点.html)

使用`node.removeChild(child)`来删除子节点。

#### 克隆节点

示例：[03-节点操作之复制节点](./JavaScript/day09/example/03-节点操作之复制节点.html)

使用`node.cloneNode()`来克隆节点。

- 如果括号参数为空或为`false`，则为浅拷贝，只克隆节点本身，不可能里面的子节点。
- 如果括号参数为`true`，则为深拷贝，即克隆节点本身又克隆子节点。

#### 三种创建元素的方式

示例：[05-三种创建元素方式区别](./JavaScript/day09/example/05-三种创建元素方式区别.html)

- `document.write()`
- `element.innerHTML`
- `document.createElement()`

##### 区别

1. `document.write`是直接将内容写入到页面的内容流，**但是文档执行完毕，则它会导致页面全部重绘**。
2. `innerHTML`是将内容写入到某个DOM节点，不会导致页面全部重绘。
3. `innerHTML`创建多个元素效率更高(不要拼接字符串，采取数组形式拼接)，结构稍微复杂。
4. `createElement()`创建多个元素效率稍微低一点点，但是结构清晰。

### 事件

#### 注册事件

示例：[06-注册事件的两种方式](./JavaScript/day09/example/06-注册事件的两种方式.html)

给元素添加事件，成为注册时间或者绑定事件。注册事件有两种方式：传统注册方式和方法监听注册方式

##### 传统注册方式

- 利用`on`开头的事件`onclick`
- 特点：注册事件的**唯一性**
- 同一个元素同一个事件只能设置一个处理函数，最后注册的处理函数将会覆盖前面注册的处理函数。

##### 方法监听注册方式

- w3c标准，推荐方式
- `addEventListener()`，是一个方法
- IE9之前的IE不支持此方法，可使用`attachEvent()`代替
- 特点：同一个元素同一个事件可以注册多个监听器
- 按注册顺序依次执行

`eventTarget.addEventListener(type, listener[, useCapture])`：将指定的监听器注册到`eventTarget`上，当该对象触发指定的事件时，就会执行事件处理函数。

- `type`：事件类型字符串，比如`click`、`mouseover`，注意不用带`on`
- `listener`：事件处理函数，事件发生时，会调用该监听函数
- `useCapture`：可选参数，是一个布尔值，默认是`false`。

#### 删除事件

示例：[07-删除事件](./JavaScript/day09/example/07-删除事件.html)

##### 传统注册方式

`eventTarget.onclick = null;`

##### 方法监听注册方式

`eventTarget.removeEventListener(type, listener[, useCapture]);`

#### DOM事件流

示例：[08-DOM事件流三个阶段](./JavaScript/day09/example/08-DOM事件流三个阶段.html)

事件发生时会在元素节点之间按照特定的顺序传播，这个传播过程即DOM事件流。

- JS代码中只能执行捕获或者冒泡其中的一个阶段
- `onclick`和`attachEvent`只能得到冒泡阶段
- `addEventListener(type, listener[, useCapture])`第三个参数如果是`true`，表示在事件捕获阶段调用事件处理程序；如果是`false`(默认)，表示事件冒泡阶段调用事件处理程序。
- **实际开发中很少使用事件捕获，更关注事件冒泡**
- **有些事件没有冒泡，比如`onblur`、`onfocus`、`onmouseenter`、`onmouseleave`**
- **事件冒泡有时候会带来麻烦，有时候又会帮助很巧妙的做某些事件**

#### 事件对象

示例：[09-事件对象](./JavaScript/day09/example/09-事件对象.html)

1. event就是一个事件对象，写到我们监听函数小括号里，当形参
2. 事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数
3. 事件对象是我们事件的一系列相关数据的集合，跟事件相关的，比如鼠标点击里面就包含了鼠标的相关信息：鼠标坐标，如果是键盘事件，里面就包含键盘事件的信息，如用于按下了哪个键

可以使用`e.target`获得事件对象，它有时候和`this`获得的对象相同，但需要注意，`e.target`返回的是出发事件对象，`this`返回的是绑定事件对象。

#### 阻止默认事件

示例：[11-事件对象阻止默认行为](./JavaScript/day09/example/11-事件对象阻止默认行为.html)

我们使用`e.preventDefault();`可以阻止一些默认事件，如链接跳转、表单提交。

对于ie9以下的浏览器，采用`e.returnValue;`

使用`return false`也可以达到相同的效果，且没有兼容问题，但会使return后面的代码不执行，且不能用于方法监听方式中。

#### 阻止冒泡

示例：[12-阻止事件冒泡](./JavaScript/day09/example/12-阻止事件冒泡.html)

事件冒泡有时会带来坏处，

`e.stopPropagation();`

低版本浏览器使用`e.cancleBubble = true;`来阻止冒泡

#### 事件委托

示例：[13-事件委托](./JavaScript/day09/example/13-事件委托.html)

事件冒泡出来，有时也会带来好处

事件委托也称为事件代理，在jQuery里面称为事件委派。

**不是每个子节点单独设置事件监听器，而是事件监听器设置在其父节点上，然后利用冒泡原理影响设置每个子节点。**

事件委托的作用：只操作了一次DOM，提高了程序的性能。

#### 常用鼠标事件

示例：[14-常见鼠标事件](./JavaScript/day09/example/14-常见鼠标事件.html)

##### 禁止鼠标右键菜单

`contextmenu`主要控制应该何时显示上下文菜单，主要用于程序员取消默认的上下文菜单

```js
document.addEventListener('contextmenu', function(e) {
    e.preventDefault();
});
```

##### 禁止鼠标选中

```js
document.addEventListener('selectstart', function(e) {
    e.preventDefault();
});
```

#### 鼠标事件对象

示例：[15-鼠标事件对象](./JavaScript/day09/example/15-鼠标事件对象.html)

`event`对象代表事件的状态，跟事件相关的一系列信息的集合。现阶段我们主要用鼠标事件对象`MouseEvent`和键盘事件对象`KeyboardEvent`。 

##### 获取鼠标的可视区的坐标

- `e.clientX`：获取x坐标
- `e.clientY`：获取y坐标

##### 获取鼠标在文档页面的坐标

- `e.pageX`：获取x坐标
- `e.pageY`：获取y坐标

##### 获取鼠标在电脑屏幕的坐标

- `e.screenX`：获取x坐标
- `e.screenY`：获取y坐标

#### 常用键盘事件

| 键盘事件     | 触发条件                                                    |
| :----------- | :---------------------------------------------------------- |
| `onkeyup`    | 按键被松开时触发                                            |
| `onkeydown`  | 按键被按下时触发                                            |
| `onkeypress` | 按键被按下时触发，**但不能识别功能键，如ctrl shift 箭头等** |

三个事件的执行顺序：`onkeydown -> onkeypress -> onkeyup`

#### 键盘事件对象

**`onkeydown`和`onkeyup`不区分字母大小写，`onkeypress`区分字母大小写。在实际开发中，更多的使用`keydown`和`keyup`，它能识别所有的键，`keypress`不能识别功能键，但是`keyCode`属性能区分大小写，返回不同的ASCII值。**

==keydown和keypress在文本框里面的特点：他们两个事件触发的时候，文字还没有落入文本框中。==

==keyup事件触发的时候，文字已经落入文本框里面了==

## BOM

BOM包括DOM

### BOM的构成

**window**对象是浏览器的顶级对象，它具有双重角色。

1. 它是JS访问浏览器窗口的一个接口
2. 它是一个全局对象。定义在全局作用域中的变量、函数都会变成window对象的属性和方法。

#### 窗口加载事件

```js
window.onload = fucntion() {}
或
window.addEventListener('load', function(){});
```

`window.onload`是窗口加载事件，当文档内容完全加载完全会触发该事件(包括图像、脚本文件、CSS文件等)，就调用的处理函数。

有了`window.onload`就可以把JS代码写到页面元素的上方，因为`onload`是等页面内容全部加载完毕，再去执行处理函数。

#### 窗口加载事件

```js
document.addEventListener('DOMContentLoaded', function() {})
```

`DOMContentLoaded`事件触发时，仅当DOM加载完成，不包括样式表，图片，flash等。IE9以上支持

如果页面的图片很多，从用户访问到`onload`触发可能需要较长的事件，交互效果就不能实现，必然影响用户的体验，此时用`DOMContentLoaded`事件比较合适。

#### 调整窗口大小事件

```js
window.addEventListener('resize', function() {})
```

`window.onresize`是调整窗口大小加载事件，当触发时就调用的处理函数。

- 只要窗口大小发生像素变化，就会触发这个事件
- 经常利用这个事件完成响应式布局。`window.innerWidth`当前屏幕的宽度

#### 定时器

`window`对象给我们提供了2个非常好用的方法-定时器。

- `setTimeout()`
- `setInterval()`

##### setTimeout()定时器

`window.setTimeout(调用函数, [延迟的毫秒数]);`

`setTimeout()`方法用于设定一个定时器，该定时器在定时器到期后执行调用函数。

- `window`可以省略
- 这个调用函数可以直接写函数，或者函数名或者采取字符串`函数名()`三种形式，第三种不推荐
- 延迟的毫秒数省略默认是0，如果写，单位是毫秒
- 因为定时器有很多，为了便于区别，可以使用`var time1 = setTimeout()`的形式给定时器起别名。

##### 停止setTimeout()定时器

`window.clearTimeout(timeoutID)`

##### setInterval()定时器

`window.setInterval(回调函数, [间隔的毫秒数]);`

`setInterval()`方法重复调用一个函数，每隔这个时间，就去调用一次回调函数。

#### this

- 在全局作用域或者普通函数中`this`指向全局对象`window`

#### 同步和异步

同步任务都在主线程上执行，形成一个执行栈。

JS的异步是通过回调函数实现的。

一般而言，异步任务有以下三种类型：

1. 普通事件，如`click`、`resize`等
2. 资源加载，如`load`、`error`等
3. 定时器，包括`setInterval`、`setTimeout`等

##### JS的执行机制

1. 先执行执行栈中的同步任务
2. 异步任务(回调函数)放入任务队列中。
3. 一旦执行栈中的所有同步任务执行完毕，系统就会按次序读取任务队列中的异步任务，于是被读取的异步任务结束等待状态，进入执行栈，开始执行。

#### location

window对象给我们提供了一个`location`属性用于获取或设置窗体的URL，并且可以用于解析URL。因为这个属性返回的是一个对象，所以我们将这个属性也成为`loacation`对象。

| location对象属性    | 返回值                          |
| ------------------- | ------------------------------- |
| `location.href`     | 获取或者设置整个URL             |
| `location.host`     | 返回主机名                      |
| `location.port`     | 返回端口号 如果未写返回空字符串 |
| `location.pathname` | 返回路径                        |
| `location.search`   | 返回参数                        |
| `location.hash`     | 返回片段                        |

`location`方法

| location对象方法     | 描述 |
| -------------------- | ---- |
| `location.assign()`  |      |
| `location.replace()` |      |
| `location.reload()`  |      |

#### navigator

`navigator`对象包含有关浏览器的信息，它有很多属性，最常用的是`userAgent`，该属性可以返回由客户端发送服务器的`user-agent`头部的值。

#### history

| history对象方法 | 作用                                                         |
| --------------- | ------------------------------------------------------------ |
| `back()`        | 后退功能                                                     |
| `forward()`     | 前进功能                                                     |
| `go(参数)`      | 前进后退功能，如果参数是1，前进1个页面，如果是-1，后退一个页面 |
