[https://www.imooc.com/learn/9.%20%E5%88%9D%E8%AF%86html+css](https://www.imooc.com/learn/9. 初识html+css)

Html和CSS的关系

1. **HTML是网页内容的载体**。内容就是网页制作者放在页面上想要让用户浏览的信息，可以包含文字、图片、视频等。
2.  **CSS样式是表现**。就像网页的外衣。比如，标题字体、颜色变化，或为标题加入背景图片、边框等。所有这些用来改变内容外观的东西称之为表现。
3. **JavaScript是用来实现网页上的特效效果**。如：鼠标滑过弹出下拉菜单。或鼠标滑过表格的背景颜色改变。还有焦点新闻（新闻图片）的轮换。可以这么理解，有动画的，有交互的一般都是用JavaScript来实现的。

```css
 font-size:12px; //改变字体大小
 color:#930;     //改变颜色
 text-align:center; //改变文字位置“居中”
```
## html标签

**\<h1> \</h1>**这是一级标题，根据数字修改标题级数

**\<p> \</p>**这是段落标签

<img src="https://gss2.bdstatic.com/9fo3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=bfffb39880cb39dbd5cd6f04b17f6241/7acb0a46f21fbe09095814666a600c338744adba.jpg" >

**\<img src= >**这是插入图片的代码（点击上面这张图片可以看到具体代码）

**\<html>\</html>**是根标签

<img src="C:\Users\jimmy\AppData\Roaming\Typora\typora-user-images\image-20200107103212601.png" alt="image-20200107103212601" style="zoom: 50%;" align="left" />

\<head>定义文档头部

\<title>\<script>\<style>\<link>\<meta>等为头部元素

\<body>标签之间是网页的主要内容

## 语义化

即明白每个标签的用途。

标题采用标题标签，各个栏目名称也可用标题标签，文章内容使用段落标签。

语义化的好处：1. 更容易被搜索引擎收录。2. 更容易让屏幕阅读器读出网页内容。

# Day02

### 各类html标签

-  **\<strong>**、**\<em>**强调标签

  \<em> 表示强调，浏览器中\<em> 默认用**斜体**表示

  \<strong> 表示更强烈的强调，浏览器中\<strong> 用**粗体**表示

  （两个标签相比，目前国内前端程序员更喜欢使用\<strong>表示强调。）

  

- **\<span>**标签为文字设置单独样式

  不同于 \<strong> 和 \<em> ，它们的语义是强调。

  而\<span>标签没有语义，只是用于设置单独样式。

  

- **\<q>**标签，短文本引用 

  语义:引用别人的话。

  （浏览器会自动为引用文本加双引号，所以引用时文本不需要自行加符号）

  

- **\<blockquote>**长文本引用 （浏览器对该标签默认样式为页面两侧缩进）

  

- **\<br>**标签:分行显示文本 

  （由于html中是忽略回车和空格的，所以\<br>标签非常有必要）

  - xhtml1.0写法\<br /> 

  - html4.01写法\<br>

  - \<br /> 是一个空标签，没有HTML内容的标签就是空标签，空标签只需要写一个开始标签，这样的标签有一个空标签，没有HTML内容的标签就是空标签，空标签只需要写一个开始标签，这样的标签有\<br /> \<hr /> \<img />

    

- **\&nbsp;** 是输入空格的语法。



- **\<hr>**标签：添加水平横线 

  同\<br />标签，也是一个空标签。所以只有开始标签，没有结束标签。

  现在一般使用 xhtml1.0 的版本（其它标签也是），这种版本比较规范。

  

- **\<address>**标签：为网页添加地址信息。

  浏览器上显示样式为**斜体**。

  

- **\<code>**标签：添加一行代码

- **\<pre>**   标签：添加多行代码，语言代码段

  \<pre> 标签的主要作用:预格式化的文本。

  被包围在 pre 元素中的文本通常<u>会保留空格和换行符</u>。

- **\<ul>**标签，添加列表 \<ul>\<li>\</li>\</ul> 无序列表

- **\<ol>**标签，有序列表。每项\<li>都自带一个序号，默认从1开始。



#### div

- **\<div>**标签，相当于一个容器，可以把一些独立的逻辑部分划分出来，使用\<div>作为容器。



#### table



- **\<tbody>…\</tbody>**：如果不加\<thead>\<tbody>\<tfooter> , table表格加载完后才显示。加上这些表格结构， tbody包含行的内容下载完优先显示，不必等待表格结束后在显示，同时如果表格很长，用tbody分段，可以一部分一部分地显示。（通俗理解table 可以按结构一块块的显示，不在等整个表格加载完后显示。）
  - \<tr>…\</tr>：表格的一行
  - \<td>…\</td>：表格的一个单元格(有几格就有几列)
  - \<th>…\</th>：表格的头部的一个单元格，**表格表头**
  
- \<table summary="表格简介文本">

- \<caption>标题文本\</caption>

  

#### \<a>

- 实现超链接
- \<a href="目标网址"  title="鼠标滑过显示的文本">链接显示的文本\</a>
- 添加 **target="_blank"**可以在新窗口打开
- 链接Email地址
  - <img src="http://img.mukewang.com/52da4f2a000150b714280550.jpg">
  - 如果mailto后面同时有多个参数的话，第一个参数必须以“?”开头，后面的参数每一个都以“&”分隔

#### \<img>

- \<img src="图片地址" alt="下载失败时的替换文本" title = "提示文本">

- 1、src：标识图像的位置；

  2、alt：指定图像的描述性文本，当图像不可见时（下载不成功时），可看到该属性指定的文本；

  3、title：提供在图像可见时对图像的描述(鼠标滑过图片时显示的文本)；

  4、图像可以是GIF，PNG，JPEG格式的图像文件。

  

#### 表单标签

- 使用表单标签，与用户交互。

- 表单：把浏览者输入的数据传送到服务器端，这样服务器端程序就可以处理表单传过来的数据。

- \<form   method="传送方式"   action="服务器文件">

  1.\<form> ：\<form>标签是成对出现的，以\<form>开始，以\</form>结束。

  2.action ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)。

  3.method ： 数据传送的方式（get/post）。

