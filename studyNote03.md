# JavaScript

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

### JS-输出内容

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