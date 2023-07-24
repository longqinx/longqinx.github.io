[toc]

# HTML5笔记

## HTML元素

### HTML元素类型

- HTML的元素可以放在两种不同的组中

  - **块级**(Block Level)元素
    - 用于构建页面结构
    - **占据可用宽度的100%**
    - 以换行符为分界进行渲染
  - **行内级**(Inline Level)元素
    - 用于块内页面内容的修饰
    - 仅占据其需要的大小

- 块级和行内级的一点小note

  ```html
  //使用块级元素p包裹图像，使得两个图像分在两行显示，即图片的关系是上下排布
  <p><img src="a.jpg"></p>
  <p><img src="b,jpg"></p>
  //不适用块级元素，因img是行内级元素，因此结果是两个图像在同一行，即图片关系是水平排布
  <img src="a.jpg">
  <img src="b,jpg">
  ```

- 常用块级元素

  - div
  - p
  - h1到h6
  - form
  - ol
  - ul
  - li

- 常用行内级元素

  - img
  - a
  - span
  - strong
  - b
  - em
  - i
  - code
  - input
  - button

- 块级元素不应被置于行内级元素中

## HTML属性

### 布尔属性(H5)

- 不同于一般的属性由键值对构成，布尔属性直接由名字构成。

- 常见布尔属性有

  - **checked**
  - **disabled**
  - **readonly**
  - **required**

  ```html
  <p><input type="email" required></p>                 该字段必须有
  <p><input type="submit" value="Submit" disabled></p> 禁用
  <p><input type="checkbox" checked></p>               默认选中
  <p><input type="text" value="Read only text" readonly></p> 只读
  ```

### 通用属性

- 某些能被大多数标签使用的属性。如

  - **id**

  - **class**

  - **title**

    - 用于对标签或是标签的内容进行说明，鼠标悬停时会出现该说明文本

    ```html
    <abbr title="World Wide Web Consortium">W3C</abbr>
    <a href="images/kites.jpg" title="Click to view a larger image">
        <img src="images/kites-thumb.jpg" alt="kites">
    </a>
    ```

  - **style**

## HTML段落

- 换行(Line Break)

  - **\<br>**

- 水平线(Horizontal Rules)

  - **\<hr>**

- 空白符处理

  - 默认HTML将多个连续的直接由键盘输入的空格和换行符当成一个
  - 使用 `&nbsp` 创建连续空格
  - 使用`<br>`创建连续换行符

- 若不想用实体符号创建空格或换行，则可使用以下标签

  - **\<pre>\</pre>**
    - 在HTML展现预格式化好的文本

  ```html
  //用特殊实体符号创建多个空格或换行
  <p>This paragraph has multiple&nbsp;&nbsp;&nbsp;spaces.</p>
  <p>This paragraph has multiple<br><br>line<br><br><br>breaks.</p>
  
  //以下按照其源码内容编排格式，避免上述麻烦
  <pre>
      Twinkle, twinkle, little star, 
      How I wonder what you are! 
      Up above the world so high, 
      Like a diamond in the sky.
  </pre>
  ```

## HTML 链接

- HTML链接可链向网页、媒体文件或本页面的不同位置等

- 通常默认的链接有三种状态
  - 未访问链接通常为蓝色+下划线
  - 访问过的链接为紫色+下划线
  - 活跃的链接为红色+下划线

### 链接使用语法

```html
<a href="https://www.google.com/">Google Search</a>
<a href="https://www.tutorialrepublic.com/">Tutorial Republic</a>
<a href="images/kites.jpg">
    <img src="kites-thumb.jpg" alt="kites">
</a>
```

### Target属性

- target属性告诉浏览器在那里打开链接目标，有以下取值
  - **_blank**
    - 在新窗口或新的标签页打开
  - **_parent**
    - 在父窗口中打开
  - **_self**
    - 默认值。在本标签也中打开
  - **_top**
    - 完整的窗口中打开
    - 若页面被装入**iframe**中，则可设置属性值为_top让页面摆脱frame在完整的窗口中显示

### 创建书签锚点

- 创建书签锚点可以让用户跳转到页面的指定位置

- 一般创建书签锚点的方法为

  - 为要跳转的元素位置加**id**属性
  - 在**\<a>**标签的**href**属性中赋值为**#id**格式

  ```html
  <a href="#sectionA">Jump to Section A</a>
  <h2 id="sectionA">Section A</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit...</p>
  ```

- 可通过此方法跳转到**其他页面的指定位置**

  ```html
  <a href="mypage.html#topicA">Go to TopicA</a>
  ```

### 创建下载链接

- 将链接目标指向文件即可

  ```html
  <a href="downloads/test.zip">Download Zip file</a>
  ```

## HTML 文本格式化

### 格式化文本

- 常用格式化文本标签

  | 标签名              | 作用              |
  | ------------------- | ----------------- |
  | \<b>\</b>           | bold，加粗        |
  | \<i>\</i>           | italic，斜体      |
  | \<mark>\</mark>     | 高亮              |
  | \<code>\</code>     | 代码              |
  | \<ins>\</ins>       | insert，插入线    |
  | \<del>\</del>       | delete，删除线    |
  | \<em>\</em>         | emphasis，强调    |
  | \<strong>\</strong> | 重要文本          |
  | \<small>\</small>   | 小号文本          |
  | \<sub>\</sub>       | subscript，下标   |
  | \<sup>\</sup>       | superscript，上标 |

- 示例

  ```html
  <p>This is <b>bold text</b>.</p>
  <p>This is <strong>strongly important text</strong>.</p>
  <p>This is <i>italic text</i>.</p>
  <p>This is <em>emphasized text</em>.</p>
  <p>This is <mark>highlighted text</mark>.</p>
  <p>This is <code>computer code</code>.</p>
  <p>This is <small>smaller text</small>.</p>
  <p>This is <sub>subscript</sub> and <sup>superscript</sup> text.</p>
  <p>This is <del>deleted text</del>.</p>
  <p>This is <ins>inserted text</ins>.</p>
  ```

- 在浏览器渲染中，strong和b类似，em和 i 类似，但其意义有区别

  - \<strong>和\<b>
    - strong表示其内容有很强的重要性
    - b仅仅是加粗，没有表达重要程度
  - em和 i 类似。**即是否传达某种语义**

### 格式化引用

- 块级引用**\<blockquote>**

  - 块级引用会将被引用的文本进行一些缩进和格式改变，形成一个可以和其他区域区分的引用块

  ```html
  <blockquote>
      <p>Learn from yesterday, live for today, hope for tomorrow. The important thing is not to stop questioning.
      </p>
      <cite>&mdash; Albert Einstein</cite>
  </blockquote>
  ```

  - **\<cite>\<cite>**用于引用的作者、URL或出处信息

- 行内引用**\<q>**

  - 行内引用会将引用的内容自动**用双引号包裹**

  ```html
  <p>According to the World Health Organization (WHO): <q>Health is a state of complete physical, mental, and social well-being.</q></p>
  ```

