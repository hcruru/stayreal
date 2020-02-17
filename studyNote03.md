# JavaScript

https://www.imooc.com/learn/36

## JavaScript学习预备知识

### 如何插入JS

- 使用\<script>标签在HTML中插入JavaScript代码，标签要成对存在，代码写在标签之间。
- \<script type="text/javascript">表示在\<script>\<\script>之间的是文本类型(text),javascript是为了告诉浏览器里面的语言属于JavaScript语言。

### JS在页面中的位置

- JavaScript代码可以放在html文件中任何位置

  - 放在\<head>部分，浏览器解析head部分就会这个代码，然后才解析页面的其余部分。

  - 放在\<body>部分，JavaScript代码在网页读取到该语句的时候就会执行。

    **注意:** javascript作为一种脚本语言可以放在html页面中任何位置，但是浏览器解释html时是按先后顺序的，所以前面的script就先被执行。比如进行页面显示初始化的js必须放在head里面，因为初始化都要求提前进行（如给页面body设置css等）；而如果是通过事件调用执行的function那么对位置没什么要求的。

### JS的语句符号

- 语句;
- 注意分号是英文状态下。

### JS注释

- 单行注释//
- 多行注释/* 注释内容 养成注释好习惯  */

### JS-变量

- 从编程角度，变量是用于存储某种/某些数值的存储器。

- 变量可以看作是一个盒子，为了区分盒子，用box1,box2来区分，作为变量的名字。

- 定义变量语法：

  var 变量名

  - 变量名可以任意取名，但要遵循命名规则：

    - 变量必须使用字母，下划线 _，或者美元符号$开始。
    - 可以使用任意多个英文字母、数字、下划线或者美元符号组成。
    - 不能使用JavaScript关键词与JavaScript保留字。

  - 变量要先声明再赋值：

    - var mychar;

      mychar="javascript";

      var mynum=6;

  - 变量可以重复赋值：

    - var mychar;

      mychar="javascript";

      mychar="hello";

- 注意：

  - 在JS中区分大小写，如变量mychar与myChar是不一样的，表示两个变量。
  - 变量虽然可以不用声明直接使用，但是不规范，需要先声明，后使用。

### JS-函数

- function 函数名()

  {

  ​	函数代码；

  }

- 说明： 

  1.function定义函数关键字

  2.“函数名”为函数取的名字

  3.“函数代码”替换为完成特定功能的代码

### JS-输出内容（document.write）

- document.write可用于直接向HTML输出流写内容，即直接在网页中输出内容。

- 第一种：输出内容用""括起，直接输出""号内的内容。

  document.write("I love JavaScript！");

- 第二种：通过变量，输出内容

  var mystr="hello world!";

  document.write(mystr);

- 第三种：输出多项内容，内容之间用+号连接

  var mystr="hello";

  document.write(mystr+"I love JavaScript");

- 第四种：输出HTML标签，并起作用，标签使用""括起来。

  var mystr="hello";

  document.write(mystr+"\<br>");  //输出hello后，输出一个换行符

  document.write("JavaScript");

### JS-警告（alert消息对话框）

- alert(字符串或变量);
  - 注：alert弹出消息对话框（包含一个确定按钮），并且按照顺序弹出对话框。
- 注意：
  - 1.在点击对话框"确定"按钮前，不能进行任何其它操作。
  - 2.消息对话框通常可以用于调试程序。
    - 3.alert输出内容，可以是字符串或变量，与document.write相似。

### JS-确认（confirm消息对话框）

- confirm 消息对话框通常用于允许用户做选择的动作，如：“你对吗？”等。弹出对话框(包括一个确定按钮和一个取消按钮)。

- 语法：confirm(str);

- 参数说明：
  - str：在消息对话框中要显示的文本
  - 返回值：Boolean值

- 返回值：

  当用户点击"确定"按钮，返回true

  当用户点击"取消"按钮，返回false

  - 注：通过返回值可以判断用户点击了什么按钮。

- 消息对话框是排它的，用户在点击对话框按钮前，不能进行任何其它操作。

- var mymessage=confirm("你喜欢JavaScript吗?");
      if(mymessage==true)
      {   document.write("很好,加油!");   }
      else
      {  document.write("JS功能强大，要学习噢!");   }

### JS-提问（prompt消息对话框）

- promt弹出消息对话框，通常用于询问一些需要与用户交互的信息。弹出消息对话框（包含一个确定按钮、取消按钮与一个文本输入框）。
- prompt()函数的返回值是String类型的
- 语法：prompt(str1,str2);
- 参数说明:

  - str1:要显示在消息对话框中的文本，不可修改

  - str2:文本框中的内容，可以修改
- 返回值：
  - 1.点击确定按钮，文本框中的内容将作为函数返回值
  - 2.点击取消按钮，将返回null
- var myname=prompt("请输入你的姓名:");
  if(myname!=null)
    {   alert("你好"+myname); }
  else
    {  alert("你好 my friend.");  }