- 文本输入框、密码输入框

  \<input type="text/password" name="名称" value="文本" />

  1、type：

     当type="text"时，输入框为文本输入框;

     当type="password"时, 输入框为密码输入框。

  2、name：为文本框命名，以备后台程序ASP 、PHP使用。

  3、value：为文本输入框设置默认值。(一般起到提示作用)

- 文本域，支持多行文字输入

  \<textarea  rows="行数" cols="列数">文本\</textarea>

  1、\<textarea>标签是成对出现的，以\<textarea>开始，以\</textarea>结束。

  2、cols ：多行输入域的列数。

  3、rows ：多行输入域的行数。

  4、在\<textarea>\</textarea>标签之间可以输入默认值。

- 单选框、复选框

  \<input   type="radio/checkbox"   value="值"    name="名称"   checked="checked"/>

  1、type:

     当 type="radio" 时，控件为单选框

     当 type="checkbox" 时，控件为复选框

  2、value：提交数据到服务器的值（后台程序PHP使用）

  3、name：为控件命名，以备后台程序 ASP、PHP 使用

  4、checked：当设置 checked="checked" 时，该选项被默认选中

- 下拉列表框

  <form action="save.php" method="post" >
      <label>爱好:</label>
      <select>
        <option value="看书">看书</option>
        <option value="旅游" selected="selected">旅游</option>//旅游作为默认选项被选中
        <option value="运动">运动</option>
        <option value="购物">购物</option>
      </select>
  </form>

  - 使下拉列表框进行多选：在select标签中设置multiple="multiple"属性

- 提交按钮，提交数据。

  - \<input   type="submit"   value="提交">

  只有type值设置为submit，按钮才有提交作用；value为按钮上显示的文字。

- 重置按钮，重置表单信息。
  
  - \<input   type="reset"   value="重置">

##### lable标签

- label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进了可用性。如果你在 label 标签内点击文本，就会触发此控件。就是说，当用户单击选中该label标签时，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关连的表单控件上）。

- \<label for="控件id名称">  【注意】标签的 for 属性中的值应当与相关控件的 id 属性值一定要相同。

  

## CSS样式

CSS：层叠样式表Cascading Style Sheets，它主要是用于定义HTML内容在浏览器内的显示样式，如文字大小、颜色、字体加粗等。

-  css 样式由**选择符**和**声明**组成，而**声明**又由**属性**和**值**组成

  <img src="http://img.mukewang.com/52fde5c30001b0fe03030117.jpg" align="left">

  - **选择符：**又称选择器，指明网页中要应用样式规则的元素，如本例中是网页中所有的段（p）的文字将变成蓝色，而其他的元素（如ol）不会受到影响。
  - **声明：**在英文大括号“｛｝”中的的就是声明，属性和值之间用英文冒号“：”分隔。当有多条声明时，中间可以英文分号“;”分隔

- CSS注释代码 使用 /*注释语句 */  ，Html中使用\<!--注释-->



- CSS的样式

  - 内联式——CSS样式表就是把css代码直接写在现有的HTML标签中，如：

    \<p style="color:red">这里文字是红色。\</p>

    - CSS样式要写再“ ”中，多条CSS样式代码写在一起,用分号隔开。

  - 嵌入式——写在当前文件中

    - 嵌入式css样式，就是可以把css样式代码写在\<style type="text/css">\</style>标签之间。
  
      \<style type="text/css">
      span{
      color:red;
      }
      \</style>
  
  - 外部式
  
    - (外联式)就是把css代码写一个单独的外部文件中，这个css样式文件以“.css”为扩展名，在\<head>内（不是在\<style>标签内）使用\<link>标签将css样式文件链接到HTML文件内，如下面代码：
  
      \<link href="base.css" rel="stylesheet" type="text/css" />
  
      (rel="stylesheet" type="text/css" 是固定写法不可修改。)
  
  - 三种方法**优先级**：内联式 > 嵌入式 > 外部式
    - 但是嵌入式>外部式有一个前提：嵌入式css样式的位置一定在外部式的后面。如右代码编辑器就是这样，<link href="style.css" ...>代码在\<style type="text/css">...\</style>代码的前面（实际开发中也是这么写的）。
    - 三者进行比较要在相同权值情况下
    - 就近原则（离被设置元素越近优先级别越高）。

### 选择器

- 选择器{
      样式;
  }

#### 标签选择器

- 标签选择器其实就是html代码中的标签\<html>、\<body>、\<h1>、\<p>、\<img>