### 显示缩写

- 标签**\<abbr>**用于显示缩写

  - 其中**title**属性为要进行缩写的目标
  - 标签的内容为描述信息

  ```html
  <p>The <abbr title="World Wide Web Consortium">W3C</abbr> is the main international standards organization for the <abbr title="World Wide Web">WWW or W3</abbr>. It was was founded by Tim Berners-Lee.</p>
  
  //上述World Wide Web 被缩写显示为WWW，鼠标悬停描述信息为 WWW or W3
  ```

### 格式化联系地址

- 标签***\<*address>**用于格式化地址，通常是作者联系方式、街道地址等

- 一般将该标签包裹的内容用斜体的地址块表示

  ```html
  <address>
  Mozilla Foundation<br>
  331 E. Evelyn Avenue<br>
  Mountain View, CA 94041, USA
  </address>
  ```

## HTML 样式

### 三种使用样式的方式

- 行内样式
  - 使用标签的style属性
- 嵌入样式
  - 在head中使用\<style>标签
- 外部样式表
  - 使用\<link>标签引入外部样式表
- 三种方式引入的样式**优先级逐渐降低**

### 两种引用外部样式表的方式

- 使用**\<link>**标签

  - 在head中使用

  ```html
  <head>
      <link rel="stylesheet" href="css/style.css">
  </head>
  ```

- 使用**@import**

  - 在head中的style标签中使用

  ```html
  <style>
      @import url("css/style.css");
      p {
          color: blue;
          font-size: 16px;
      }
  </style>
  ```

  - 在另一个样式表中使用

  ```css
  @import url("css/layout.css");
  @import url("css/color.css");
  body {
      color: blue;
      font-size: 14px;
  }
  ```

## HTML 图像

- 使用img标签可使用图像

### H5中的\<picture>标签

- 此标签可是用户定义多种版本的图像去**适应不同类型的设备**
- 此标签包含零个或多个**\<source>**标签，每个用于指明不同图像的资源。其中的**media**属性用于指明媒体环境类型
- 此标签在最后包含一个\<img>标签

```html
<picture>
    <source media="(min-width: 1000px)" srcset="logo-large.png">
    <source media="(max-width: 500px)" srcset="logo-small.png">
    <img src="logo-default.png" alt="My logo">
</picture>

//浏览器会自动适配每个source标签，寻找最合适的进行匹配。若全都匹配失败则展示img标签中的图像
```

### 图像映射

- 图像映射可以让开发者定义图像的**交互热点**，其表现类似超链接

  ```html
  <img src="objects.png" usemap="#objects" alt="Objects">
  <map name="objects">
      <area shape="circle" coords="137,231,71" href="clock.html" alt="Clock">
      <area shape="poly" coords="363,146,273,302,452,300" href="sign.html" alt="Sign">
      <area shape="rect" coords="520,160,641,302" href="book.html" alt="Book">
  </map>
  ```

- 上述代码中img使用**usemap**属性指明图像使用的映射关系

- map标签声明一个映射关系，属性name指定其引用名。其中的area标签用于定义一个可点击区域

- area中

  - shape属性定义区域形状
  - coords定义形状的一些参数

## HTML表格

### 创建表格

- table标签用于创建表格，内部：

  - tr(table row)：用于创建行
  - td(table data)：创建数据单元格(列)
  - th(table header)：创建表头

- 示例

  ```html
  <table>
      <tr>
          <th>No.</th>
          <th>Name</th>
          <th>Age</th>
      </tr>
      <tr>
          <td>1</td>
          <td>Peter Parker</td>
          <td>16</td>
      </tr>
      <tr>
          <td>2</td>
          <td>Clark Kent</td>
          <td>34</td>
      </tr>
  </table>
  ```

- 默认表格没有边框，需要指定css的border属性

- 默认表格大小适应内容，可用css的padding属性调整

- 默认表格的各单元格的边框是分开的(视觉上是两根线)，需调整table的border-collapse属性为collapse让边框合并

### 跨行跨列

- 类似于Excel表格中的合并

  - **rowspan**属性设置跨行数量
  - **colspan**属性设置跨列数量

- 示例

  ```html
  <table>
      <tr>
          <th>Name</th>
          <th colspan="2">Phone</th> //跨两列
      </tr>
      <tr>
          <td>John Carter</td>
          <td>5550192</td>
          <td>5550152</td>
      </tr>
  </table>
  ```

### 添加标题

- 使用**\<caption>**标签为表格添加标题

- 此标签必须被放置在table起始标签之后的第一个位置

- 默认标题出现在表格的上边，可以修改css的caption-side修改标题位置

- 示例

  ```html
  <table>
      <caption>Users Info</caption>
      <tr>
          <th>No.</th>
          <th>Name</th>
          <th>Age</th>
      </tr>
      <tr>
          <td>1</td>
          <td>Peter Parker</td>
          <td>16</td>
      </tr>
      <tr>
          <td>2</td>
          <td>Clark Kent</td>
          <td>34</td>
      </tr>
  </table>
  ```

### 定义表头、表体、表尾

- thead定义表头

- tbody定义表体

- tfoot定义表尾

- 示例

  ```html
  <table>
      <thead>
          <tr>
              <th>Items</th>
              <th>Expenditure</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td>Stationary</td>
              <td>2,000</td>
          </tr>
          <tr>
              <td>Furniture</td>
              <td>10,000</td>
          </tr>        
      </tbody>
      <tfoot>
          <tr>
              <th>Total</th>
              <td>12,000</td>
          </tr>
      </tfoot>
  </table>
  ```

- 不建议使用表格进行布局

## HTML列表

### 列表类型

- 无序列表(Unordered List)
- 有序列表(Ordered List)
- 描述列表(Description List)
  - 用于创建列表项及其描述

### 无序列表

- 使用**ul (unordered list)**标签创建无序列表，内部使用  **li**  标签创建列表项

  ```html
  <ul>
      <li>Chocolate Cake</li>
      <li>Black Forest Cake</li>
      <li>Pineapple Cake</li>
  </ul>
  ```

- 可通过css的list-style-type更改每个项目前的符号

### 有序列表

- 使用**ol (ordered list)**标签创建有序列表，内部用  **li** 创建列表项

  ```html
  <ol>
      <li>Fasten your seatbelt</li>
      <li>Starts the car's engine</li>
      <li>Look around and go</li>
  </ol>
  ```

- 默认列表从 1 开始计数，可通过 start 属性更改起始序号

  ```html
  <ol start="10">
      <li>Mix ingredients</li>
      <li>Bake in oven for an hour</li>
      <li>Allow to stand for ten minutes</li>
  </ol>
  ```

- 同样可是哟个list-style-type指定项目符号样式

### 描述列表

