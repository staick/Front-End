# HTML

HTML，即Hyper Text Markup Language，文本标记语言。

HTML通常以`.html`作为后缀名，如`index.html`

## 语法规范

### 基本语法概述

1. HTML标签由尖括号包围的关键词，如`<html>`；
2. HTML标签通常成对出现，如`<html></html>`，这种称为**双标签**，标签中第一个标签是开始标签，第二个是结束标签；
3. 有些特殊的标签必须是单个标签，例如`<br />`，这种称为单标签。

### 标签关系

双标签关系可以分为两类：**包含关系**和**并列关系**。

- 包含关系

  ```html
  <head>
      <title></title>
  </head>
  ```

  其中，`head`和`title`是包含关系，`head`是父标签，`title`是子标签。

- 并列关系

  ```html
  <html>
      <head></head>
      <body></body>
  </html>
  ```

  其中，`head`和`body`是并列关系。

### 基本结构标签

```html
<html>
    <head>
        <title>第一个页面</title>
    </head>
    <body>
        键盘敲烂，工资过万！
    </body>
</html>
```

### 标签语义

**根据标签的语义，在合适的地方给一个最为合理的标签，可以让页面结构更为清晰。**

### 常用标签

#### 标题标签

示例：[04-标题标签](./Basic/day01/example/04-标题标签.html)

```html
<h1>标题标签</h1>
<h1>标题一共六级选，</h1>
<h2>文字加粗一行显。</h2>
<h3>由大到小依次减，</h3>
<h4>从重到轻随之变。</h4>
<h5>语法规范书写后，</h5>
<h6>具体效果刷新见。</h6>
------pink老师
```

#### 段落标签

示例：[05-段落和换行标签](./Basic/day01/example/05-段落和换行标签.html)

```html
<p>The Zen of Python, by Tim Peters</p>
<p>Beautiful is better than ugly. Explicit is better than implicit. 
       Simple is better than complex. Complex is better than complicated.
       Flat is better than nested. Sparse is better than dense.
       Readability counts. Special cases aren't special enough to break the rules.
       Although practicality beats purity. Errors should never pass silently.
       Unless explicitly silenced. In the face of ambiguity, refuse the temptation to guess.
       There should be one-- and preferably only one --obvious way to do it.
       Although that way may not be obvious at first unless you're Dutch.
       Now is better than never. Although never is often better than right now. 
       If the implementation is hard to explain, it's a bad idea. 
       If the implementation is easy to explain, it may be a good idea. 
       Namespaces are one honking great idea -- let's do more of those!
</p>
```

#### 换行标签

示例：[05-段落和换行标签](./Basic/day01/example/05-段落和换行标签.html)

强制换行。

```html
Beautiful is better than ugly. Explicit is better than implicit.<br \> 
```

课堂案例：[06-体育新闻](./Basic/day01/example/06-体育新闻.html)

#### 文本格式化标签

示例：[07-文本格式化标签](./Basic/day01/example/07-文本格式化标签.html)

粗体`<strong></strong>`或`<b></b>`

```html
我是<strong>加粗</strong>的文字
我是<b>加粗</b>文字
```

斜体`<em></em>`或`<i></i>`

```html
我是<em>倾斜</em>的文字
我是<i>倾斜</i>文字
```

下划线`<ins></ins>`或`<u></u>`

```html
我是<ins>下划线</ins>
我是<u>下划线</u>
```

删除线`<del></del>`或`<s></s>`

```html
我是<del>删除线</del>
我是<s>删除线</s>
```

#### div和span标签

示例：[08-div和span标签](./Basic/day01/example/08-div和span标签.html)

这两个标签非常常用，但是没有语义，可以看成一个盒子。

div可以看成一个大盒子，独占一行。

span可以看成是一个小盒子，不能独占一行。

```html
<div>我是一个div标签我一个人独占一行</div>
<div>我是一个div标签我一个人独占一行</div>
<span>百度</span>
<span>搜狐</span>
<span>新浪</span>
```

> 我是一个div标签我一个人独占一行
>
> 我是一个div标签我一个人独占一行
>
> 百度 搜狐 新浪

#### 图像标签

示例：[09-图像标签](./Basic/day01/example/09-图像标签.html)

图像标签`<img>`用于显示图像，是一个单标签。

它有如下属性：

- `src`：图片的路径。
- `alt`：替换文本，当图像不能正确显示时，显示该属性定义的文字。
- `title`：提示文本，当鼠标挡在图像时，显示的文字。
- `width`：设置图像的宽度。
- `height`：设置图像的高度。
- `border`：设置图像边框的粗细。