#### 类选择器

- .类选器名称{css样式代码;}

- 1、英文圆点开头

  2、其中类选器名称可以任意起名 

- 第一步：使用合适的标签把要修饰的内容标记起来，如下：

  \<span>胆小如鼠\</span>
  第二步：使用class="类选择器名称"为标签设置一个类，如下：

  \<span class="stress">胆小如鼠\</span>
  第三步：设置类选器css样式，如下：

  .stress{color:red;}     类前面要加入一个英文圆点

#### ID选择器

- 1、为标签设置id="ID名称"，而不是class="类名称"。

  2、ID选择符的前面是井号（#）号，而不是英文圆点（.）。



- 类选择器和ID选择器的区别

  **相同点**：可以应用于任何元素
  **不同点**：

  1、ID选择器只能在文档中使用一次。与类选择器不同，在一个HTML文档中，ID选择器只能使用一次，而且仅一次。而类选择器可以使用多次。

  2、**可以使用类选择器词列表方法为一个元素同时设置多个样式。**我们可以为一个元素同时设多个样式，但只可以用类选择器的方法实现，ID选择器是不可以的（**不能使用 ID 词列表）。**

  - .stress{
        color:red;
    }
    .bigsize{
        font-size:25px;
    }

    \<p>到了\<span class="stress bigsize">三年级\</span>下学期时，我们班上了一节公开课...\</p>

    上面代码的作用是为“三年级”三个文字设置文本颜色为红色并且字号为25px。

    ID选择器不可以。

#### 子选择器

- 大于符号(>),用于选择指定标签元素的**第一代子元素**。如右侧代码编辑器中的代码：

  .food>li{border:1px solid red;}
  这行代码会使class名为food下的子元素li（水果、蔬菜）加入红色实线边框。

#### 包含（后代）选择器

- **包含选择器**，即加入空格,用于选择指定标签元素下的后辈元素。如右侧代码编辑器中的代码：

  .first  span{color:red;}

- 后代选择器与子选择器的区别：

  - 子选择器（child selector）仅是指它的直接后代，作用于子元素的第一代后代。子选择器是通过“**>**”进行选择。

  - 后代选择器是作用于**所有**子后代元素。后代选择器通过**空格**来进行选择。

  <u>总结</u>：**>**作用于元素的第一代后代，**空格**作用于元素的所有后代。

#### 通用选择器

- 通用选择器是功能最强大的选择器，它使用一个（*）号指定，它的作用是匹配html中所有标签元素，如下使用下面代码使用html中任意标签元素字体颜色全部设置为红色：

  \* {color:red;}

#### 伪类选择符

- 伪类选择符:允许给html不存在的标签（标签的某种状态）设置样式。

  如给html中一个标签元素的鼠标滑过的状态来设置字体颜色：

  a:hover{color:red;} 

  - 到目前为止，可以兼容所有浏览器的“伪类选择符”就是 a 标签上使用 :hover 了。其实 :hover 可以放在任意的标签上，比如说 p:hover，但是它们的兼容性也是很不好的，所以现在比较常用的还是 a:hover 的组合。

#### 分组选择符

- 为html中多个标签元素设置同一个样式时，可以使用分组选择符（，），如下代码为右侧代码编辑器中的h1、span标签同时设置字体颜色为红色：

  h1,span{color:red;}
  它相当于下面两行代码：

  h1{color:red;}
  span{color:red;}

### 属性

#### 继承

- CSS的**<u>某些样式</u>**是具有继承性的，那么什么是继承呢？继承是一种规则，它允许样式不仅应用于某个特定html标签元素，而且应用于其后代。
  - 颜色样式有继承性，但边框像素，边框线子元素不具有继承性。

#### 特殊性

- 为同一个元素设置了不同的CSS样式代码，那么元素会根据权值启用样式：

  **标签的权值为1，类选择符的权值为10，ID选择符的权值最高为100**

  p{color:red;} 权值为1
  p span{color:green;} 权值为1+1=2
  .warning{color:white;} 权值为10
  p span.warning{color:purple;} 权值为1+1+10=12
  #footer .note p{color:yellow;} 权值为100+10+1=111

  **注意：还有一个权值比较特殊--继承也有权值但很低，有的文献提出它只有0.1，所以可以理解为继承的权值最低。**
  
  

#### 层叠

- 层叠就是在html文件中对于同一个元素可以有多个css样式存在，当有相同权重的样式存在时，会根据这些css样式的前后顺序来决定，处于最后面的css样式会被应用。

- 如下面代码:

  p{color:red;}
  p{color:green;}

  \<p class="first">三年级时，我还是一个\<span>胆小如鼠\</span>的小女孩。\</p>

  最后 p 中的文本会设置为green，这个层叠很好理解，理解为后面的样式会覆盖前面的样式。

  css样式优先级：

  内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）。

#### 重要性

- !important 可以为某些样式设置最高权值

- p{color:red!important;}    要写在分号前面

  - 这里注意当网页制作者不设置css样式时，浏览器会按照自己的一套样式来显示网页。并且用户也可以在浏览器中设置自己习惯的样式，比如有的用户习惯把字号设置为大一些，使其查看网页的文本更加清楚。这时注意样式优先级为：浏览器默认的样式 < 网页制作者样式 < 用户自己设置的样式，但记住!important优先级样式是个例外，权值高于用户自己设置的样式。

    