- 使用**dl (description list)**标签创建描述列表，内部用   **dt (term)** 指明项目，用**dd (description) ** 指明项目的定义或描述

  ```html
  <dl>
      <dt>Bread</dt>
      <dd>A baked food made of flour.</dd>
      <dt>Coffee</dt>
      <dd>A drink made from roasted coffee beans.</dd>
  </dl>
  ```

- 浏览器默认将项目和描述分行显示，描述（定义）通常有缩进

## HTML 表单

### input标签

- input标签是表单中最常用的。可通过**type**指定输入控件类型，有

  - text
  - password
  - checkbox
  - radio
  - submit
  - file
  - reset
  - 等

- 示例

  ```html
  //行内文本
  <form>
      <label for="username">Username:</label>
      <input type="text" name="username" id="username">
  </form>
  
  //单选
  <form>
      <input type="radio" name="gender" id="male">
      <label for="male">Male</label>
      <input type="radio" name="gender" id="female">
      <label for="female">Female</label>
  </form>
  
  //复选
  <form>
      <input type="checkbox" name="sports" id="soccer">
      <label for="soccer">Soccer</label>
      <input type="checkbox" name="sports" id="cricket">
      <label for="cricket">Cricket</label>
      <input type="checkbox" name="sports" id="baseball">
      <label for="baseball">Baseball</label>
  </form>
  //单选和复选可通过在属性中添加布尔属性  checked  默认勾选，如
  <input type="checkbox" checked>
  
  //文件选择
  <form>
      <label for="file-select">Upload:</label>
      <input type="file" name="upload" id="file-select">
  </form>
  ```

### textarea标签

- 此标签允许用户输入多行文本

  ```html
  <form>
      <label for="address">Address:</label>
      <textarea rows="3" cols="30" name="address" id="address"></textarea>
  </form>
  ```

### 下拉列表

- 示例

  ```html
  <form>
      <label for="city">City:</label>
      <select name="city" id="city">
          <option value="sydney">Sydney</option>
          <option value="melbourne">Melbourne</option>
          <option value="cromwell">Cromwell</option>
      </select>
  </form>
  ```

### 提交(submit)和重置(reset)按钮

- 通过指定input标签的属性为submit得到提交按钮

- 通过指定属性为reset得到重置按钮

- 提交按钮被点击后，表单的数据会被提交给form标签的action属性指定的页面(服务器)处理

- 重置点击后会重置表单中的所有控件

  ```html
  <form action="action.php" method="post">
      <label for="first-name">First Name:</label>
      <input type="text" name="first-name" id="first-name">
      <input type="submit" value="Submit">
      <input type="reset" value="Reset">
  </form>
  ```

- NOTE：

  - 可使用button 标签创建按钮，其功能同input创建的按钮，但可以提供更加丰富的个性化方式

### 控件分组fieldset

- 可通过fieldset标签和legend标签对表单中的控件进行分组，同一个组的控件将会被一个区域围起来便于区分

- 其中legend标签指定分组名

- 示例

  ```html
  <form>
      <fieldset>
          <legend>Contact Details</legend>
          <label>Email Address: <input type="email" name="email"></label>
          <label>Phone Number: <input type="text" name="phone"></label>
      </fieldset>
  </form>
  ```

### 常用form表单的属性

| 属性名  | 描述                                                |
| ------- | --------------------------------------------------- |
| name    | 指明表单名。在同一个文档的表单中必须是唯一的        |
| action  | 指明服务器端的程序或脚本URL，用于处理表单提交的数据 |
| method  | post或get，指明提交请求方式                         |
| target  | 同\<a>标签的target                                  |
| enctype | 指明数据如何被编码。当method为post时有用            |

## iframe

### 简介

- **iframe  (inline frame)**用于在一个web页面中显示外部对象，如其他web页面

- 其工作方式类似在一个web页面中嵌套了一个新的浏览器页面

- 基本使用语法

  ```html
  <iframe src="URL"></iframe>
  ```

### 移除边框

- 默认iframe是带有边框的，可通过css属性border去掉边框

  ```html
  <iframe src="hello.html" style="border: none;"></iframe>
  ```

### 将iframe作为链接对象(target)

- iframe可作为超链接的对象，即target属性指定的对象

- 当指定iframe的name属性后，可以在其他 a 标签的target属性中指定为iframe的name，此时点击超链接会在该iframe中打开

  ```html
  <iframe src="demo-page.html" name="myFrame"></iframe>
  <p><a href="https://www.tutorialrepublic.com" target="myFrame">Open TutorialRepublic.com</a></p>
  ```

## HTML布局

### 表格布局

- 不建议使用此布局方式，因为此布局方式渲染速度比较慢

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>HTML Table Layout</title>
</head>
<body style="margin:0px;">
    <table style="width:100%; border-collapse:collapse; font:14px Arial,sans-serif;">
        <tr>
            <td colspan="2" style="padding:10px 20px; background-color:#acb3b9;">
                <h1 style="font-size:24px;">Tutorial Republic</h1>
            </td>
        </tr>
        <tr style="height:170px;">
            <td style="width:20%; padding:20px; background-color:#d4d7dc; vertical-align: top;">
                <ul style="list-style:none; padding:0px; line-height:24px;">
                    <li><a href="#" style="color:#333;">Home</a></li>
                    <li><a href="#" style="color:#333;">About</a></li>
                    <li><a href="#" style="color:#333;">Contact</a></li>
                </ul>
            </td>
            <td style="padding:20px; background-color:#f2f2f2; vertical-align:top;">
                <h2>Welcome to our site</h2>
                <p>Here you will learn how to create websites...</p>
            </td>
        </tr>
        <tr>
            <td colspan="2" style="padding:5px; background-color:#acb3b9; text-align:center;">
                <p>copyright &copy; tutorialrepublic.com</p>
            </td>
        </tr>
    </table>
</body>
</html>
```

### 基于div标签的布局

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>HTML Div Layout</title>
<style>
    body {
        font: 14px Arial,sans-serif; 
        margin: 0px;
    }
    .header {
        padding: 10px 20px;
        background: #acb3b9; 
    }
    .header h1 {
        font-size: 24px;
    }
    .container {
        width: 100%;
        background: #f2f2f2; 
    }
    .nav, .section {
        float: left; 
        padding: 20px;
        min-height: 170px;
        box-sizing: border-box;
    }
    .nav {            
        width: 20%;             
        background: #d4d7dc;
    }
    .section {
        width: 80%;
    }
    .nav ul {
        list-style: none; 
        line-height: 24px;
        padding: 0px; 
    }
    .nav ul li a {
        color: #333;
    }    
    .clearfix:after {
        content: ".";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
    .footer {
        background: #acb3b9;            
        text-align: center;
        padding: 5px;
    }
</style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Tutorial Republic</h1>
        </div>
        <div class="wrapper clearfix">
            <div class="nav">
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </div>
            <div class="section">
                <h2>Welcome to our site</h2>
                <p>Here you will learn how to create websites...</p>
            </div>
        </div>
        <div class="footer">
            <p>copyright &copy; tutorialrepublic.com</p>
        </div>
    </div>
</body>
</html>
```