### JS-打开新窗口（window.open）

- open()方法可以查找一个已经存在或者新建的浏览器窗口。

- 语法：

  window.open([URL],[窗口名称],[参数字符串]);

- 参数说明：

  - URL:可选参数，在窗口中要显示的网页的网址或路径。

    如果省略这个参数，或者它的值是空字符串，那么窗口就显示任何文档。

  - 窗口名称：可选参数，被打开窗口的名称。

    1.该名称由字母、数字和下划线字符组成。

    2."\_top"、"\_blank"、"\_self"具有特殊意义的名称。

    - _blank:在新窗口显示目标网页
    - _self:在当前窗口显示目标网页
    - _top:框架网页中在上部窗口中显示目标网页

    3.相同name的窗口只能创建一个，想要创建多个窗口则name不能相同。
    
    4.name不能包含含有空格。
  
  - 参数字符串：可选参数，设置窗口参数，各参数用逗号隔开。
  
  - 参数表：
  
    <img src="http://img1.sycdn.imooc.com/52e3677900013d6a05020261.jpg">

- 例：

  window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')

  注意：运行结果考虑浏览器兼容问题。

  ### JS-关闭窗口（window.close）

- close()

- 用法:

  window.close();     或      \<窗口对象>.close();

  例如：关闭新建的窗口。

  var mywin=window.open('http://www.imooc.com');

  mywin.close();

- 注意:上面代码在打开新窗口的同时，关闭该窗口，看不到被打开的窗口。

## DOM

- 文档对象模型DOM(Document Object Model)定义访问和处理HTML文档的标准方法。

  DOM将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。
  
- 将HTML代码分解为DOM系欸但层次图：

  <img src="http://img.mukewang.com/52e4bd0f0001dd8d04830279.jpg">

- HTML文档可以说由节点构成的集合，三种常见的DOM节点：
  - 1.元素节点：上图中\<html>、\<body>、\<p>等都是元素节点，即标签。
  - 2.文本节点：向用户展示的内容，如\<li>...\</li>中的JavaScript、DOM、CSS等文本。
  - 3.属性节点：元素属性，如\<a>标签的链接属性href="http://www.imooc.com"。

- 例：

  \<a href="http://www.imooc.com">JavaScript DOM\</a>

   <img src="http://img.mukewang.com/52e4bdb80001064c04480196.jpg">

### 通过ID获取元素

- 网页由标签将信息组织起来，而标签的id属性值是唯一的。

  在网页中，我们通过id先找到标签，然后进行操作。

- 语法：

  document.getElementById("id");

- 例:

  <img src="http://img.mukewang.com/52e4c5950001054207900423.jpg">

- 结果：null或[object HTMLParagraphElement]

  <img src="http://img.mukewang.com/52e4c6080001734c03800275.jpg">

- 注：获取的元素是一个对象，如想对元素进行操作，我们要通过它的属性或方法。

- 【注意注意】：个人笔记：

  - 练习中的代码是：

    \<p id="con">JavaScript\</p>
    \<script type="text/javascript">
      var mychar=document.getElementById("con");
      document.write("结果:"+mychar); //输出获取的P标签。 
    \</script>

    - 输出结果为[object HTMLParagraphElement]
    - 而示例中的代码结果是null，因为示例中的代码是先执行\<script>,所以是null；练习中是先执行\<p>所以顺序不同结果不同。

### innerHTML属性

- innerHTML 属性用于获取或替换 HTML 元素的内容。

- 语法：

  Object.innerHTML

- 注意：

  1.Object是获取的元素对象，如通过document.getElementById("ID")获取的元素。

  2.注意书写，innerHTML区分大小写。

  通过id="con"获取\<p>元素，并将元素的内容输出和改变元素内容：

  <img src="http://img.mukewang.com/52e4cd080001f01507220418.jpg">

  结果：

  <img src="http://img.mukewang.com/52e4cb5c000187ce03740251.jpg">

### 改变HTML样式

- HTML DOM允许JavaScript改变HTML元素的样式。

- 语法：

  Object.style.property=new style;

  - 注意：Obejct是获取的元素对象，如通过document.getElementById("id");是获取的元素。

- 基本属性表(property)

  <img src="http://img.mukewang.com/52e4d4240001dd6c04850229.jpg" align=left>

  

  - 注意：这只是一小部分CSS样式属性，其它样式也可以通过该方法设置和修改。

- 例：

  改变\<p>元素的样式，将颜色改为红色，字号为改为20，背景颜色改为蓝：

  ```HTML
  <p id="pcon">Hello World!</p>
  <script>
     var mychar = document.getElementById("pcon");
     mychar.style.color="red";
     mychar.style.fontSize="20";
     mychar.style.backgroundColor ="blue";
  </script>
  ```

  结果：

  <img src="http://img.mukewang.com/52e4d6ae000177d203770253.jpg" align=left>

### 显示和隐藏（display属性）