## CSS格式化排版

### 文字排版

#### 字体

- body{font-family:"Microsoft Yahei";} 设置字体为微软雅黑

####  字号、颜色

- body{font-size:12px; color:blue;}

#### 粗体

- font-weight:bold;

#### 斜体

- font-style:italic;

#### 下划线

- text-decoration:underline;

#### 删除线

- text-decoration:line-through;

### 段落排版

#### 缩进

- text-indent:2em;
  - 2em的意思就是文字的2倍大小。

#### 行间距（行高）

- line-height:1.5em;      这里设置行间距为1.5倍。

#### 中文字间距、字母间距

- 中文字间隔、字母间隔：

  letter-spacing:50px;   设置文字间隔或者字母间隔为50px。

- 单词间距设置：

  word-spacing:50px;   设置英文单词之间间距为50px。

#### 对齐

- 为块状元素的文本、图片设置居中样式: text-align:center;
  - center居中，left居左，right居右。

## CSS盒模型

### 元素分类

在CSS中，html中的标签元素大体被分为三种不同的类型：块状元素、内联元素(又叫行内元素)和内联块状元素。

常用的块状元素有：

\<div>、\<p>、\<h1>...\<h6>、\<ol>、\<ul>、\<dl>、\<table>、\<address>、\<blockquote> 、\<form>


常用的内联元素有：

\<a>、\<span>、\<br>、\<i>、\<em>、\<strong>、\<label>、\<q>、\<var>、\<cite>、\<code>

常用的内联块状元素有：

\<img>、\<input>

#### 块级元素

- 什么是块级元素？在html中\<div>、\<p>、\<h1>、\<form>、\<ul> 和 \<li>就是块级元素。设置display:block就是将元素显示为块级元素。如下代码就是将内联元素a转换为块状元素，从而使a元素具有块状元素特点。

  a{display:block;}

- 特点：

  - 1、每个块级元素都从新的一行开始，并且其后的元素也另起一行。（真霸道，一个块级元素独占一行）

    2、元素的高度、宽度、行高以及顶和底边距**都可设置**。

    3、<u>元素宽度在不设置的情况下，**是它本身父容器的100%**（和父元素的宽度一致）</u>，除非设定一个宽度。

#### 内联元素

- 在html中，\<span>、\<a>、\<label>、 \<strong> 和\<em>就是典型的内联元素（行内元素）（inline）元素。当然块状元素也可以通过代码display:inline将元素设置为内联元素。如下代码就是将块状元素div转换为内联元素，从而使 div 元素具有内联元素特点。

   div{
       display:inline;
   }

- 特点：

  1、和其他元素都在一行上；

  2、元素的高度、宽度及顶部和底部边距**不可设置**；

  3、元素的宽度就是它包含的文字或图片的宽度，不可改变。

#### 内联块状元素

- 内联块状元素（inline-block）就是同时具备内联元素、块状元素的特点，代码display:inline-block就是将元素设置为内联块状元素。(css2.1新增)，\<img>、\<input>标签就是这种内联块状标签。

- 特点：

  1、和其他元素都在一行上；

  2、元素的高度、宽度、行高以及顶和底边距都可设置。

### 盒模型

#### 边框

- 盒子模型的边框就是围绕着内容及补白的线，这条线你可以设置它的粗细、样式和颜色(边框三个属性)。

  如下面代码为 div 来设置边框粗细为 2px、样式为实心的、颜色为红色的边框：

  div{
      border:2px  solid  red;
  }
  上面是 border 代码的缩写形式，可以分开写：

  div{
      border-width:2px;
      border-style:solid;
      border-color:red;
  }

  - 注意：

    1、border-style（边框样式）常见样式有：

    dashed（虚线）| dotted（点线）| solid（实线）。

    2、border-color（边框颜色）中的颜色可设置为十六进制颜色，如:

    border-color:#888;//前面的井号不要忘掉。

    3、border-width（边框宽度）中的宽度也可以设置为：

    thin | medium | thick（但不是很常用），最常还是用像素（px）。

- 为标签单独设置某方向的边框，其它方向不设置：

  div{border-bottom:1px solid red;}    为标签设置下边框

  border-top:1px solid red; 上
  border-right:1px solid red; 右
  border-left:1px solid red; 左

#### 宽度和高度

- css内定义的宽（width）和高（height），指的是填充以里的内容范围。

- 一个元素实际宽度（盒子的宽度）=左边界+左边框+左填充+内容宽度+右填充+右边框+右边界。

<img src="http://img1.sycdn.imooc.com/539fbb3a0001304305570259.jpg"  >

- div{
      width:200px;
      padding:20px;
      border:1px solid red;
      margin:10px;    
  }\

  元素的实际长度为：10px+1px+20px+200px+20px+1px+10px=262px。

<img src="http://img1.sycdn.imooc.com/543b4cae0001b34304300350.jpg">

#### 填充

- 元素内容与边框之间是可以设置距离的，称之为“填充”。填充也可分为上、右、下、左(顺时针)。

  - div{padding:20px 10px 15px 30px;}

  - **顺序一定不要搞混**。可以分开写上面代码：

  - div{
       padding-top:20px;
       padding-right:10px;
       padding-bottom:15px;
       padding-left:30px;
    }

  - 如果上、右、下、左的填充都为10px;可以这么写

    div{padding:10px;}

  - 如果上下填充一样为10px，左右一样为20px，可以这么写：div{padding:10px 20px;}