### 使用H5的结构元素布局

- H5引入的新的结构化元素

  | 标签    | 描述                           |
  | ------- | ------------------------------ |
  | header  | 文档或章节(section)标头        |
  | footer  | 文档或章节尾                   |
  | nav     | navigation，导航栏             |
  | section | 文档中的章节，如header、footer |
  | article | 文章、博客或其他自包含的内容   |
  | aside   | 与页面松散相关的内容           |

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>HTML5 Web Page Layout</title>
<style>
    body {
        font: 14px Arial,sans-serif; 
        margin: 0px;
    }
    header {
        padding: 10px 20px;
        background: #acb3b9; 
    }
    header h1 {
        font-size: 24px;
    }
    .container {
        width: 100%;
        background: #f2f2f2;  
    }
    nav, section {
        float: left; 
        padding: 20px;
        min-height: 170px;
        box-sizing: border-box;
    }
    section {
        width: 80%;
    }
    nav {
        width: 20%;             
        background: #d4d7dc;
    }    
    nav ul {
        list-style: none; 
        line-height: 24px;
        padding: 0px; 
    }
    nav ul li a {
        color: #333;
    }
    .clearfix:after {
        content: ".";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
    footer {
        background: #acb3b9;            
        text-align: center;
        padding: 5px;
    }
</style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Tutorial Republic</h1>
        </header>
        <div class="wrapper clearfix">
            <nav>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>
            <section>
                <h2>Welcome to our site</h2>
                <p>Here you will learn how to create websites...</p>
            </section>
        </div>
        <footer>
            <p>copyright &copy; tutorialrepublic.com</p>
        </footer>
    </div>
</body>
</html>
```

## HTML head标签

### head标签中可使用的元素

- title

- meta

- base

- link

  ```html
  <head>
      <title>Linking Style Sheets</title>
      <link rel="stylesheet" href="style.css">
  </head>
  ```

- style

- script

- noscript

### base标签

- 用于定义整个文档中的相对URL的基本URL，即相对链接的前缀部分

- 示例

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <title>Defining a base URL</title>
      <base href="https://www.tutorialrepublic.com/">
  </head>
  <body>
      <p><a href="html-tutorial/html-head.php">HTML Head</a>.</p>
  </body>
  </html>
  
  //上述a标签实际请求的路径为https://www.tutorialrepublic.com/html-tutorial/html-head.php
  ```

## HTML Meta (元数据)

### 声明字符编码

- 省略此属性时默认使用平台的编码方式

  ```html
  <head>
      <title>Declaring Character Encoding</title> 
      <meta charset="utf-8">
  </head>
  ```

### 定义文档作者

- 示例

  ```html
  <head>
      <title>Defining Document's Author</title>
      <meta name="author" content="Alexander Howick">
  </head>
  ```

### 面向搜索引擎的关键词或描述

- 搜索引擎通常使用元数据meta生成对一个网页的简短描述

  ```html
  <head>
      <title>Defining Keywords and Description</title>  
      <meta name="keywords" content="HTML, CSS, javaScript">
      <meta name="description" content="Easy to understand tutorials and references on HTML, CSS, javaScript and more..."> 
  </head>
  ```

### 配置移动设备的视图

- viewport元数据标签可让移动设备正确地渲染网页内容

- 不指定此标签时默认采用桌面网页的方式渲染，因此可能会出现大小、排版混乱的情况

- viewport可设置移动设备访问网页时的最佳视图大小和缩放限制

  ```html
  <head>
      <title>Configuring the Viewport</title> 
      <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
  
  //上述width属性指定视图宽度和设备的宽度一样，initial-scale=1指定默认缩放比例为100%
  ```

## HTML Script

- **最好将\<script>标签放在文档最后**，即body的闭标签之前。因为浏览器在遇到脚本后会停止渲染剩余页面，转而解析脚本，等到脚本解析完毕后再渲染页面，因此可能导致性能问题

### noscript标签

- 当用户浏览器禁用JS或这不支持JS的时候，此标签一种可代替的信息来表示。类似于img标签中的alt属性

## HTML实体(Entities)

- 某些符号被HTML保留。如`>`、`<`等，并且有些符号不能在键盘上直接打出，如版权标志©

- HTML字符实体(简称实体)即用于在文档中表达上述字符

- 如常用字符实体有

  | 字符 | 描述                 | 实体名   | 数字引用 |
  | :--: | :------------------- | :------- | :------- |
  |      | non-breaking space   | \&nbsp;  | \&#160;  |
  |  <   | less than            | \&lt;    | \&#60;   |
  |  >   | greater than         | \&gt;    | \&#62;   |
  |  &   | ampersand            | \&amp;   | \&#38;   |
  |  "   | quotation mark       | \&quot;  | \&#34;   |
  |  '   | apostrophe           | \&apos;  | \&#39;   |
  |  ¢   | cent                 | \&cent;  | \&#162;  |
  |  £   | pound                | \&pound; | \&#163;  |
  |  ¥   | yen                  | \&yen;   | \&#165;  |
  |  €   | euro                 | \&euro;  | \&#8364; |
  |  ©   | copyright            | \&copy;  | \&#169;  |
  |  ®   | registered trademark | \&reg;   | \&#174;  |
  |  ™   | trademark            | \&trade; | \&#8482; |

## HTML URL

- URL语法

  ```html
  scheme://host:port/path?query-string#fragment-id
  ```

- scheme

  - 访问资源的协议名称，常用`http`、`https`、`ftp`、`mailto`

- host

  - 分配给主机的域名。决定资源的位置

- port

  - 端口号。服务器端通常提供多个服务，端口号用于告诉服务器用户请求的是何种服务

- path

  - 具体资源位置

- query-string

  - 传送给服务器端脚本的数据。其前边有`?`表示，通常为等号分隔的键值对表示。每个键值对中间使用`&`分割

  - 如

    ```html
    ?first_name=John&last_name=Corner
    
    q=mobile+phone
    ```

- fragment-id

  - 片段标识符。由`#`标识，其作用是定位到当前页面的某一个部分，类似a标签的书签

### URL编码

- 类似实体，某些符号是被URL保留的，如`/`分隔符，如果在不恰当的位置使用会引起歧义

- 同时，有一些编码的符号不在未保留的字符中，但其编码方式也不符合URL编码

- 解决方式，即对**不在未保留字符集中**的字符进行**百分号编码**，格式为

  ```html
  %HH
  其中%为标识符，HH为该字符的十六进制编码
  如 François
  编码后为 Fran%C3%A7ois
  ```

- 保留字符表

  | `!`   | `#`   | `$`   | `&`   | `'`   | `(`   | `)`   | `*`   | `+`   | `,`   | `/`   | `:`   | `;`   | `=`   | `?`   | `@`   | `[`   | `]`   |
  | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
  | `%21` | `%23` | `%24` | `%26` | `%27` | `%28` | `%29` | `%2A` | `%2B` | `%2C` | `%2F` | `%3A` | `%3B` | `%3D` | `%3F` | `%40` | `%5B` | `%5D` |

- 非保留字符表

  | `A`  | `B`  | `C`  | `D`  | `E`  | `F`  | `G`  | `H`  | `I`  | `J`  | `K`  | `L`  | `M`  | `N`  | `O`  | `P`  | `Q`  | `R`  | `S`  | `T`  | `U`  | `V`  | `W`  | `X`  | `Y`  | `Z`  |
  | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
  | `a`  | `b`  | `c`  | `d`  | `e`  | `f`  | `g`  | `h`  | `i`  | `j`  | `k`  | `l`  | `m`  | `n`  | `o`  | `p`  | `q`  | `r`  | `s`  | `t`  | `u`  | `v`  | `w`  | `x`  | `y`  | `z`  |
  | `0`  | `1`  | `2`  | `3`  | `4`  | `5`  | `6`  | `7`  | `8`  | `9`  | `-`  | `_`  | `.`  | `~`  |      |      |      |      |      |      |      |      |      |      |      |      |

## HTML5特性

### 新的输入类型

#### color

```html
<form>
    <label for="mycolor">Select Color:</label>
    <input type="color" value="#00ff00" id="mycolor">
</form>
```

- 当选中颜色时，会将选中颜色**值返回给value属性**。格式为`#rrggbb`默认为黑色

#### date

```html
<form>
    <label for="mydate">Select Date:</label>
    <input type="date" value="2019-04-15" id="mydate">
</form>
```

- 下拉日历的日期输入。包含年月日。返回结果格式为`yyyy-mm-dd`

#### datetime-local

```html
<form>
    <label for="mydatetime">Choose Date and Time:</label>
    <input type="datetime-local" id="mydatetime">
</form>
```

- 允许选择本地时间的**年月日**和时间的**时和分**

#### email

```html
<style>
    //伪元素
    input[type="email"]:valid{
        outline: 2px solid green;
    }
    input[type="email"]:invalid{
        outline: 2px solid red;
    }
</style>
<script>
    function getValue() {
        var email = document.getElementById("myemail").value;
        alert(email);
    }
</script>
</head>
<body>
    <form>
        <label for="myemail">Enter Email Address:</label>
        <input type="email" id="myemail" required>
        <button type="button" onclick="getValue();">Get Value</button>
    </form>
</body>
```

- 用于输入电子邮件地址，类似text文本框，用了required属性时浏览器会检查格式确保输入正确

#### month

```html
<form>
    <label for="mymonth">Select Month:</label>
    <input type="month" id="mymonth">
</form>
```

- 用于输入年月

#### number

```html
<form>
    <label for="mynumber">Enter a Number:</label>
    <input type="number" min="1" max="10" step="0.5" id="mynumber">
</form>
```

- 用于输入数字。min指定最小值，max指定最大值，step指定min、max步长，上述表示只能输入1 1.5 2 2.5 等数
- PS：可使用CSS的伪元素进行状态判断，同email

#### range

```html
<form>
    <label for="mynumber">Select a Number:</label>
    <input type="range" min="1" max="10" step="0.5" id="mynumber">    
</form>
```

- 类似number，但提供了一个更简单的输入方式，即**滑动条**

#### search

```html
<form>
    <label for="mysearch">Search Website:</label>
    <input type="search" id="mysearch">
</form>
```

- 提供搜索输入框

#### tel

```html
<form>
    <label for="myphone">Telephone Number:</label>
    <input type="tel" id="myphone" placeholder="xx-xxxx-xxxx" required>
</form>
```

- 输入电话号码。但浏览器本身不带有号码校验功能。可使用input的pattern属性指定正则表达式校验

#### time

```html
<form>
    <label for="mytime">Select Time:</label>
    <input type="time" id="mytime">
</form>
```

- 用于输入时间，包含时和分。12或24小时制取决于系统

#### url

```html
<form>
    <label for="myurl">Enter Website URL:</label>
    <input type="url" id="myurl" required>
</form>
```

- 可用于输入URL或Web地址。可用required属性指定校验并用css伪元素改变状态
- 可用multiple属性使得可以输入不止一个URL

#### week

```html
<form>
    <label for="myweek">Select Week:</label>
    <input type="week" id="myweek">
</form>
```

- 下拉选择年份和周

### Canvas(画布)

- 简述

  - \<canvas>元素可用于使用Javascript在网页上绘制图形
  - 默认canvas宽为300px，高为150px且无边界和内容
  - 可使用width和height指定宽高，用border指定边框属性
  - canvas使用的坐标系和屏幕坐标系类似，以其矩形区域左上角为原点，横向为x，纵向为y

- **canvas基本结构**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="utf-8">
  <title>Drawing on Canvas</title>
  <script>
      //匿名函数，与onload事件绑定，在页面加载成功后执行
      window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          //定义canvas环境(上下文)，类型为2d
          var context = canvas.getContext("2d");
          // draw stuff here
      };
  </script>
  </head>
  <body>
      <canvas id="myCanvas" width="300" height="200"></canvas>
  </body>
  </html>
  ```

- **绘制直线**

  - **moveTo()**
    - 定义绘制起点光标位置
  - **lineTo()**
    - 定义绘制结束点位置
  - **stroke()**
    - 使直线可见

  ```html
  <script>
      window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.moveTo(50, 150);
          context.lineTo(250, 50);
          context.stroke();
      };
  </script>
  ```

- **绘制弧线(圆弧)**

  - **arc()**

  ```javascript
  context.arc(centerX, centerY, radius, startingAngle, endingAngle, counterclockwise);
  //参数说明
  中心点坐标 半径 起始角度 结束角度 是否逆时针(同样的起始角度和结束角度，顺逆时针得到的弧互补)
  ```

  ```html
  <script>
      window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.arc(150, 150, 80, 1.2 * Math.PI, 1.8 * Math.PI, false);
          context.stroke();
      };
  </script>
  ```

- **绘制矩形**

  - **rect()**

  ```javascript
  context.rect(x, y, width, height);
  ```

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.rect(50, 50, 200, 100); 
          context.stroke();
      };
  </script>
  ```

