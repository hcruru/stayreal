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