#### 边界

- 元素与其它元素之间的距离可以使用边界（margin）来设置。边界也是可分为上、右、下、左。

  - 如下代码：

    div{margin:20px 10px 15px 30px;}

  - 也可以分开写：

    div{
       margin-top:20px;
       margin-right:10px;
       margin-bottom:15px;
       margin-left:30px;
    }

  - 如果上右下左的边界都为10px;可以这么写：

    div{ margin:10px;}

  - 如果上下边界一样为10px，左右一样为20px，可以这么写：div{ margin:10px 20px;}

- padding和margin的区别：padding在边框里，margin在边框外

## CSS布局模型

- 布局模型与盒模型一样都是 CSS 最基本、 最核心的概念。 

  但布局模型是建立在盒模型基础之上，又不同于我们常说的 CSS 布局样式或 CSS 布局模板。

  如果说布局模型是本，那么 CSS 布局模板就是末了，是外在的表现形式。 
  CSS包含3种基本的布局模型，用英文概括为：Flow、Layer 和 Float。
  在网页中，元素有三种布局模型：
  1、流动模型（Flow）
  2、浮动模型 (Float)
  3、层模型（Layer）

### 流动模型

- 流动（Flow）是默认的网页布局模式。也就是说网页在默认状态下的 HTML 网页元素都是根据流动模型来分布网页内容的。

- 特征：

  - 第一点，**块状元素**都会在所处的包含元素内**自上而下**按顺序垂直延伸分布，因为在默认状态下，块状元素的宽度都为100%。实际上，块状元素都会以行的形式占据位置。

  - 第二点，在流动模型下，内联元素都会在所处的包含元素内从左到右水平分布显示。（内联元素可不像块状元素这么霸道独占一行）

    右侧代码编辑器中内联元素标签a、span、em、strong都是内联元素。

### 浮动模型

- 设置元素浮动，可以实现让两个块状元素并排显示。

- 任何元素在默认情况下是不能浮动的，但可以用 CSS 定义为浮动，如 div、p、table、img 等元素都可以被定义为浮动。

  如下代码可以实现两个 div 元素一行显示。

  div{
      width:200px;
      height:200px;
      border:2px red solid;
      float:**left**;
  }

  \<div id="div1">\</div>
  \<div id="div2">\</div>

  <img src="http://img1.sycdn.imooc.com/540e62c60001c56a06760417.jpg">

  - 也可以同时设置两个元素右浮动也可以实现一行显示。

    div{
        width:200px;
        height:200px;
        border:2px red solid;
        float:**right**;
    }

    <img src="http://img1.sycdn.imooc.com/540e632b0001f5f506760417.jpg">

### 层模型

- 层布局模型就像是图像软件PhotoShop中非常流行的图层编辑功能一样，每个图层能够精确定位操作，但在网页设计领域，由于网页大小的活动性，层布局没能受到热捧。

- CSS定义了一组定位（positioning）属性来支持层布局模型。

  层模型有三种形式：

  1、**绝对定位**(position: absolute)

  2、**相对定位**(position: relative)

  3、**固定定位**(position: fixed)

#### 绝对定位

- 为元素设置层模型中的绝对定位，需要设置position:absolute(表示绝对定位)。

- 这条语句的作用将元素从文档流中拖出来，然后使用left、right、top、bottom属性相对于其最接近的一个具有定位属性的父包含块进行绝对定位。<u>如果不存在这样的包含块，则相对于body元素，即**相对于浏览器窗口**</u>。

  - 如下面代码可以实现div元素相对于浏览器窗口向右移动100px，向下移动50px。

    div{
        width:200px;
        height:200px;
        border:2px red solid;
        position:absolute;
        left:100px;
        top:50px;
    }

    \<div id="div1">\</div>

    <img src="http://img1.sycdn.imooc.com/53a00b130001e86707360547.jpg">

#### 相对定位

- 为元素设置层模型中的相对定位，需要设置position:relative（表示相对定位）。

  它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。

  相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后相对于以前的位置移动，移动的方向和幅度由left、right、top、bottom属性确定，偏移前的位置保留不动。

  - 如下代码实现相对于以前位置向下移动50px，向右移动100px;

    #div1{
        width:200px;
        height:200px;
        border:2px red solid;
        position:relative;
        left:100px;
        top:50px;
    }

    \<div id="div1">\</div>

    <img src="http://img1.sycdn.imooc.com/53a00d2b00015c4b06190509.jpg">

- 偏移前的位置保留不动：

  div标签的后面加入一个span标签，当div标签设置了相对定位进行移动后，这个span标签仍然按照div标签以前的位置显示。

<img src="http://img1.sycdn.imooc.com/541a4bfc0001abef05940489.jpg">

#### 固定定位

- fixed：表示固定定位，与absolute定位类型类似，但它的相对移动的坐标是视图（**屏幕内的网页窗口**）本身。

  由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化，除非你在屏幕中移动浏览器窗口的屏幕位置，或改变浏览器窗口的显示大小，因此固定定位的元素会始终位于浏览器窗口内视图的某个位置，不会受文档流动影响，这与background-attachment:fixed;属性功能相同。

  以下代码可以实现相对于浏览器视图向右移动100px，向下移动50px。并且拖动滚动条时位置固定不变。

  #div1{
      width:200px;
      height:200px;
      border:2px red solid;
      position:fixed;
      left:100px;
      top:50px;
  }

  \<p>文本\</p>