- **圆形绘制**

  - 无专门绘制圆形的函数，同绘制闭合弧线实现绘制圆的效果

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.arc(150, 100, 70, 0, 2 * Math.PI, false);
          context.stroke();
      };
  </script>
  ```

- **在描边上应用样式和颜色**

  - 默认描边为1px黑色，可使用`strokeStyle`和`lineWidth`属性设置相应值

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.lineWidth = 5;
          context.strokeStyle = "orange";
          context.moveTo(50, 150);
          context.lineTo(250, 50);
          context.stroke();
      };
  </script>
  ```

  - 可通过`lineCap`属性设置线条两端的封口样式，可取
    - butt
    - round
    - square

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.lineWidth = 10;
          context.strokeStyle = "orange";
          context.lineCap = "round";
          context.arc(150, 150, 80, 1.2 * Math.PI, 1.8 * Math.PI, false);
          context.stroke();
      };
  </script>
  ```

- **为形状填充颜色**

  - **fillStyle属性**
  - **fill()**
  - 建议将fill()置于stroke()之前

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.rect(50, 50, 200, 100); 
          context.fillStyle = "#FB8B89";
          context.fill();
          context.lineWidth = 5;
          context.strokeStyle = "black";
          context.stroke();
      };
  </script>
  ```

- **为形状填充渐变色**

  - 线性渐变

  ```javascript
  var grd = context.createLinearGradient(startX, startY, endX, endY);
  ```

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.rect(50, 50, 200, 100); 
          var grd = context.createLinearGradient(0, 0, canvas.width, canvas.height);
          //添加颜色
          grd.addColorStop(0, '#8ED6FF');   
          grd.addColorStop(1, '#004CB3');
          context.fillStyle = grd;
          context.fill();
          context.stroke();
      };
  </script>
  ```

  - 径向渐变

  ```javascript
  var grd = context.createRadialGradient(startX, startY, startRadius, endX, endY, endRadius);
  ```

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.arc(150, 100, 70, 0, 2 * Math.PI, false);
          var grd = context.createRadialGradient(150, 100, 10, 160, 110, 100);
          grd.addColorStop(0, '#8ED6FF');   
          grd.addColorStop(1, '#004CB3');
          context.fillStyle = grd;
          context.fill();
          context.stroke();
      };
  </script>
  ```