```html
<img src="../images/miku.jpeg">
<!-- 设置替换文本 -->
<img src="miku.jpeg" alt="初音未来">
<!-- 设置提示文本 -->
<img src="../images/miku.jpeg" title="初音未来">
<!-- 设置突变的宽度 -->
<img src="../images/miku.jpeg" width="100px">
<!-- 设置图片的高度 -->
<img src="../images/miku.jpeg" height="100px">
<!-- 设置图像的边框 -->
<img src="../images/miku.jpeg" border="15px">
```

图像标签属性注意点：

1. `src`标签是必须的；
2. 图像标签可以有多个属性，必须卸载标签名后面；
3. 属性之前不分先后顺序，标签名与属性，属性与属性之间以空格隔开；
4. 属性采取键值对的格式，即属性="属性值"；
5. 图像的宽和高一般只设置一个，另一个可等比例缩放；
6. `border`属性通常使用CSS进行设置。

#### 超链接标签

示例：[14-超链接标签](./Basic/day01/example/14-超链接标签.html)

在HTML标签中，`<a></a>`标签用于定义超链接，作用是从一个页面链接到另一个页面。a为anchor的缩写。

格式：`<a href="跳转的目标" target="目标窗口的弹出方式">文本或图像</a>`

它有`href`和`target`两个属性

- `href`：必须属性，用于指定链接目标的url地址；
- `target`：用于指定链接页面的打开方式，`_self`为默认值，在当前窗口打开；`_blank`在新窗口中打开。

```html
<a href="http://www.qq.com" target="_self">腾讯</a>
<a href="http://www.qq.com" target="_blank">腾讯</a>
```

链接分类：

- 外部链接

  ```html
  <a href="http://www.qq.com" target="_blank">腾讯</a>
  ```

- 内部链接，网站内部页面之间的相互链接，直接链接内部页面的名称即可。

  ```html
  <a href="09-图像标签.html">图像标签</a>
  ```

- 空链接，如果没有明确链接目标，可以使用空链接。

  ```html
  <a href="#">空链接</a>
  ```

- 下载链接，如果href里面的地址是非文本文件，会下载这个文件。

  ```html
  <a href="../images/miku.jpeg">下载图片</a>
  ```

- 网页元素链接，在网页中的各种元素，如文本、图像、表格、音频、视频等都可以添加超链接。

  ```html
  <a href="https://www.baidu.com">
      <img src="../images/miku.jpeg">
  </a>
  ```

- 锚点链接，点击链接，可以快速定位到页面中的某个位置。

  示例：[15-锚点定位](./Basic/day01/example/15-锚点定位.html)

  - 在链接文本的href属性中，设置属性值为**#名字**的形式。

    ```html
    <a href="#live">个人生活</a>
    ```

    

  - 找到目标位置标签，里面添加一个id属性=刚才的名字。

    ```html
    <h3 id="live">个人生活</h3>
    ```

#### 注释标签

示例：[16-注释标签和特殊字符](./Basic/day01/example/16-注释标签和特殊字符.html)

```html
<!-- 这是一条注释标签 -->
```

#### 特殊字符

示例：[16-注释标签和特殊字符](./Basic/day01/example/16-注释标签和特殊字符.html)

|   描述   | 字符的代码 |
| :------: | :--------: |
|   空格   |  \&nbsp;   |
|  小于号  |   \&lt;    |
|  大于号  |   \&gt;    |
|   和号   |   \&amp;   |
|  人民币  |   \&yen;   |
|   版权   |  \&copy;   |
| 注册商标 |   \&reg;   |
|  摄氏度  |   \&deg;   |
|  正负号  | \&plusmn;  |
|   乘号   |  \&times;  |
|   除号   | \&divide;  |
|  2次方   |  \&sup2;   |
|  3次方   |  \&sup3;   |

day01综合案例：[综合案例](./Basic/day01/example/17-综合案例/demo.html)

#### 表格标签

##### 表格结构

示例：[01-表格基本语法](./Basic/day02/example/01-表格基本语法.html)

```html
<table>
    <tr>
   		<td></td>
        <td></td>
    </tr>
</table>
```

- `<table></table>`用于定义表格的标签；
- `<tr></tr>`用于定义表格中的行，必须嵌套在`<table></table>`标签中；
- `<td></td>`用于定义表格中的单元格，必须嵌套在`<tr></tr>`标签中；
- td指的是table data，即数据单元格的内容。

##### 表头单元格

示例：[02-表头单元格](./Basic/day02/example/02-表头单元格.html)