#### Relative与Absolute组合使用

- 使用position:absolute可以实现被设置元素相对于浏览器（body）设置定位

- 使用position:relative可以相对于其它元素进行定位

  - 遵循的规则：

    1、**参照定位的元素必须是相对定位元素的前辈元素**：

    \<div id="box1"><!--参照定位的元素-->
        \<div id="box2">相对参照元素进行定位\</div><!--相对定位元素-->
    \</div>

    从上面代码可以看出box1是box2的父元素（父元素当然也是前辈元素了）。

    2、**参照定位的元素必须加入position:relative;**

    #box1{
        width:200px;
        height:200px;
        position:relative;        
    }
    3、**定位元素加入position:absolute，便可以使用top、bottom、left、right来进行偏移定位了**。

    #box2{
        position:absolute;
        top:20px;
        left:30px;         
    }
    这样box2就可以相对于父元素box1定位了（这里注意参照物就可以不是浏览器了，而可以自由设置了）。

- 个人话语总结:

  想要某个元素B参照元素A进行定位，A元素要为B元素的前辈元素，且A元素中要加入position:relative;B元素要加入position:absolute;

## CSS代码缩写，占用更少带宽

### 盒模型代码简写

- 盒模型外边距(margin)、内边距(padding)和边框(border)设置**上下左右**四个方向的边距是按照**顺时针方向**设置的：上右下左。

  具体应用在margin和padding的例子如下：

  margin:10px 15px 12px 14px; /*上设置为10px、右设置为15px、下设置为12px、左设置为14px*/

- 三种缩写方法:

  1、如果top、right、bottom、left的值相同，如下面代码：

  ```css
  margin:10px 10px 10px 10px;
  ```

  可缩写为：

  ```css
  margin:10px;
  ```

  2、如果<u>top和bottom</u>值相同、<u>left和 right</u>的值相同，如下面代码：

  ```css
  margin:10px 20px 10px 20px;
  ```

  可缩写为：

  ```CSS
  margin:10px 20px;
  ```

  3、如果left和right的值相同，如下面代码：

  ```CSS
  margin:10px 20px 30px 20px;
  ```

  可缩写为：

  ```CSS
  margin:10px 20px 30px;
  ```

  注意：padding、border的缩写方法和margin是一致的。

### 颜色值缩写

- 当设置的颜色是16进制的色彩值时，如果每两位的值相同，可以缩写一半。

  例子1：

  ```css
  p{color:#000000;}
  ```

  可以缩写为：

  ```css
  p{color: #000;}
  ```

  例子2：

  ```css
  p{color: #336699;}
  ```

  可以缩写为：

  ```css
  p{color: #369;}
  ```

### 字体缩写

- 网页中的字体css样式代码也有他自己的缩写方式，下面是给网页设置字体的代码：

  ```css
  body{
      font-style:italic;
      font-variant:small-caps; 
      font-weight:bold; 
      font-size:12px; 
      line-height:1.5em; 
      font-family:"宋体",sans-serif;
  }
  ```

  可以缩写为一句：

  ```css
  body{
      font:italic  small-caps  bold  12px/1.5em  "宋体",sans-serif;
  }
  ```

- 注意：

  1、使用这一简写方式你至少要指定 font-size 和 font-family 属性，其他的属性(如 font-weight、font-style、font-variant、line-height)如未指定将自动使用默认值。

  2、在缩写时 font-size 与 line-height 中间要加入“/”斜扛。

  一般情况下因为对于中文网站，英文还是比较少的，所以下面缩写代码比较常用：

  ```
  body{
      font:12px/1.5em  "宋体",sans-serif;
  }
  ```

  只是有字号、行间距、中文字体、英文字体设置。

## 单位和值

### 颜色值

- 在网页中的颜色值有<u>字体颜色（color）</u>、<u>背景颜色（background-color）</u>、<u>边框颜色（border）</u>等，设置颜色的方法也有很多种：

  1、英文命令颜色

  ```css
  p{color:red;}
  ```

  2、RGB颜色

  这个与 photoshop 中的 RGB 颜色是一致的，由 R(red)、G(green)、B(blue) 三种颜色的比例来配色。

  ```CSS
  p{color:rgb(133,45,200);}
  ```

  每一项的值可以是 0~255 之间的整数，也可以是 0%~100% 的百分数。如：

  ```CSS
  p{color:rgb(20%,33%,25%);}
  ```

  3、十六进制颜色

  这种颜色设置方法是现在比较普遍使用的方法，其原理其实也是 RGB 设置，但是其每一项的值由 0-255 变成了十六进制 00-ff。

  ```CSS
  p{color:#00ffff;}
  ```

### 长度值

- 目前比较常用到的长度单位：px（像素）、em、% 百分比，这三种单位都是相对单位。

#### 像素

- 像素指的是显示器上的小点（CSS规范中假设“90像素=1英寸”）。实际情况是浏览器会使用显示器的实际像素值有关，在目前大多数的设计者都倾向于使用像素（px）作为单位。

#### em