- **绘制文本**

  - **fillText()填充文字**

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          //指定字体信息
          context.font = "bold 32px Arial";
          //对齐方式
          context.textAlign = "center";
          //文本基线
          context.textBaseline = "middle";
          //颜色
          context.fillStyle = "orange";
          //绘制
          context.fillText("Hello World!", 150, 100);
      };
  </script>
  ```

  - **strokeText()文字描边**

  ```html
  <script>
  	window.onload = function() {
          var canvas = document.getElementById("myCanvas");
          var context = canvas.getContext("2d");
          context.font = "bold 32px Arial";
          context.textAlign = "center";
          context.textBaseline = "middle";
          context.strokeStyle = "orange";
          //描边
          context.strokeText("Hello World!", 150, 100);
      };
  </script>
  ```

### SVG(可缩放矢量图)

- 简述

  - SVG(scalable vector graphics)，是一种基于XML的图像格式，用于在Web中创建基于二维向量的图形
  - 不同于光栅图像(.png、.jpg等)，SVG可实现任意缩放不损失精度
  - SVG是使用一系列遵循XML模式的语句进行绘制的，即SVG可用文本编辑器创建
  - 优势
    - SVG可被搜索、索引、编写脚本、压缩
    - 可用Javascript实时创建和修改
    - 可被高质量打印
    - 可用内建的动画元素对其内容进行动画设计
    - 可包含指向其他文档的超链接

- **在HTML中嵌入SVG**

  - \<svg>元素

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="utf-8">
      <title>Embedding SVG in HTML</title>
  </head>
  <body>
      <svg width="300" height="200">
          <text x="10" y="20" style="font-size:14px;">
              Your browser support SVG.
          </text>
          Sorry, your browser does not support SVG.
      </svg>
  </body>
  </html>
  ```

- **绘制直线**

  - \<line>元素

  ```html
  <svg width="300" height="200">
      <line x1="50" y1="50" x2="250" y2="150" style="stroke:red; stroke-width:3;" />
  </svg>
  ```

- **绘制矩形**

  - \<rect>元素

  ```html
  <svg width="300" height="200">
      <rect x="50" y="50" width="200" height="100" style="fill:orange; stroke:black; stroke-width:3;" />
  </svg>
  ```

- **绘制圆**

  - \<circle>元素

  ```html
  <svg width="300" height="200">
      <circle cx="150" cy="100" r="70" style="fill:lime; stroke:black; stroke-width:3;" />
  </svg>
  ```

- **绘制文本**

  - \<text>元素
  - x、y指定相对于SVG画布左上角位置，dx、dy定义相对位置

  ```html
  <svg width="300" height="200">
      <text x="20" y="30" style="fill:purple; font-size:22px;">
          Welcome to Our Website!
      </text>
      <text x="20" y="30" dx="0" dy="20" style="fill:navy; font-size:14px;">
          Here you will find lots of useful information.
      </text>
  </svg>
  ```

  - 可在text元素中使用`<tspan>`来重新格式化其中的文本，类似于分块处理。这样做的好处是可以对同一块区域的文本进行不同格式设置，但不影响其整体性，如此可以一次性选择该区域内的所有文本

  ```html
  <svg width="300" height="200">
      <text x="30" y="15" style="fill:purple; font-size:22px; transform:rotate(30deg);">
          <tspan style="fill:purple; font-size:22px;">
              Welcome to Our Website!
          </tspan>
          <tspan dx="-230" dy="20" style="fill:navy; font-size:14px;">
              Here you will find lots of useful information.
          </tspan>
      </text>
  </svg>
  ```

- **SVG和canvas区别**

  | SVG                                                | Canvas                                             |
  | :------------------------------------------------- | :------------------------------------------------- |
  | 基于向量，由形状组成                               | 基于光栅，由像素组成                               |
  | 多个图形元素，为页面DOM树的一部分                  | 单个元素，类似\<img>，canvas可被保存为png或jpg图像 |
  | 可用脚本或CSS更改                                  | 仅能通过脚本修改                                   |
  | 良好的文字渲染能力                                 | 较差的文字渲染能力                                 |
  | 使用更少的对象或更大的表平面提供良好性能           | 使用更多的对象或较小的平面提供良好的性能           |
  | 更好的缩放性，可高质量打印，不存在因像素引起的问题 | 较差的缩放性，不适合高质量打印                     |

### Audio(音频)

- **使用HTML5\<audio>元素**

  - 使用浏览器默认控件

  ```html
  <audio controls="controls" src="media/birds.mp3">
      Your browser does not support the HTML5 Audio element.
  </audio>
  ```

  - 使用浏览器默认控件，但音频资源是可替换的(适应不同浏览器)
    - ogg格式用于火狐、谷歌、欧朋等浏览器，而MP3用于IE等浏览器

  ```html
  <audio controls="controls">
      <source src="media/birds.mp3" type="audio/mpeg">
      <source src="media/birds.ogg" type="audio/ogg">
      Your browser does not support the HTML5 Audio element.
  </audio>
  ```