可以用`<th></th>`标签替代`<td></td>`来设置表头单元格，表头单元格中的文字居中加粗显示。

```html
<table>
    <tr>
        <th>姓名</th> <th>性别</th> <th>年龄</th>
    </tr>
    <tr>
        <td>刘德华</td> <td>男</td> <td>56</td>
    </tr>
    <tr>
        <td>张学友</td> <td>男</td> <td>58</td>
    </tr>
    <tr>
        <td>郭富城</td> <td>男</td> <td>51</td>
    </tr>
    <tr>
        <td>黎明</td> <td>男</td> <td>57</td>
    </tr>
</table>
```

##### 表格属性

示例：[03-表格属性](./Basic/day02/example/03-表格属性.html)

==表格属性在实际开发中不常使用，后面都是通过CSS来设置的，这里只做了解。==

- `align`：规定表格相对周围元素的对齐方式，有left、center和right三个属性值。
- `border`：规定表格单元是否拥有边框，默认为""，表示没有边框。
- `cellpadding`：规定单元边沿与其内容之间的空白，默认1像素。
- `cellspacing`：规定单元格之间的空白，默认为2像素。
- `width`：规定表格的宽度。
- `height`：规定表格的高度。

案例：[04-小说排行榜案例](./Basic/day02/example/04-小说排行榜案例.html)

##### 表格结构标签

示例：[05-表格结构标签](./Basic/day02/example/05-表格结构标签.html)

在表格标签中，可以分别用：`<thead></thead>`标签表示表格的头部区域，用`<tbody></tbody>`标签表示表格的主体区域，来更好的分清表格结构。

##### 合并单元格

示例：[06-合并单元格](./Basic/day02/example/06-合并单元格.html)

合并单元格三部曲：

1. 先确定是跨行还是跨列合并；
2. 找到目标单元格，写上合并方式=合并的单元格数量；
3. 删除多余的单元格。

 ###### 跨行合并

使用`rowspan="合并单元格的个数"`来跨行合并单元格，也就是合并一列上的单元格。最上侧单元格为目标单元格，写合并代码。

###### 跨列合并

使用`colspan="合并单元格的个数"`来跨列合并单元格，也就是合并一行上的单元格。最左侧单元格为目标单元格，写合并代码。

#### 列表标签

如果说表格是用来显示数据的，那么列表就是来布局的。

根据使用场景不同，可以将列表分为三大类：无序列表、有序列表和自定义里列表。

##### 无序列表(重点)

示例：[07-无序列表](./Basic/day02/example/07-无序列表.html)

使用`<ul></ul>`标签表示无序列表，用`<li></li>`标签表示列表项。

```html
<ul>
    <li>列表项1</li>
    <li>列表项2</li>
    <li>列表项3</li>
</ul>
```

- 无序列表的各个列表项之间没有顺序级别，是并列的。
- `<ul></ul>`中只能嵌套`<li></li>`，直接在`<ul></ul>`标签中输入其他标签或者文字的做法是不被允许的。
- `<li></li>`之间相当于一个容器，可以容纳所有元素。
- 无序列表会带有自己的样式，但在实际使用中，会使用CSS来设置。

##### 有序列表(理解)

示例：[08-有序列表](./Basic/day02/example/08-有序列表.html)

使用`<ol></ol>`标签表示有序列表，用`<li></li>`标签表示列表项。

```html
<ol>
    <li>列表项1</li>
    <li>列表项2</li>
    <li>列表项3</li>
</ol>
```

- `<ol></ol>`中只能嵌套`<li></li>`，直接在`<ol></ol>`标签中输入其他标签或者文字的做法是不被允许的。
- `<li></li>`之间相当于一个容器，可以容纳所有元素。
- 有序列表会带有自己的样式，但在实际使用中，会使用CSS来设置。

##### 自定义列表(重点)

在HTML标签中，`<dl>`标签用于定义描述列表(或定义列表)，该标签会与`<dt>`(定义项目/名字)和`<dd>`(描述每一个项目/名字)一起使用。

```html
<dl>
    <dt>名词1</dt>
    <dd>名词1解释1</dd>
    <dd>名词1解释2</dd>
</dl>
```

- `<dl></dl>`中只能包含`<dt></dt>`和`<dd></dd>`。
- `<dt></dt>`和`<dd></dd>`的个数没有限制，经常是一个`<dt>`对应多个`<dd>`。

自定义列表常用于下面的场景：

