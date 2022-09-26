# 前端

## 基础知识

### 浏览器

#### 常用浏览器

- IE浏览器
- Firefox浏览器
- Chrome浏览器
- Edge浏览器
- Safari浏览器
- Opera浏览器

#### 浏览器的内核

浏览器内核(渲染引擎)：负责读取网页内容，整理讯息，计算网页的显示方式并显示页面。

| 浏览器       | 内核                  |
| ------------ | --------------------- |
| IE           | Trident               |
| firefox      | Gecko                 |
| Safari       | Webkit                |
| chrome/Opera | Blink（Webkit的分支） |

### Web标准

Web标准主要包括**结构(Structure)**、**表现(Presentation)**和**行为(Behavior)**三个方面。

- **结构**：用于对网页元素进行整理和分类，现阶段主要是HTML；
- **表现**：用于设置网页元素的版式、颜色、大小等外观样式，主要指CSS；
- **行为**：指网页模型的定义及交互的编写，现阶段主要是JavaScript

## HTML

HTML，即Hyper Text Markup Language，文本标记语言。

HTML通常以`.html`作为后缀名，如`index.html`

### 语法规范

#### 基本语法概述

1. HTML标签由尖括号包围的关键词，如`<html>`；
2. HTML标签通常成对出现，如`<html></html>`，这种称为**双标签**，标签中第一个标签是开始标签，第二个是结束标签；
3. 有些特殊的标签必须是单个标签，例如`<br />`，这种称为单标签。

#### 标签关系

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

#### 基本结构标签

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

#### 标签语义

**根据标签的语义，在合适的地方给一个最为合理的标签，可以让页面结构更为清晰。**

#### 常用标签

##### 标题标签

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

##### 段落标签

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

##### 换行标签

示例：[05-段落和换行标签](./Basic/day01/example/05-段落和换行标签.html)

强制换行。

```html
Beautiful is better than ugly. Explicit is better than implicit.<br \> 
```

课堂案例：[06-体育新闻](./Basic/day01/example/06-体育新闻.html)

##### 文本格式化标签

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

##### div和span标签

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

##### 图像标签

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

##### 超链接标签

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

##### 注释标签

示例：[16-注释标签和特殊字符](./Basic/day01/example/16-注释标签和特殊字符.html)

```html
<!-- 这是一条注释标签 -->
```

##### 特殊字符

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

### VSCode的使用

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

#### 插件推荐

- `Chinese(simple)Language Pack for VS Code`：安装中文简体。
- `Open in browser`：在浏览器中打开页面。
- `JS-CSS-HTML Formatter`：每次保存，自动格式化js、css和html代码。==不再维护==
- `Auto Rename Tag`：自动重命名背对的HTML/XML标签。
- `CSS Peek`：追踪至样式。

## JavaScript