- **链接音频文件**

  - 使用超链接链接到音频文件可实现播放音频的功能

  ```html
  <a href="media/sea.mp3">Track 1</a>
  <a href="media/wind.mp3">Track 2</a>
  ```

- **使用\<object>元素**

  - object元素用于在HTML页面中嵌入各种不同的媒体文件
  - 最初用于嵌入ActiveX控件，但其可用于如音频、视频、PDF、flash动画、图片等嵌入
  - 并非被广泛支持

  ```html
  <object data="media/sea.mp3"></object>
  <object data="media/sea.ogg"></object>
  ```

- **使用\<embed>元素**

  - embed元素用于在HTML中嵌入多媒体内容
  - 注意：此元素虽然被广泛支持，且是HTML5中的标准定义，但可能因为浏览器不支持音频格式或缺少插件而不能播放

  ```html
  <embed src="media/wind.mp3">
  <embed src="media/wind.ogg">
  ```

### Video(视频)

- **使用HTML5\<video>元素**

  - 类似audio元素

  ```html
  <video controls="controls" src="media/shuttle.mp4">
      Your browser does not support the HTML5 Video element.
  </video>
  ```

- **使用\<object>元素**

  - 见audio

- **使用\<embed>元素**

  - 见audio

### Web Storage(数据存储)

- 简述

  - H5的web storage允许在用户本地计算机上存储数据
  - 类似cookie，但是速度上快于cookie且相比cookie更好。但安全性比cookie差
  - 用web storage存储的数据不会发送到服务器，而cookie存储的数据在每次请求时都会发送到服务器
  - cookie允许存储约4KB的信息，而web storage允许存储最多5M的信息
  - 根据作用域和生命周期划分的两种类型
    - **Local storage**：使用`localStorage`对象**永久**地存储网站数据，直到移除
    - **Session storage**：使用`sessionStorage`对象临时存储网站数据，当一个session结束(用户关闭浏览器或标签页)时数据被清除

- **localStorage对象**

  - 每条数据用**键值对**形式存储
  - 主要方法
    - **localStorage.setItem(key,value)**：通过键值对存储数据
    - **localStorage.getItem(key)**：通过键获取数据
    - **localStorage.removeItem(key)**：通过键移除数据
    - **localStorage.clear()**：清除所有数据
  - **注意：**不同浏览器存储的数据不通用

  ```html
  <script>
  // Check if the localStorage object exists
  if(localStorage) {
      // Store data
      localStorage.setItem("first_name", "Peter");
      
      // Retrieve data
      alert("Hi, " + localStorage.getItem("first_name"));
  } else {
      alert("Sorry, your browser do not support local storage.");
  }
  </script>
  ```

- **sessionStorage对象**

  - 除了生命周期和作用域外，其他和localStorage一样

### Application Cache(应用缓存)

- 简述

  - 多数基于web的应用只能联网使用，H5的应用缓存机制允许离线访问网面
  - 优点
    - 离线浏览
    - 提高性能
    - 减少HTTP请求，节省带宽

- **创建缓存清单文件**

  - 缓存清单用于告诉浏览器缓存哪些文件
  - 总是以  **CACHE MANIFEST**  开头

  ```
  CACHE MANIFEST
  # v1.0 : 10-08-2014
   
  CACHE:
  # pages
  index.html
   
  # styles & scripts
  css/theme.css
  js/jquery.min.js
  js/default.js
   
  # images
  /favicon.ico
  images/logo.png
   
  NETWORK:
  login.php
   
  FALLBACK:
  / /offline.html
  ```

  - 清单文件可含有三个不同部分：**CACHE、NETWORK、FALLBACK**
  - CACHE部分定义的文件列表在其第一次下载后被显示缓存
  - NETWORK部分定义的文件只能在联网时访问，不会被缓存
  - FALLBACK部分定义了浏览器不能建立与服务器的连接时使用的备用页面。此部分每条项目都指定两个URI，第一个表示主资源，第二个表示备用资源。如上述文件中，当用户离线时会显示`offline.html`
  - 使用`#`开头的为注释

- **使用缓存清单文件**

  - 需要服务器端提供MIME类型为`text/cache-manifest`的清单文件
  - 在\<html>标签中用**manifest**属性使用清单文件

  ```html
  <!DOCTYPE html>
  <html lang="en" manifest="example.appcache">
  <head>
      <title>Using the Application Cache</title>
  </head>
  <body>
      <!--The document content will be inserted here-->
  </body>
  </html>
  ```

### Web Worker(后台处理、多线程技术)

- 简述

  - 使用Javascript处理需要耗费时间和计算力密集型任务时，浏览器页面可能没有响应直到任务完成，因为Javascript总是在前台运行
  - web worker是H5引入的特性，也被称作工作线程、后台异步化。用于独立的后台处理，不影响前台的响应
  - Web worker不能访问DOM，即在需要使用web worker的JS代码中不能访问DOM

- **创建使用Web Worker的文件**

  - worker.js

  ```js
  var i = 0;
  function countNumbers() {
      if(i < 100000) {
          i = i + 1;
          //web worker的postMessage()方法用于发送信息到页面
          postMessage(i);
      }
   
      // Wait for sometime before running this script again
      setTimeout("countNumbers()", 500);
  }
  countNumbers();
  ```

- **使用web worker后台处理**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="utf-8">
  <title>Using Web Worker</title>
  <script>
      if(window.Worker) {
          // 创建一个新的web worker，参数为需要后台执行的脚本
          var worker = new Worker("worker.js");
          
          // 处理onmessage事件。postMessage()会发布此事件
          worker.onmessage = function(event) {
              document.getElementById("result").innerHTML = event.data;
          };
      } else {
          alert("Sorry, your browser do not support web worker.");
      }
  </script>
  </head>
  <body>
      <div id="result">
          <!--Received messages will be inserted here-->
      </div>
  </body>
  </html>
  ```

- **终止web worker**

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="utf-8">
  <title>Start/Stop Web Worker</title>
  <script>
      // 全局变量
      var worker;
      
      function startWorker() {
          // 初始化web worker
          worker = new Worker("worker.js");
          
          // 处理onmessage事件
          worker.onmessage = update;
          
          // 告诉worker开始进行
          worker.postMessage("start");
      }
      
      function update(event) {
          // Update the page with current message from worker
          document.getElementById("result").innerHTML = event.data;
      }
      
      function stopWorker() {
          // 终止worker
          worker.terminate();
      }
  </script>
  </head>
  <body>
      <h1>Web Worker Demo</h1>
      <button onclick="startWorker();" type="button">Start web worker</button>
      <button type="button" onclick="stopWorker();">Stop web worker</button>
      <div id="result">
          <!--Received messages will be inserted here-->
      </div>
  </body>
  </html>
  ```

### SSE(Server-Sent Event，服务端发送事件)

- H5提供的一种web页面与服务器交互的方式

- 传统的`XMLHttpRequest`对象(Ajax的核心)允许用JS与服务器交互，但其只是单次的