- 就是本元素给定字体的 font-size 值，如果元素的 font-size 为 14px ，那么 1em = 14px；如果 font-size 为 18px，那么 1em = 18px。如下代码：

  ```CSS
  p{font-size:12px;text-indent:2em;}
  ```

  上面代码就是可以实现段落首行缩进 24px（也就是两个字体大小的距离）。

- **注意一个特殊情况：**

  当给 font-size 设置单位为 em 时，**此时计算的标准以 p 的父元素的 font-size 为基础**。如下代码：

  html:

  ```html
  <p>以这个<span>例子</span>为例。</p>
  ```

  css:

  ```css
  p{font-size:14px}
  span{font-size:0.8em;}
  ```

  结果 span 中的字体“例子”字体大小就为 11.2px（14 * 0.8 = 11.2px）。

#### 百分比%

- ```CSS
  p{font-size:12px;line-height:130%}
  ```

  设置行高（行间距）为字体的130%（12 * 1.3 = 15.6px）。

## CSS样式设置小技巧

### 水平居中设置

#### 行内元素

- 水平居中分为<u>行内元素</u>和<u>块状元素</u>，块状元素中又分为<u>定宽块状元素</u>和<u>不定宽块状元素</u>。

- 如果被设置元素为文本、图片等行内元素时，水平居中是通过给**父元素**设置 `text-align:center` 来实现的。(父元素和子元素：如下面的html代码中，div是“我想要在父容器中水平居中显示”这个文本的父元素。反之这个文本是div的子元素 )如下代码：

html代码：

```html
<body>
  <div class="txtCenter">我想要在父容器中水平居中显示。</div>
</body>
```

css代码：

```css
<style>
  .txtCenter{
    text-align:center;
  }
</style>
```

#### 定宽块状元素