- 网页中经常会看到显示和隐藏的效果，可通过display属性来设置。

- 语法：

  Object.style.display = value ;

- 注意：Object是获取的元素对象

- value取值：

  <img src="http://img.mukewang.com/52e4dba5000179da04110095.jpg">

<img src="http://img.mukewang.com/52e4dcf50001bead09310689.jpg">

- 【个人笔记】这个功能可以用于登录注册页面，提示选项，当用户已经注册，可以点击登录，然后提示文字相应显示。

### 控制类名（className 属性）

- className属性设置或返回元素的class属性

- 语法：

  object.className =classname;

- 作用：

  1.获取元素的class属性

  2.为网页内的某个元素指定一个css样式来更改该元素的外观

- 例：

  获得 \<p> 元素的 class 属性和改变className：

  <img src="http://img.mukewang.com/52e4e28c0001c97f07980838.jpg" align=left>

- 结果：

  <img src="http://img.mukewang.com/52e4e711000135d903810270.jpg" align=left>

## 编程练习

小伙伴们，请编写"改变颜色"、"改变宽高"、"隐藏内容"、"显示内容"、"取消设置"的函数，点击相应按钮执行相应操作，点击"取消设置"按钮后，提示是否取消设置，如是执行操作，否则不做操作。

### 任务

一、定义"改变颜色"的函数

```
提示:
obj.style.color
obj.style.backgroundColor 
```

二、定义"改变宽高"的函数

```
提示:
obj.style.width
obj.style.height 
```

三、定义"隐藏内容"的函数

```
提示:
obj.style.display="none";
```

四、定义"显示内容"的函数

```
提示:
obj.style.display="block";
```

五、定义"取消设置"的函数

```
提示: 
使用confirm()确定框，来确认是否取消设置。
如是将以上所有的设置恢复原始值,否则不做操作。
```

六、当点击相应按钮，执行相应操作，为按钮添加相应事件

### myAnswer

- js_learning_2_7.html

  <!DOCTYPE HTML>

  <html>

  <head>

  <meta http-equiv="Content-Type" Content="text/html; charset=utf-8" />
<title>javascript</title>
  <style type="text/css">

  body{font-size:12px;}

  \#txt{

    height:400px;
    
    width:600px;
    
    border:#333 solid 1px;
    
    padding:5px;}

  p{

    line-height:18px;
    
    text-indent:2em;}

  </style>

  </head>

  <body>

   <h2 id="con">JavaScript课程</H2>
  <div id="txt"> 

   <h5>JavaScript为网页添加动态效果并实现与用户交互的功能。</h5>
          <p>1. JavaScript入门篇，让不懂JS的你，快速了解JS。</p>
        <p>2. JavaScript进阶篇，让你掌握JS的基础语法、函数、数组、事件、内置对象、BOM浏览器、DOM操作。</p>
          <p>3. 学完以上两门基础课后，在深入学习JavaScript的变量作用域、事件、对象、运动、cookie、正则表达式、ajax等课程。</p>
 </div>

 <form>

 <!--当点击相应按钮，执行相应操作，为按钮添加相应事件-->

  <input type="button" value="改变颜色" onclick="changeColor()"> 

  <input type="button" value="改变宽高" onclick="changeHeight()" >

  <input type="button" value="隐藏内容" onclick="hideText()" >

  <input type="button" value="显示内容" onclick="showText()" >

  <input type="button" value="取消设置" onclick="cancelSelect()">

 </form>

  <script type="text/javascript">

//定义"改变颜色"的函数

  function changeColor(){

​    var mytext = document.getElementById("txt");

​    mytext.style.color="red";

  }



//定义"改变宽高"的函数

  function changeHeight(){

​    var mytext = document.getElementById("txt");

​    mytext.style.width="100px";

​    mytext.style.height="200px";

  }



//定义"隐藏内容"的函数

  function hideText(){

​    var mytext = document.getElementById("txt");

​    mytext.style.display="none";

  }



//定义"显示内容"的函数



  function showText(){

​    var mytext = document.getElementById("txt");

​    mytext.style.display="block";

  }

//定义"取消设置"的函数

//使用confirm()确定框来确认是否取消设置。

  function cancelSelect(){

​    var MSG = confirm("确定要取消设置吗?");

​      if (MSG == true) {

​        var mytext =document.getElementById("txt");

​        mytext.style = "txt";

​      }

​      else {

​      }

  }

 </script>

</body>

</html>

<!-- //出现的问题：“取消设置”这个功能没有设置成功，对于className这个属性修改不知道如何操作

//此外，CSS样式中的#txt以及要怎么弄，假如用className来设置要怎么定参数 -->

<!-- function cancelSelect(){

  var message = confirm("确定要取消设置吗？");

  if (message==true){

​    var mytext = document.getElementById("txt");

​    mytext.className="p";

  }

} -->

<!-- //每个function中 都由一个getElementById,这个如果放在全局会更好 -->