- 某些情况需要页面与服务器有长时间的连接，如股票网站上价格的自动更新

- SSE允许web页面与服务器保持一个打开的连接，因此服务器可在任何需要的时候自动发送一个新的响应而不需要重连

- SSE无方向性

- **PHP+SSE实现服务器端定时向客户端推送时间信息**

  - php

    - 通过SSE发送的信息必须以`data:`开头，紧跟实际的信息文本，最后换行符序列`\n\n`，即

    ```php
    data:actualMessageToSend\n\n
    ```

  ```php
  <?php
  header("Content-Type: text/event-stream");
  header("Cache-Control: no-cache");
   
  // Get the current time on server
  $currentTime = date("h:i:s", time());
   
  // Send it in a message
  echo "data: " . $currentTime . "\n\n";
  flush();
  ?>
  ```

  - Web页面中处理信息
    - 使用`EventSource`对象接受SSE信息

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <title>Using Server-Sent Events</title>
  <script>
      window.onload = function() {
          var source = new EventSource("server_time.php");
          source.onmessage = function(event) {
              document.getElementById("result").innerHTML += "New time received from web server: " + event.data + "<br>";
          };
      };
  </script>
  </head>
  <body>
      <div id="result">
          <!--Server response will be inserted here-->
      </div>
  </body>
  </html>
  ```

### Geolocation(地理定位)

- 地理定位功能用于查询访问用户的地理坐标(经纬度)

- **获取用户坐标**

  - 使用`navigator.geolocation`的方法
  - **getCurrentPosion()**
  - **watchPosition()**
  - **clearWatch()**

  ```html
  <script>
      function showPosition() {
          //判断浏览器是否支持
          if(navigator.geolocation) {
              //参数为获取位置成功后的回调函数
              navigator.geolocation.getCurrentPosition(function(position) {
                  var positionInfo = "Your current position is (" + "Latitude: " + position.coords.latitude + ", " + "Longitude: " + position.coords.longitude + ")";
                  document.getElementById("result").innerHTML = positionInfo;
              });
          } else {
              alert("Sorry, your browser does not support HTML5 geolocation.");
          }
      }
  </script>
  ```

- **处理错误和用户拒绝共享位置**

  - `getCurrentPosition()`函数接收两个函数为参数，第一个为获取成功后的回调函数，第二个为获取位置失败后的回调函数

  ```javascript
  if(navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(successCallback, errorCallback);
      result.innerHTML = "Getting the position information...";
  } else {
      alert("Sorry, your browser does not support HTML5 geolocation.");
  }
  ```

- **监控访问者的移动**

  - `watchPosition()`
  - 与getCurrentPosition()有相同的参数
  - 通过返回新位置实现追踪用户轨迹

  ```html
  <script>
      // Set global variable
      var watchID;
  
      function showPosition() {
          if(navigator.geolocation) {
              watchID = navigator.geolocation.watchPosition(successCallback);
          } else {
              alert("Sorry, your browser does not support HTML5 geolocation.");
          }
      }
  
      function successCallback(position) {
          toggleWatchBtn.innerHTML = "Stop Watching";
          
          // Check position has been changed or not before doing anything
          if(prevLat != position.coords.latitude || prevLong != position.coords.longitude){
              
              // Set previous location
              var prevLat = position.coords.latitude;
              var prevLong = position.coords.longitude;
              
              // Get current position
              var positionInfo = "Your current position is (" + "Latitude: " + position.coords.latitude + ", " + "Longitude: " + position.coords.longitude + ")";
              document.getElementById("result").innerHTML = positionInfo;
              
          }
          
      }
  
      function startWatch() {
          var result = document.getElementById("result");
          
          var toggleWatchBtn = document.getElementById("toggleWatchBtn");
          
          toggleWatchBtn.onclick = function() {
              if(watchID) {
                  toggleWatchBtn.innerHTML = "Start Watching";
                  navigator.geolocation.clearWatch(watchID);
                  watchID = false;
              } else {
                  toggleWatchBtn.innerHTML = "Aquiring Geo Location...";
                  showPosition();
              }
          }
      }
      
      // Initialise the whole system (above)
      window.onload = startWatch;
  </script>
  ```

- 扩展：可使用Google地图等地图Javascript API实现位置显示

### Drag and Drop(拖拽)

- 简述

  - H5允许用户将元素拖拽到其他位置，目标位置可以是不同的应用
  - 使用拖拽功能时，元素会变为半透明并跟随鼠标移动
  - 可通过元素的**draggable**属性指定元素是否可拖拽

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="utf-8">
  <title>Using Drag and Drop</title>
  <script>
      function dragStart(e) {
          // Sets the operation allowed for a drag source
          e.dataTransfer.effectAllowed = "move";
      
          // Sets the value and type of the dragged data
          e.dataTransfer.setData("Text", e.target.getAttribute("id"));
      }
      function dragOver(e) {
          // Prevent the browser default handling of the data
          e.preventDefault();
          e.stopPropagation();
      }
      function drop(e) {
          // Cancel this event for everyone else
          e.stopPropagation();
          e.preventDefault();
      
          // Retrieve the dragged data by type
          var data = e.dataTransfer.getData("Text");
      
          // Append image to the drop box
          e.target.appendChild(document.getElementById(data));
      }
  </script>
  <style>
      #dropBox {
          width: 300px;
          height: 300px;
          border: 5px dashed gray;
          background: lightyellow;
          text-align: center;
          margin: 20px 0;
          color: orange;
      }
      #dropBox img {
          margin: 25px;
      }
  </style>
  </head>
  <body>
      <h2>Drag and Drop Demo</h2>
      <p>Drag and drop the image into the drop box:</p>
      <div id="dropBox" ondragover="dragOver(event);" ondrop="drop(event);">
          <!--Dropped image will be inserted here-->
      </div>
      <img src="../images/kites.jpg" id="dragA" draggable="true" ondragstart="dragStart(event);" width="250" height="250" alt="Flying Kites">
  </body>
  </html>
  ```

- **拖拽时的事件**

  - 鼠标事件，如鼠标移动(mousemove)事件在拖拽时**不触发**

    | 事件         | 描述                                                         |
    | :----------- | :----------------------------------------------------------- |
    | ondragstart  | 开始拖拽元素时触发                                           |
    | ondragenter  | 当可拖拽元素进入可放置(drop)区时触发                         |
    | ondragover   | 当可拖拽元素经过可放置区(drop)时触发                         |
    | ondreagleave | 当可拖拽元素离开可放置区时触发                               |
    | ondrag       | 当用户拖拽时触发(连续触发)，可获取此时的鼠标位置             |
    | ondrop       | 当可拖拽元素被成功放置到可放置区时触发                       |
    | ondragend    | 当拖拽事件结束后触发，无论拖拽成功或中途取消。在从桌面拖拽到浏览器时不触发 |