- 当被设置元素为 [块状元素](http://www.imooc.com/code/2048) 时用 text-align：center 就不起作用了，这时也分两种情况：**定宽**块状元素和**不定宽**块状元素。

- 定宽块状元素：块状元素的宽度width为固定值。

- 满足**定宽**和**块状**两个条件的元素是可以通过设置“左右margin”值为“auto”来实现居中的。我们来看个例子就是设置 div 这个块状元素水平居中：

  html代码：

  ```html
  <body>
    <div>我是定宽块状元素，哈哈，我要水平居中显示。</div>
  </body>
  ```

  css代码：

  ```css
  <style>
  div{
      border:1px solid red;/*为了显示居中效果明显为 div 设置了边框*/
      
      width:200px;/*定宽*/
      margin:20px auto;/* margin-left 与 margin-right 设置为 auto */
  }
  
  </style>
  ```

  也可以写成：

  ```css
  margin-left:auto;
  margin-right:auto;
  ```

  注意：元素的“上下 margin” 是可以随意设置的。

#### 不定宽块状元素

- 不定宽块状元素：块状元素的宽度width不固定。
- 使用情景：网页上的分页导航，因为分页的数量是不确定的，所以我们不能通过设置宽度来限制它的弹性。

- 三种居中方法:
  1. 加入 [table](http://www.imooc.com/code/292) 标签
  2. 设置 [display: inline](http://www.imooc.com/code/2049) 方法：与第一种类似，显示类型设为 行内元素，进行不定宽元素的属性设置
  3. 设置 [position:relative](http://www.imooc.com/code/2074) 和 left:50%：利用 相对定位 的方式，将元素向左偏移 50% ，即达到居中的目的

##### 方法一：加入table标签

- 利用table标签的长度自适应性---即不定义其长度也不默认父元素body的长度（table其长度根据其内文本长度决定）。

  因此可以看做一个定宽度块元素，然后再利用**定宽度块状**居中的margin的方法，使其水平居中。

  - 第一步：为需要设置的居中的元素外面加入一个 table 标签 ( 包括 \<tbody>、\<tr>、\<td> )。

  - 第二步：为这个 table 设置“左右 margin 居中”（这个和定宽块状元素的方法一样）。

  举例如下：

  html代码：

  ```html
  <div>
   <table>
    <tbody>
      <tr><td>
      <ul>
          <li>我是第一行文本</li>
          <li>我是第二行文本</li>
          <li>我是第三行文本</li>
      </ul>
      </td></tr>
    </tbody>
   </table>
  </div>
  ```

  css代码：

  ```css
  <style>
  table{
      border:1px solid;
      margin:0 auto;
  }
  </style>
  ```

##### 方法二：改变display为inline类型

- 改变块级元素的 display 为 inline 类型（设置为 [行内元素](http://www.imooc.com/code/2049) 显示），然后使用 `text-align:center` 来实现居中效果。如下例子：

  html代码：

  ```html
  <body>
  <div class="container">
      <ul>
          <li><a href="#">1</a></li>
          <li><a href="#">2</a></li>
          <li><a href="#">3</a></li>
      </ul>
  </div>
  </body>
  ```

  css代码：

  ```css
  <style>
  .container{
      text-align:center;
  }
  /* margin:0;padding:0（消除文本与div边框之间的间隙）*/
  .container ul{
      list-style:none;
      margin:0;
      padding:0;
      display:inline;
  }
  /* margin-right:8px（设置li文本之间的间隔）*/
  .container li{
      margin-right:8px;
      display:inline;
  }
  </style>
  ```

  这种方法相比第一种方法的**优势**是不用增加无语义标签，但也存在着一些**问题**：它将块状元素的 display 类型改为 inline，变成了行内元素，所以少了一些功能，比如设定长度值。

##### 方法三：设置浮动和相对定位

- 通过给父元素设置[ float](http://www.imooc.com/code/2071)，然后给**父元素设置 [position:relative](http://www.imooc.com/code/2074) 和 left:50%**，**子元素设置 position:relative 和 left: -50%** 来实现水平居中。

- 我们可以这样理解：

  假想ul层的父层（即下面例子中的div层）中间有条平分线将ul层的父层（div层）平均分为两份，

  ul层的css代码是将ul层的最左端与ul层的父层（div层）的平分线对齐；

  li层的css代码则是将li层的平分线与ul层的最左端（也是div层的平分线）对齐，从而实现li层的居中。

- 代码如下：

  ```html
  <body>
  <div class="container">
      <ul>
          <li><a href="#">1</a></li>
          <li><a href="#">2</a></li>
          <li><a href="#">3</a></li>
      </ul>
  </div>
  </body>
  ```

  css代码：

  ```css
  <style>
  .container{
      float:left;
      position:relative;
      left:50%
  }
  
  .container ul{
      list-style:none;
      margin:0;
      padding:0;
      
      position:relative;
      left:-50%;
  }
  .container li{float:left;display:inline;margin-right:8px;}
  </style>
  ```

### 垂直居中设置

- 分两种情况：父元素高度确定的单行文本，以及父元素高度确定的多行文本。

#### 父元素高度确定的单行文本

- **父元素高度确定的单行文本**的竖直居中的方法是通过

  设置父元素的 height 和[ line-height ](http://www.imooc.com/code/2083)高度一致来实现的。

  (height: 该元素的高度，line-height: 顾名思义，行高（行间距），指在文本中，行与行之间的 基线间的距离 )。

  line-height 与 font-size 的计算值之差，在 CSS 中成为“行间距”。分为两半，分别加到一个文本行内容的顶部和底部。

  这种文字行高与块高一致带来了一个弊端：当文字内容的长度大于块的宽时，就有内容脱离了块。

  如下代码：

  ```
  <div class="container">
      hi,imooc!
  </div>
  ```

  css代码：

  ```
  <style>
  .container{
      height:100px;
      line-height:100px;
      background:#999;
  }
  </style>
  ```

#### 父元素高度确定的多行文本

##### 方法一：插入table

- 使用插入 [table](http://www.imooc.com/code/292) (包括tbody、tr、td)标签，同时设置 vertical-align：middle。

  css 中有一个用于竖直居中的属性 vertical-align，在父元素设置此样式时，会对inline-block类型的子元素都有用。下面看一下例子：

  html代码：

  ```html
  <body>
  <table><tbody><tr><td class="wrap">
  <div>
      <p>看我是否可以居中。</p>
  </div>
  </td></tr></tbody></table>
  </body>
  ```

  css代码：

  ```css
  table td{height:500px;background:#ccc}
  ```

  因为 td 标签默认情况下就默认设置了 vertical-align 为 middle，所以我们不需要显式地设置了。

##### 方法二：

- 在 chrome、firefox 及 IE8 以上的浏览器下可以设置块级元素的 display 为 table-cell（设置为表格单元显示），激活 vertical-align 属性，但注意 IE6、7 并不支持这个样式, 兼容性比较差。

- 这种方法的好处是不用添加多余的无意义的标签，但缺点也很明显，它的兼容性不是很好，不兼容 IE6、7而且这样修改display的block变成了table-cell，破坏了原有的块状元素的性质。

  html代码：

  ```html
  <div class="container">
      <div>
          <p>看我是否可以居中。</p>
          <p>看我是否可以居中。</p>
          <p>看我是否可以居中。</p>
      </div>
  </div>
  ```

  css代码：

  ```css
  <style>
  .container{
      height:300px;
      background:#ccc;
      display:table-cell;/*IE8以上及Chrome、Firefox*/
      vertical-align:middle;/*IE8以上及Chrome、Firefox*/
  }
  </style>
  ```

## 隐性改变display类型

- 当为元素（不论之前是什么类型元素，display:none 除外）设置以下 2 个句之一：

  1. [position : absolute](http://www.imooc.com/code/2073) 

  2. float : left 或 [float:right](http://www.imooc.com/code/2071) 

  简单来说，只要html代码中出现以上两句之一，元素的display显示类型就会自动变为以 display:inline-block（[块状元素](http://www.imooc.com/code/2048)）的方式显示，当然就可以设置元素的 width 和 height 了，且默认宽度不占满父元素。

-  a 标签是 [行内元素](http://www.imooc.com/code/2049) ，所以设置它的 width 是 没有效果的，但是设置为 position:absolute 以后，就可以了。

- html代码：

  ```html
  <div class="container">
      <div>
          <p>看我是否可以居中。</p>
          <p>看我是否可以居中。</p>
          <p>看我是否可以居中。</p>
      </div>
  </div>
  ```

  css代码：

  ```css
  <style>
  .container{
      height:300px;
      background:#ccc;
      display:table-cell;/*IE8以上及Chrome、Firefox*/
      vertical-align:middle;/*IE8以上及Chrome、Firefox*/
  }
  </style>
  ```