![ScreenCapture2022-09-30 16.38.07](https://cdn.jsdelivr.net/gh/staick/images@master/PicGo/202209301638597.png)

#### 表单标签

在HTML中，一个完整的表单由表单域、表单控件(也称表单元素)和提示信息3个部分构成。

##### 表单域

表单域是一个包含表单元素的区域。在HTML中使用`<form></from>`定义表单域。

`<form>`会把它范围内的表单元素信息提交给服务器。

```html
<form action="url地址" method="提交方式" name="表单域名称">
    各种表单元素控件
</form>
```

- action：用于指定接受并处理表单数据的服务程序的url地址。
- method：用于设置表单数据的提交方式，其取值为get或post。
- name：用于指定表单的名称，以区分同一个页面中的多个表单域。

##### 表单控件(表单元素)

###### input输入表单元素

在表单元素中`<input>`标签用于收集用户信息。

在`<input>`标签中，包含一个type属性，根据不同的type属性值，输入字段拥有很多种形式。

```html
<input type="属性值">
```

- `<input>`标签是一个单标签。
- type属性设置痛的属性值来指定不同的空间类型。

type属性的属性值及其描述如下：

| 属性值   | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| button   | 定义可点击按钮(多数情况下，用于通过JavaScript启动脚本)。     |
| checkbox | 定义复选框。                                                 |
| file     | 定义输入字段和“浏览”按钮，供文件上传。                       |
| hidden   | 定义隐藏的输入字段。                                         |
| image    | 定义图像形式的提交按钮。                                     |
| password | 定义密码字段。该字段中的字符被掩码。                         |
| radio    | 定义单选按钮。                                               |
| reset    | 定义充值按钮，重置按钮会清除表单中的所有数据。               |
| submit   | 定义提交按钮，提交按钮会把表单数据发送到服务器。             |
| text     | 定义单行的输入字段，用户可在其中输入文本，默认宽度为20个字符。 |

radio单选按钮，可以通过指定一样的名字name，实现多选一。

除type属性外，`<input>`标签还有其他很多属性：

- name：由用户自定义，定义input元素的名称。
- value：由用户自定义，规定input元素的值。
- checked：checked，规定此input元素首次加载时应当被选中。
- maxlength：正整数，规定输入字段中的字符的最大长度。

name和value是每个表单元素都有的属性，主要给后台人员使用。

name表单元素的名字，要求单选按钮和复选框要有相同的name值。

###### select下拉表单元素

###### textarea文本域表单元素

## VSCode的使用

示例：[03-vscode创建页面](./Basic/day01/example/03-vscode创建页面.html)

快速生成页面骨架结构：输入`!`按下**Tab**键：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

上述骨架代码新增了一些代码：

1. `<!DOCTYPE>`标签：文档类型的声明标签，告诉浏览器使用哪种HTML版本来显示网页，必须位于文档开头，不属于HTML标签。
2. `lang`语言：定义当前文档显示的语言，`en`为英文，`zh-CN`为中文。但是只是对浏览器起提示作用，可以写其他语言。
3. `charset`字符集：指定编码，如果不写，可能会出现乱码的情况。

### 插件推荐

- `Chinese(simple)Language Pack for VS Code`：安装中文简体。
- `Open in browser`：在浏览器中打开页面。
- `JS-CSS-HTML Formatter`：每次保存，自动格式化js、css和html代码。==不再维护==
- `Auto Rename Tag`：自动重命名背对的HTML/XML标签。
- `CSS Peek`：追踪至样式。

## HTML5新特性

参考文章：[html5新特性总结](https://www.cnblogs.com/binguo666/p/10928907.html)

### 语义标签

|    标签     |               描述               |
| :---------: | :------------------------------: |
| `<header>`  |        定义文档的头部区域        |
| `<footer>`  |        定义文档的尾部区域        |
|   `<nav>`   |          定义文档的导航          |
| `<section>` |          定义文档中的节          |
| `<article>` |             定义文章             |
|  `<aside>`  |        定义页面以外的内容        |
| `<details>` | 定义用户可以看到或隐藏的额外细节 |
| `<summary>` |    标签包含details元素的标题     |
| `<dialog>`  |            定义对话框            |
| `<figure>`  |      定义自包含内容，如图表      |
|  `<main>`   |          定义文档主内容          |
|  `<mark>`   |         定义文档的主内容         |
|  `<time>`   |          定义日期/时间           |

![img](https://cdn.jsdelivr.net/gh/staick/images@master/PicGo/202209292033847.png)

### 增强型表单



### 视频和音频

### Canvas绘图

### SVG绘图

### 地理定位

### 拖放API

可以通过将元素的`draggable`属性设置为`true`来使元素可以拖放：

```html
<div draggable="true">你好，世界！</div>
```

### WebWorker

### WebStorage

### WebSocket

