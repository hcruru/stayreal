#  JavaScript进阶篇笔记

https://www.imooc.com/learn/10

## JS基础语法

- HTML文件中引用js文件的方法：

  \<script type="text/javascript" src="javascript.js">\</script>

### 变量

- 变量是用于存储某种/某些数值的存储器。

### 变量命名

- 变量名字可以任意取，但要遵循规则：

  1.必须以字母、下划线或美元符号开头，后面可以跟字母、下划线、美元符号和数字。

  - 正确：

    mysum

    _mychar

    $numal

  - 错误：

    6num   //开头不能用数字

    %sum   //开头不能用除（_ $）外特殊符号，如（% + / 等）

    sum+sum    //开头中间不能使用除（_ $）外特殊符号（% + /）

  2.变量名区分大小写，如:A与a是两个不同变量。

  3.不允许使用JavaScript关键字和保留字做变量名。

  <img src="http://img.mukewang.com/529c07c000014f5103080447.jpg" align=left>

### 变量声明

- 我们要使用盒子装东西,是不是先要找到盒子,那在编程中，这个过程叫声明变量,找盒子的动作。

- 语法：

  var 变量名;

- var相当于找盒子的动作，在JavaScript中是关键字（即保留字），这个关键字的作用是声明变量，并为"变量"准备位置（即内存）。

  var mynum;

- 可以一次声明一个变量，也可以一次声明多个变量，变量之间用","逗号隔开。

  var num1,num2;

  - 注意：变量也可以不声明直接使用，但为了规范，需要先声明后使用。

### 变量赋值

- 把变量看作一个盒子，用盒子来存放物品，

  在变量中存储内容，使用"="号给变量存储内容：

  var mynum = 5 ;

  - 给变量mynum赋值，值为5，另一种写法 

    var mynum;    //声明变量

    mynum=5;     //给变量mynum赋值

- 注：这里"="号是给变量赋值，不是等于号。

- 可以把数值、字符串、布尔值等存储在变量中：

  var num1= 123;

  var num2="一二三";

  var num3=true;

  - num1变量存储的内容是数值；num2变量存储的内容是字符串，字符串需要用一对引号`""`括起来，num3变量存储的内容是布尔值(true、false)。

### 表达式

- 表达式是指具有一定的值、用操作符把常数和变量连接起来的代数式。**一个表达式可以包含常数或变量。**

  num=num+1;

  - 串表达式:

    "I"+"love"+"you"

    "super"+mychar

    注：串表达式中mychar是变量

  - 数值表达式

    num+5*3

    注：数值表达式中num是变量

  - 布尔表达式

    2>3

    num==5

    编写布尔值true或flase的表达式

    注：布尔表达式中num是变量

### +号操作符

- 操作符是用于在JavaScript中指定一定动作的符号。

  （1）操作符

  看下面这段JavaScript代码。

  ```html
  sum = numa + numb;
  ```

  其中的`"="`和`"+"`都是操作符。

  JavaScript中还有很多这样的操作符，例如，算术操作符(+、-、*、/等)，比较操作符(<、>、>=、<=等)，逻辑操作符(&&、||、！)。

  **注意: “=” 操作符是赋值，不是等于。**

  (2) `"+"`操作符

  算术运算符主要用来完成类似加减乘除的工作，在JavaScript中，“+”不只代表加法，还可以连接两个字符串，例如：

  ```
  mystring = "Java" + "Script"; // mystring的值“JavaScript”这个字符串
  ```

### 自加一，自减一 ( ++和- -)

- 算术操作符除了(+、-、*、/)外，还有两个非常常用的操作符，自加一`“++”`；自减一`“--”`。

- ```javascript
  mynum = 10;
  mynum++; //mynum的值变为11
  mynum--; //mynum的值又变回10
  ```

- mynum++使mynum值在原基础上增加1，mynum--使mynum在原基础上减去1,其实也可以写成:

  ```javascript
  mynum = mynum + 1;//等同于mynum++
  mynum = mynum - 1;//等同于mynum--
  ```

### 比较操作符

- 大于号">"是比较操作符
- 当两个操作数通过操作符进行比较，得到值为真（true）和假（false）。
- <img src="http://img.mukewang.com/532a3c150001c65802010207.jpg" align=left>

- ```javascript
  var a = 5;//定义a变量，赋值为5
  var b = 9; //定义b变量，赋值为9
  document.write (a<b); //a小于b的值吗? 结果是真(true)
  document.write (a>=b); //a大于或等于b的值吗? 结果是假(false)
  document.write (a!=b); //a不等于b的值吗? 结果是真(true)
  document.write (a==b); //a等于b的值吗? 结果是假(false)
  ```

### 逻辑与操作符

- 数学里面的“a>b”，在JavaScript中还表示为a>b；数学中的“b大于a，b小于c”是“a<b<c”，那么在JavaScript中可以用&&表示，如下：

  ```javascript
  b>a && b<c    //“&&”是并且的意思, 读法"b大于a"并且" b小于c "
  ```

- “&&”是逻辑与操作符，只有“&&”两边值同时满足(同时为真)，整个表达式值才为真。

- <img src="http://img.mukewang.com/52a16f880001d27803770180.jpg">

  如果A为假，A && B为假，不会在执行B; 反之，如果A为真，要由 B 的值来决定 A && B 的值。

### 逻辑或操作符

- `"||"`逻辑或操作符，相当于生活中的“或者”，当两个条件中有任一个条件满足，“逻辑或”的运算结果就为“真”。

- <img src="http://img.mukewang.com/530a9d2b0001a33e03770178.jpg">

  如果A为真，A || B为真，不会在执行B; 反之，如果A为假，要由 B 的值来决定 A || B 的值。

### 逻辑非操作符

- `"!"`是逻辑非操作符，也就是"不是"的意思,非真即假，非假即真。

- <img src="http://img.mukewang.com/52a1760c000159a702330111.jpg" align=left>

### 操作符优先级

- **操作符之间的优先级（高到低）:**

  算术操作符 → 比较操作符 → 逻辑操作符 → "="赋值符号

  如果同级的运算是按从左到右次序进行,多层括号由里向外。

## 数组

- 数组是一个值的集合，每个值都有一个索引号，从0开始，每个索引都有一个相应的值，根据需要添加更多数值。

### 创建数组

- 语法：

  ```javascript
  var myarray=new Array();
  ```

- <img src="http://img.mukewang.com/52ca004b0001c81103980228.jpg">

- 创建数组的同时，还可以为数组指定长度，长度可任意指定。

  ```javascript
  var myarray= new Array(8); //创建数组，存储8个数据。 
  ```

  **注意：**
  1.创建的新数组是空数组，没有值，如输出，则显示undefined。
  2.虽然创建数组时，指定了长度，但实际上数组都是变长的，也就是说即使指定了长度为8，仍然可以将元素存储在规定长度以外。

### 数组赋值

- **数组的表达方式：**

  ```javascript
  第一步：创建数组var myarr=new Array(); 
  第二步：给数组赋值
          myarr[1]=" 张三";
          myarr[2]=" 李四";
  ```

  下面创建一个数组，用于存储5个人的数学成绩。

  ```javascript
  var myarray=new Array(); //创建一个新的空数组
  myarray[0]=66; //存储第1个人的成绩
  myarray[1]=80; //存储第2个人的成绩
  myarray[2]=90; //存储第3个人的成绩
  myarray[3]=77; //存储第4个人的成绩
  myarray[4]=59; //存储第5个人的成绩
  ```

  **注意：**数组每个值有一个索引号，从0开始。

  我们还可以用简单的方法创建上面的数组和赋值：

  第一种方法：

  ```javascript
  var myarray = new Array(66,80,90,77,59);//创建数组同时赋值
  ```

  第二种方法：

  ```javascript
   var myarray = [66,80,90,77,59];//直接输入一个数组（称 “字面量数组”）
  ```

  **注意：**数组存储的数据可以是任何类型（数字、字符、布尔值等）

### 向数组增加一个新元素

- 使用下一个未用的索引，任何时刻可以不断向数组增加新元素。

  ```javascript
  myarray[5]=88; //使用一个新索引，为数组增加一个新元素
  ```

### 使用数组元素

- 要得到一个数组元素的值，只需引用数组变量并提供一个索引，如：
  **第一个人的成绩表示方法：**`myarray[0]`
  **第三个人的成绩表示方法:** `myarray[2]`

### 数组属性length

- 引用数组的属性length,可以知道数组的大小。

  Length属性表示数组的长度，即数组中元素的个数。

  **语法：**

  ```javascript
  myarray.length; //获得数组myarray的长度
  ```

  **注意：**因为数组的索引总是由0开始，所以一个数组的上下限分别是：0和length-1。如数组的长度是5，数组的上下限分别是0和4。

  ```javascript
  var arr=[55,32,5,90,60,98,76,54];//包含8个数值的数组arr 
  document.write(arr.length); //显示数组长度8
  document.write(arr[7]); //显示第8个元素的值54
  ```

  同时，JavaScript数组的length属性是可变的，这一点需要特别注意。

  ```javascript
  arr.length=10; //增大数组的长度
  document.write(arr.length); //数组长度已经变为10
  ```

  数组随元素的增加，长度也会改变，如下:

  ```javascript
  var arr=[98,76,54,56,76]; // 包含5个数值的数组
  document.write(arr.length); //显示数组的长度5
  arr[15]=34;  //增加元素，使用索引为15,赋值为34
  alert(arr.length); //显示数组的长度16
  ```

### 二维数组

- 一维数组，我们看成一组盒子，每个盒子只能放一个内容。

  ```javascript
  一维数组的表示: myarray[ ]
  ```

  二维数组，我们看成一组盒子，不过每个盒子里还可以放多个盒子。

  ```javascript
  二维数组的表示: myarray[ ][ ]
  ```

  **注意:** 二维数组的两个维度的索引值也是从0开始，两个维度的最后一个索引值为长度-1。 

- **1. 二维数组的定义方法一**

  ```javascript
  var myarr=new Array();  //先声明一维 
  for(var i=0;i<2;i++){   //一维长度为2
     myarr[i]=new Array();  //再声明二维 
     for(var j=0;j<3;j++){   //二维长度为3
     myarr[i][j]=i+j;   // 赋值，每个数组元素的值为i+j
     }
   }
  ```

  <img src="http://img.mukewang.com/537957a20001c24c03200210.jpg">

- 2. **二维数组的定义方法二**

  var Myarr = [[0 , 1 , 2 ],[1 , 2 , 3]]

  **3. 赋值**

  myarr\[0][1]=5; //将5的值传入到数组中，覆盖原有值。

  **说明:** myarr\[0][1]0表示表的行，1表示表的列。

## 流程控制语句

### 判断-if语句

- if语句是基于条件成立才执行相应代码时使用的语句。

- 语法：

  if(条件)
  { 条件成立时执行代码}

### 二选一 -if...else语句

- if...else语句是在指定的条件成立时执行代码，在条件不成立时执行else后的代码。

- 语法：

  ```javascript
  if(条件)
  { 条件成立时执行的代码}
  else
  {条件不成立时执行的代码}
  ```

### 多重判断-if..else嵌套语句

- 要在多组语句中选择一组来执行，使用if..else嵌套语句。

- 语法：

  ```javascript
  if(条件1)
  { 条件1成立时执行的代码}
  else  if(条件2)
  { 条件2成立时执行的代码}
  ...
  else  if(条件n)
  { 条件n成立时执行的代码}
  else
  { 条件1、2至n不成立时执行的代码}
  ```

- <img src="http://img.mukewang.com/541799000001aada05260280.jpg">

### 多种选择-Switch语句

- 当有很多种选项的时候，switch比if else使用更方便。

- 语法：

  ```javascript
  switch(表达式)
  {
  case值1:
    执行代码块 1
    break;
  case值2:
    执行代码块 2
    break;
  ...
  case值n:
    执行代码块 n
    break;
  default:
    与 case值1 、 case值2...case值n 不同时执行的代码
  }
  ```

- 语法说明:

  Switch必须赋初始值，值与每个case值匹配。

  满足执行该 case 后的所有语句，并用break语句来阻止运行下一个case。

  如所有case值都不匹配，执行default后的语句。

  JS中case中表达式与switch后的条件表达式进行全等比较。

- 例：

  假设评价学生的考试成绩，10分满分制，我们按照每一分一个等级将成绩分等，并根据成绩的等级做出不同的评价。

<img src="http://img.mukewang.com/52d1293c0001394705510767.jpg">

- 注意：每一个case后执行的语句的break;不能少

### for循环

- 循环语句，就是重复执行一段代码。

- for语句结构：

  ```javascript
  for(初始化变量;循环条件;循环迭代)
  {     
      循环语句 
   }
  ```

### while循环

- while循环和for循环有相同功能, while循环重复执行一段代码，直到某个条件不再满足。

- while语句结构：

  ```javascript
  while(判断条件)
  {
      循环语句
   }
  ```

### Do...while循环

- do while结构的基本原理和while结构是基本相同的，但是它保证循环体至少被执行一次。因为它是先执行代码，后判断条件，如果条件为真，继续循环。

- **do...while**语句结构:

  ```javascript
  do
  {
      循环语句
   }
  while(判断条件)
  ```

### 退出循环break

- 在while、for、do...while、while循环中使用break语句退出当前循环，直接执行后面的代码。

- 格式：

  ```javascript
  for(初始条件;判断条件;循环后条件值更新)
  {
    if(特殊情况)
    {break;}
    循环代码
  }
  ```

### 继续循环continue

- continue的作用是仅仅跳过本次循环，而整个循环体继续执行。

- 语句结构：

  ```javascript
  for(初始条件;判断条件;循环后条件值更新)
  {
    if(特殊情况)
    { continue; }
   循环代码
  }
  ```

## 函数

- 函数的作用，可以写一次代码，然后反复地重用这个代码。

- 如果要实现8组数的和，就需要16行代码，实现的越多，代码行也就越多。所以我们可以把完成特定功能的代码块放到一个函数里，直接调用这个函数，就省去重复输入大量代码的麻烦。

  **使用函数完成:**

  ```javascript
  function add2(a,b){
  sum = a + b;
   alert(sum);
  } //  只需写一次就可以
  
  add2(3,2);
  add2(7,8);
  ....  //只需调用函数就可以
  ```

### 定义函数

- ```javascript
  function  函数名( )
  {
       函数体;
  }
  ```

### 函数调用

- 函数定义好后，是不能自动执行的，需要调用它,直接在需要的位置写函数名。

  **第一种情况:在标签内调用。**

  ```javascript
    <script type="text/javascript">
      function add2()
      {
           sum = 1 + 1;
           alert(sum);
      }
    add2();//调用函数，直接写函数名。
  </SCRIPT>
  ```

  **第二种情况:**在HTML文件中调用，如通过点击按钮后调用定义好的函数。

  ```javascript
  <html>
  <head>
  <script type="text/javascript">
     function add2()
     {
           sum = 5 + 6;
           alert(sum);
     }
  </script>
  </head>
  <body>
  <form>
  <input type="button" value="click it" onclick="add2()">  //按钮,onclick点击事件，直接写函数名
  </form>
  </body>
  </html>
  ```

### 有参数的函数

- 定义函数还可以如下格式：

  ```javascript
  function 函数名(参数1,参数2)
  {
       函数代码
  }
  ```

  **注意:参数可以多个，根据需要增减参数个数。参数之间用(逗号，）隔开。**

  按照这个格式，函数实现任意两个数的和应该写成：

  ```javascript
  function add2(x,y)
  {
     sum = x + y;
     document.write(sum);
  }
  ```

  x和y则是函数的两个参数，调用函数的时候，我们可通过这两个参数把两个实际的加数传递给函数了。

  例如，add2(3，4)会求3+4的和，add2(60,20)则会求出60和20的和。

### 返回值的函数

- ```javascript
  function add2(x,y)
  {
     sum = x + y;
     return sum; //返回函数值,return后面的值叫做返回值。
  }
  ```

- 还可以通过变量存储调用函数的返回值，代码如下:

  ```javascript
  result = add2(3,4);//语句执行后,result变量中的值为7。
  ```

  **注意:函数中参数和返回值不只是数字，还可以是字符串等其它类型。** 

## 事件响应

- JavaScript 创建动态页面。事件是可以被 JavaScript 侦测到的行为。网页中的每个元素都可以产生某些可以触发 JavaScript 函数或程序的事件。

  比如说，当用户单击按钮或者提交表单数据时，就发生一个鼠标单击（onclick）事件，需要浏览器做出处理，返回给用户一个结果。

- 主要事件表：

  <img src="http://img.mukewang.com/53e198540001b66404860353.jpg">

### 鼠标单击事件( onclick ）

- onclick是鼠标单击事件，当在网页上单击鼠标时，就会发生该事件。同时onclick事件调用的程序块就会被执行，通常与按钮一起使用。

- 比如，我们单击按钮时，触发 onclick 事件，并调用两个数和的函数add2()。代码如下：

  ```javascript
  <html>
  <head>
     <script type="text/javascript">
        function add2(){
          var numa,numb,sum;
          numa=6;
          numb=8;
          sum=numa+numb;
          document.write("两数和为:"+sum);  }
     </script>
  </head>
  <body>
     <form>
        <input name="button" type="button" value="点击提交" onclick="add2()" />
     </form>
  </body>
  </html>
  ```

  **注意:** 在网页中，如使用事件，就在该元素中设置事件属性。 

### 鼠标经过事件（onmouseover）

- 鼠标经过事件，当鼠标移到一个对象上时，该对象就触发onmouseover事件，并执行onmouseover事件调用的程序。

- 例：

  鼠标经过"确定"按钮时，触发onmouseover事件，调用函数info()，弹出消息框，代码如下:

  <img src="http://img.mukewang.com/53e196e500013f1807700354.jpg">

  运行结果：

  <img src="http://img.mukewang.com/53e196fd00017d8704870416.jpg">

### 鼠标移开事件（onmouseout）

- 鼠标移开事件，当鼠标移开当前对象时，执行onmouseout调用的程序。

- 例：

  当把鼠标移动到"登录"按钮上，然后再移开时，触发onmouseout事件，调用函数message()，代码如下:

  <img src="http://img.mukewang.com/53e195580001a0bc07730356.jpg">

  运行结果：

  <img src="http://img.mukewang.com/53e195bf00010d1804760385.jpg">

### 光标聚焦事件（onfocus）

- 当网页中的对象获得聚点时，执行onfocus调用的程序就会被执行。

- 例：

  将光标移到文本框内时，即焦点在文本框内，触发onfocus 事件，并调用函数message()。

  <img src="http://img.mukewang.com/53e19337000113d108390338.jpg">

  运行结果：

  <img src="http://img.mukewang.com/5312c5660001821a04300326.jpg">

### 失焦事件（onblur）

- onblur事件与onfocus是相对事件，当光标离开当前获得聚焦对象的时候，触发onblur事件，同时执行被调用的程序。

- eg:

  网页中有用户和密码两个文本框。当前光标在用户文本框内时（即焦点在文本框），在光标离开该文本框后（即失焦时），触发onblur事件，并调用函数message()。

  <img src="http://img.mukewang.com/53e191d00001dfe508560326.jpg">

  <img src="http://img.mukewang.com/5312da710001968704410319.jpg">

### 内容选中事件（onselect）

- 选中事件，当文本框或者文本域中的文字被选中时，触发onselect事件，同时调用的程序就会被执行。

- eg:

  当选中用户文本框内的文字时，触发onselect 事件，并调用函数message()。

  <img src="http://img.mukewang.com/53e190b70001ffa908560325.jpg">

  <img src="http://img.mukewang.com/5312d7ba00013fff03950319.jpg">

### 文本框内容改变事件（onchange）

- 通过改变文本框的内容来触发onchange事件，同时执行被调用的程序。

- eg:

  当用户将文本框内的文字改变后，弹出对话框“您改变了文本内容！”。

  <img src="http://img.mukewang.com/5312d59c00011cd311490444.jpg">

  <img src="http://img.mukewang.com/5312d5c600012c3703960319.jpg">

### 加载事件（onload）

- 事件会在页面加载完成后，立即发生，同时执行被调用的程序。
  注意：

  1. 加载页面时，触发onload事件，事件写在\<body>标签内。

  2. 此节的加载页面，可理解为打开一个新页面时。

- eg:当加载一个新页面时，弹出对话框“加载中，请稍等…”。

  <img src="http://img.mukewang.com/5312e3c10001bd9908920372.jpg">

  <img src="http://img.mukewang.com/5312e3eb0001e8a103930318.jpg">

### 卸载事件（onunload）

- 当用户退出页面时（页面关闭、页面刷新等），触发onUnload事件，同时执行被调用的程序。

  **注意：不同浏览器对onunload事件支持不同。**

- eg:

  当退出页面时，弹出对话框“您确定离开该网页吗？”。

  <img src="http://img.mukewang.com/5312ee6b0001f89408950418.jpg">

  <img src="http://img.mukewang.com/546470c90001583205460464.jpg">

- 个人记录：

  这里实际操作过程中有个问题：

  刷新进入网站会显示弹窗，但是关闭页面时不会显示，评论中给的解答是这样的：

  <img src="https://img1.mukewang.com/5b2224b800019fa105000451.jpg">

## 内置对象

- JavaScript 中的所有事物都是对象，如:字符串、数值、数组、函数等，每个对象带有**属性**和**方法**。

  **对象的属性：**反映该对象某些特定的性质的，如：字符串的长度、图像的长宽等；

  **对象的方法：**能够在对象上执行的动作。例如，表单的“提交”(Submit)，时间的“获取”(getYear)等；

  JavaScript 提供多个内建对象，比如 String、Date、Array 等等，使用对象前先定义，如下使用数组对象：

  ```javascript
    var objectName =new Array();//使用new关键字定义对象
  或者
    var objectName =[];
  ```

  **访问对象属性的语法:**

  ```javascript
  objectName.propertyName
  ```

  如使用 Array 对象的 length 属性来获得数组的长度：

  ```javascript
  var myarray=new Array(6);//定义数组对象
  var myl=myarray.length;//访问数组长度length属性
  ```

  **以上代码执行后，myl的值将是：6**

  **访问对象的方法：**

  ```javascript
  objectName.methodName()
  ```

  如使用string 对象的 toUpperCase() 方法来将文本转换为大写：

  ```javascript
  var mystr="Hello world!";//创建一个字符串
  var request=mystr.toUpperCase(); //使用字符串对象方法
  ```

  以上代码执行后，request的值是**：HELLO WORLD!**

### Date日期对象

- 日期对象可以储存任意一个日期，并且可以精确到毫秒数（1/1000 秒）。

  定义一个时间对象 :

  ```javascript
  var Udate=new Date(); 
  ```

  **注意**:使用关键字new，Date()的首字母必须大写。 

  使 Udate 成为日期对象，并且已有初始值：**当前时间(当前电脑系统时间)**。

  如果要自定义初始值，可以用以下方法：

  ```javascript
  var d = new Date(2012, 10, 1);  //2012年10月1日
  var d = new Date('Oct 1, 2012'); //2012年10月1日
  ```

  我们最好使用下面介绍的“方法”来严格定义时间。

  **访问方法语法：**“<日期对象>.<方法>”

  Date对象中处理时间和日期的常用方法：

  <img src="http://img.mukewang.com/555c650d0001ae7b04180297.jpg">

### 返回/设置年份方法

#### get/setFullYear()

- 返回/设置年份，用四位数表示。

  ```javascript
  var mydate=new Date();//当前时间2020年2月1日
  document.write(mydate+"<br>");//输出当前时间
  document.write(mydate.getFullYear()+"<br>");//输出当前年份
  mydate.setFullYear(81); //设置年份
  document.write(mydate+"<br>"); //输出年份被设定为 0081年。
  ```

  **注意:**不同浏览器， mydate.setFullYear(81)结果不同，年份被设定为 0081或81两种情况。

  **结果:**

  ```javascript
  Thu Mar 06 2014 10:57:47 GMT+0800
  2014
  Thu Mar 06 0081 10:57:47 GMT+0800
  ```

  **注意:**

  1.结果格式依次为：星期、月、日、年、时、分、秒、时区。(火狐浏览器)

  2.不同浏览器，时间格式有差异。

### 返回星期方法

#### getDay()

-  返回星期，返回的是0-6的数字，0 表示星期天。如果要返回相对应“星期”，通过数组完成，代码如下:

  ```javascript
  <script type="text/javascript">
    var mydate=new Date();//定义日期对象
    var weekday=["星期日","星期一","星期二","星期三","星期四","星期五","星期六"];
  //定义数组对象,给每个数组项赋值
    var mynum=mydate.getDay();//返回值存储在变量mynum中
    document.write(mydate.getDay());//输出getDay()获取值
    document.write("今天是："+ weekday[mynum]);//输出星期几
  </script>
  ```

  注意：以上代码是在2014年3月7日，星期五运行。

  **结果:**

  5

  今天是：星期五

### 返回/设置时间方法

#### get/setTime() 

- 返回/设置时间，单位毫秒数，计算从 1970 年 1 月 1 日零时到日期对象所指的日期的毫秒数。

- 如果将目前日期对象的时间推迟1小时，代码如下:

  ```javascript
  <script type="text/javascript">
    var mydate=new Date();
    document.write("当前时间："+mydate+"<br>");
    mydate.setTime(mydate.getTime() + 60 * 60 * 1000);
    document.write("推迟一小时时间：" + mydate);
  </script>
  ```

  **结果:**

  当前时间：Thu Mar 6 11:46:27 UTC+0800 2014

  推迟一小时时间：Thu Mar 6 12:46:27 UTC+0800 2014

  **注意:**

  1. 一小时 60 分，一分 60 秒，一秒 1000 毫秒

  2. 时间推迟 1 小时,就是: “x.setTime(x.getTime() + 60 * 60 * 1000);”

### String 字符串对象

- 定义字符串的方法就是直接赋值。

  ```javascript
  var mystr = "I love JavaScript!"
  ```

  定义mystr字符串后，我们就可以访问它的属性和方法。

  **访问字符串对象的属性length:**

  stringObject.length; 返回该字符串的长度。

  ```javascript
  var mystr="Hello World!";
  var myl=mystr.length;
  ```

  以上代码执行后，myl 的值将是：12

  **访问字符串对象的方法：**

  使用 String 对象的 toUpperCase() 方法来将字符串小写字母转换为大写：

  ```javascript
  var mystr="Hello world!";
  var mynum=mystr.toUpperCase();
  以上代码执行后，mynum 的值是：HELLO WORLD!
  ```

- 变成小写：toLowerCase()方法

### 返回指定位置的字符

#### charAt()

- charAt() 方法可返回指定位置的字符。返回的字符是长度为 1 的字符串。

  **语法:**

  ```javascript
  stringObject.charAt(index)
  ```

  **参数说明：**

  <img src="http://img.mukewang.com/53251a310001cf1e03370092.jpg">

  **注意**：

  1.字符串中第一个字符的下标是 0。最后一个字符的下标为字符串长度减一（string.length-1）。

  2.如果参数 index 不在 0 与 string.length-1 之间，该方法将返回一个空字符串。

  **如:**在字符串 "I love JavaScript!" 中，返回位置2的字符：
  
  ```javascript
  <script type="text/javascript">
    var mystr="I love JavaScript!"
    document.write(mystr.charAt(2));
</script>
  ```

  **注意：**一个空格也算一个字符。

  以上代码的运行结果：
  
  ```javascript
  l
  ```

### 返回指定的字符串首次出现的位置

#### indexOf() 

- indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。

  **语法**

  ```javascript
  stringObject.indexOf(substring, startpos)
  ```

  **参数说明：**

  <img src="http://img1.sycdn.imooc.com/53853d4200019feb04920149.jpg">

  **说明：**

  1.该方法将从头到尾地检索字符串 stringObject，看它是否含有子串 substring。

  2.可选参数，从stringObject的startpos位置开始查找substring，如果没有此参数将从stringObject的开始位置查找。

  3.如果找到一个 substring，则返回 substring 的第一次出现的位置。stringObject 中的字符位置是从 0 开始的。

  **注意：**

  1.indexOf() 方法区分大小写。

  2.如果要检索的字符串值没有出现，则该方法返回 -1。

  例如: 对 "I love JavaScript!" 字符串内进行不同的检索：

  ```javascript
  <script type="text/javascript">
    var str="I love JavaScript!"
    document.write(str.indexOf("I") + "<br />");
    document.write(str.indexOf("v") + "<br />");
    document.write(str.indexOf("v",8));
  </script>
  ```

  以上代码的输出：

  ```javascript
  0
  4
  9
  ```

### 字符串分割split()

- split() 方法将字符串分割为字符串数组，并返回此数组。

  **语法：**

  ```javascript
  stringObject.split(separator,limit)
  ```

  **参数说明:**

  <img src="http://img1.sycdn.imooc.com/532bee4800014c0404230108.jpg">

  **注意：**如果把空字符串 ("") 用作 separator，那么 stringObject 中的每个字符之间都会被分割。

  **我们将按照不同的方式来分割字符串：**

  使用指定符号分割字符串，代码如下:

  ```javascript
  var mystr = "www.imooc.com";
  document.write(mystr.split(".")+"<br>");
  document.write(mystr.split(".", 2)+"<br>");
  ```

  **运行结果:**

  ```javascript
  www,imooc,com
  www,imooc
  ```

  将字符串分割为字符，代码如下：

  ```javascript
  document.write(mystr.split("")+"<br>");
  document.write(mystr.split("", 5));
  ```

  运行结果:

  ```javascript
  w,w,w,.,i,m,o,o,c,.,c,o,m
  w,w,w,.,i
  ```

### 提取字符串substring()

- substring() 方法用于提取字符串中介于两个指定下标之间的字符。

  **语法:**

  ```
  stringObject.substring(startPos,stopPos) 
  ```

  **参数说明:**

  <img src="http://img1.sycdn.imooc.com/532bf1bb000151af04450082.jpg">

  **注意：**

  1. 返回的内容是从 start开始(包含start位置的字符)到 stop-1 处的所有字符，其长度为 stop 减start。

  2. 如果参数 start 与 stop 相等，那么该方法返回的就是一个空串（即长度为 0 的字符串）。

  3. 如果 start 比 stop 大，那么该方法在提取子串之前会先交换这两个参数。

  使用 substring() 从字符串中提取字符串，代码如下：

  ```javascript
  <script type="text/javascript">
    var mystr="I love JavaScript";
    document.write(mystr.substring(7));
    document.write(mystr.substring(2,6));
  </script>
  ```

  **运行结果**:

  ```javascript
  JavaScript
  love
  ```

### 提取指定数目的字符substr()

- substr() 方法从字符串中提取从 startPos位置开始的指定数目的字符串。

  **语法:**

  ```javascript
  stringObject.substr(startPos,length)
  ```

  **参数说明:**

  <img src="http://img1.sycdn.imooc.com/532bf2e00001105305100098.jpg">

  **注意：**如果参数startPos是负数，从字符串的尾部开始算起的位置。也就是说，-1 指字符串中最后一个字符，-2 指倒数第二个字符，以此类推。

  如果startPos为负数且绝对值大于字符串长度，startPos为0。

  使用 substr() 从字符串中提取一些字符，代码如下：

  ```javascript
  <script type="text/javascript">
    var mystr="I love JavaScript!";
    document.write(mystr.substr(7));
    document.write(mystr.substr(2,4));
  </script>
  ```

  **运行结果：**

  ```javascript
  JavaScript!
  love
  ```

### Math对象

- Math对象，提供对数据的数学计算。

  使用 Math 的属性和方法，代码如下：

  ```javascript
  <script type="text/javascript">
    var mypi=Math.PI; 
    var myabs=Math.abs(-15);
    document.write(mypi);
    document.write(myabs);
  </script>
  ```

  **运行结果**:

  ```javascript
  3.141592653589793
  15
  ```

  **注意：**

  Math 对象是一个固有的对象，无需创建它，直接把 Math 作为对象使用就可以调用其所有属性和方法。这是它与Date,String对象的区别。

  Math 对象属性

  <img src="http://img1.sycdn.imooc.com/532fe7cf0001e7b505170269.jpg">

  Math 对象方法

  <img src="http://img1.sycdn.imooc.com/532fe841000174db05160622.jpg">

### 向上取整ceil()

- ceil() 方法可对一个数进行向上取整。

  **语法:**

  ```
  Math.ceil(x)
  ```

  **参数说明:**

  <img src="http://img1.sycdn.imooc.com/532fe8e00001e4e605230063.jpg">

  **注意：**

  它返回的是大于或等于x，并且与x最接近的整数。

  我们将把 ceil() 方法运用到不同的数字上，代码如下：

  ```javascript
  <script type="text/javascript">
    document.write(Math.ceil(0.8) + "<br />")
    document.write(Math.ceil(6.3) + "<br />")
    document.write(Math.ceil(5) + "<br />")
    document.write(Math.ceil(3.5) + "<br />")
    document.write(Math.ceil(-5.1) + "<br />")
    document.write(Math.ceil(-5.9))
  </script>
  ```

  **运行结果：**

  ```javascript
  1
  7
  5
  4
  -5
  -5
  ```

### 向下取整floor()

- floor() 方法可对一个数进行向下取整。

  **语法:**

  ```
  Math.floor(x)
  ```

  **参数说明：**

  <img src="http://img1.sycdn.imooc.com/532fe8e00001e4e605230063.jpg">

  **注意：**返回的是小于或等于x，并且与 x 最接近的整数。

  我们将在不同的数字上使用 floor() 方法，代码如下:

  ```javascript
  <script type="text/javascript">
    document.write(Math.floor(0.8)+ "<br>")
    document.write(Math.floor(6.3)+ "<br>")
    document.write(Math.floor(5)+ "<br>")
    document.write(Math.floor(3.5)+ "<br>")
    document.write(Math.floor(-5.1)+ "<br>")
    document.write(Math.floor(-5.9))
  </script>
  ```

  **运行结果：**

  ```javascript
  0
  6
  5
  3
  -6
  -6
  ```

### 四舍五入round()

- round() 方法可把一个数字四舍五入为最接近的整数。

  **语法:**

  ```
  Math.round(x)
  ```

  **参数说明：**

  <img src="http://img1.sycdn.imooc.com/532feb70000180ab03210059.jpg">

  **注意：**

  1. 返回与 x 最接近的整数。

  2. 对于 0.5，该方法将进行上舍入。(5.5 将舍入为 6)

  3. 如果 x 与两侧整数同等接近，则结果接近 +∞方向的数字值 。(如 -5.5 将舍入为 -5; -5.52 将舍入为 -6),如下图:

  <img src="http://img1.sycdn.imooc.com/53fc4cc8000169a907530196.jpg">

  把不同的数舍入为最接近的整数,代码如下：

  ```javascript
  <script type="text/javascript">
    document.write(Math.round(1.6)+ "<br>");
    document.write(Math.round(2.5)+ "<br>");
    document.write(Math.round(0.49)+ "<br>");
    document.write(Math.round(-6.4)+ "<br>");
    document.write(Math.round(-6.6));
  </script>
  ```

  **运行结果：**

  ```javascript
  2
  3
  0
  -6
  -7
  ```

### 随机数 random()

- ```javascript
  random() 方法可返回介于 0 ~ 1（大于或等于 0 但小于 1 )之间的一个随机数。
  ```

  **语法：**

  ```javascript
  Math.random();
  ```

  **注意：**返回一个大于或等于 0 但小于 1 的符号为正的数字值。

  我们取得介于 0 到 1 之间的一个随机数，代码如下：

  ```javascript
  <script type="text/javascript">
    document.write(Math.random());
  </script>
  ```

  **运行结果：**

  ```javascript
  0.190305486195328  
  ```

  **注意**:

  因为是随机数，所以每次运行结果不一样，但是0 ~ 1的数值。

  获得0 ~ 10之间的随机数，代码如下:

  ```javascript
  <script type="text/javascript">
    document.write((Math.random())*10);
  </script>
  ```

  **运行结果：**

  ```javascript
  8.72153625893887
  ```

### Array 数组对象

- 数组对象是一个对象的集合，里边的对象可以是不同类型的。数组的每一个成员对象都有一个“下标”，用来表示它在数组中的位置，是从零开始的

  **数组定义的方法：**

  1.定义了一个空数组:

  ```javascript
  var  数组名= new Array();
  ```

  2.定义时指定有n个空元素的数组：

  ```javascript
  var 数组名 =new Array(n);
  ```

  3.定义数组的时候，直接初始化数据：

  ```javascript
  var  数组名 = [<元素1>, <元素2>, <元素3>...];
  ```

  我们定义myArray数组，并赋值，**代码如下：**

  ```javascript
  var myArray = [2, 8, 6]; 
  ```

  **说明：**定义了一个数组 myArray，里边的元素是：myArray[0] = 2; myArray[1] = 8; myArray[2] = 6。

  **数组元素使用：**

  ```javascript
  数组名[下标] = 值;
  ```

  **注意**: 数组的下标用方括号括起来，从0开始。

  **数组属性：**

  length 用法：<数组对象>.length；返回：数组的长度，即数组里有多少个元素。它等于数组里最后一个元素的下标加一。

  **数组方法：**

  <img src="http://img.mukewang.com/533295ab0001dead05190599.jpg">

#### 数组连接concat()

- concat() 方法用于连接两个或多个数组。此方法返回一个新数组，不改变原来的数组。

  **语法**

  ```
  arrayObject.concat(array1,array2,...,arrayN)
  ```

  **参数说明：**

  <img src="http://img.mukewang.com/5332968d0001d39b05010137.jpg">

  **注意:** 

  该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。

  我们创建一个数组，将把 concat() 中的参数连接到数组 myarr 中，代码如下：

  ```javascript
  <script type="text/javascript">
    var mya = new Array(3);
    mya[0] = "1";
    mya[1] = "2";
    mya[2] = "3";
    document.write(mya.concat(4,5)+"<br>");
    document.write(mya); 
  </script>
  ```

  **运行结果：**

  ```javascript
  1,2,3,4,5
  1,2,3
  ```

  我们创建了三个数组，然后使用 concat() 把它们连接起来，代码如下：

  ```javascript
  <script type="text/javascript">
    var mya1= new Array("hello!")
    var mya2= new Array("I","love");
    var mya3= new Array("JavaScript","!");
    var mya4=mya1.concat(mya2,mya3);
    document.write(mya4);
  </script>
  ```

  **运行结果：**

  ```javascript
  hello!,I,love,JavaScript,!
  ```

#### 指定分隔符连接数组元素join()

- join()方法用于把数组中的所有元素放入一个字符串。元素是通过指定的分隔符进行分隔的。

  **语法：**

  ```
  arrayObject.join(分隔符)
  ```

  **参数说明:**

  <img src="http://img.mukewang.com/533297ff0001516905150059.jpg">

  注意：

  返回一个字符串，该字符串把数组中的各个元素串起来，用<分隔符>置于元素与元素之间。这个方法不影响数组原本的内容。 我们使用join（）方法，将数组的所有元素放入一个字符串中，代码如下：

  ```javascript
  <script type="text/javascript">
    var myarr = new Array(3);
    myarr[0] = "I";
    myarr[1] = "love";
    myarr[2] = "JavaScript";
    document.write(myarr.join());
  </script>
  ```

  **运行结果：**

  ```javascript
  I,love,JavaScript
  ```

  我们将使用分隔符来分隔数组中的元素，代码如下：

  ```javascript
  <script type="text/javascript">
    var myarr = new Array(3)
    myarr[0] = "I";
    myarr[1] = "love";
    myarr[2] = "JavaScript";
    document.write(myarr.join("."));
  </script>
  ```

  **运行结果：**

  ```javascript
  I.love.JavaScript
  ```

#### 颠倒数组元素顺序reverse()

- reverse() 方法用于颠倒数组中元素的顺序。

  **语法：**

  ```javascript
  arrayObject.reverse()
  ```

  **注意：**该方法会改变原来的数组，而不会创建新的数组。

  定义数组myarr并赋值，然后颠倒其元素的顺序：

  ```javascript
  <script type="text/javascript">
    var myarr = new Array(3)
    myarr[0] = "1"
    myarr[1] = "2"
    myarr[2] = "3"
    document.write(myarr + "<br />")
    document.write(myarr.reverse())
  </script>
  ```

  **运行结果：**

  ```javascript
  1,2,3
  3,2,1
  ```

#### 选定元素slice()

- slice() 方法可从已有的数组中返回选定的元素。

  **语法**

  ```javascript
  arrayObject.slice(start,end)
  ```

  **参数说明：**

  <img src="http://img.mukewang.com/533299680001637b05160145.jpg">

  1.返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。

  2.该方法并不会修改数组，而是返回一个子数组。

  **注意：**

  1. 可使用负值从数组的尾部选取元素。

     2.如果 end 未被规定，那么 slice() 方法会选取从 start 到数组结尾的所有元素。

  3. String.slice() 与 Array.slice() 相似。

  我们将创建一个新数组，然后从其中选取的元素，代码如下：

  ```javascript
  <script type="text/javascript">
    var myarr = new Array(1,2,3,4,5,6);
    document.write(myarr + "<br>");
    document.write(myarr.slice(2,4) + "<br>");
    document.write(myarr);
  </script>
  ```

  **运行结果：**

  ```javascript
  1,2,3,4,5,6
  3,4
  1,2,3,4,5,6
  ```

#### 数组排序sort()

- **sort()**方法使数组中的元素按照一定的顺序排列。

  **语法:**

  ```
  arrayObject.sort(方法函数)
  ```

  **参数说明：**

  <img src="http://img.mukewang.com/53329a2a000127f705170060.jpg">

  1.如果不指定<方法函数>，则按unicode码顺序排列。

  2.如果指定<方法函数>，则按<方法函数>所指定的排序方法排序。

  ```javascript
  myArray.sort(sortMethod);
  ```

  **注意:** 该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比较函数应该具有两个参数 a 和 b，其返回值如下： 

   若返回值<=-1，则表示 A 在排序后的序列中出现在 B 之前。
   若返回值>-1 && <1，则表示 A 和 B 具有相同的排序顺序。
   若返回值>=1，则表示 A 在排序后的序列中出现在 B 之后。

  1.使用sort()将数组进行排序，代码如下：

  ```javascript
  <script type="text/javascript">
    var myarr1 = new Array("Hello","John","love","JavaScript"); 
    var myarr2 = new Array("80","16","50","6","100","1");
    document.write(myarr1.sort()+"<br>");
    document.write(myarr2.sort());
  </script>
  ```

  **运行结果：**

  ```javascript
  Hello,JavaScript,John,love
  1,100,16,50,6,80
  ```

  **注意:上面的代码没有按照数值的大小对数字进行排序。**

  **2.如要实现这一点，就必须使用一个排序函数，代码如下：**

  ```javascript
  <script type="text/javascript">
    function sortNum(a,b) {
    return a - b;
   //升序，如降序，把“a - b”该成“b - a”
  }
   var myarr = new Array("80","16","50","6","100","1");
    document.write(myarr + "<br>");
    document.write(myarr.sort(sortNum));
  </script>
  ```

  **运行结果：**

  ```javascript
  80,16,50,6,100,1
  1,6,16,50,80,100
  ```

- 个人笔记:

  这里有个不是很明白的点:既然是传值，数组中有那么多个值，是这个sort函数内置了进行逐个比较吗？否则如何根据两个数得到返回值进行比较，是因为内置函数的原因吗？不需要我们考虑原理，只要使用就可以。

## 浏览器对象

### window对象

- window对象是BOM的核心，window对象指当前的浏览器窗口。

- **window对象方法:**
- <img src="http://img.mukewang.com/535483720001a54506670563.jpg">

### JavaScript 计时器

- 在JavaScript中，我们可以在设定的时间间隔之后来执行代码，而不是在函数被调用后立即执行。
  **计时器类型：**
  一次性计时器：仅在指定的延迟时间之后触发一次。
  间隔性触发计时器：每隔一定的时间间隔就触发一次。
  **计时器方法：**

  <img src="http://img.mukewang.com/56976e1700014fc504090143.jpg">

### 计时器setInterval()

- 在执行时,从载入页面后每隔指定的时间执行代码。

  **语法:**

  ```javascript
  setInterval(代码,交互时间);
  ```

  **参数说明：**

  1. 代码：要调用的函数或要执行的代码串。

  2. 交互时间：周期性执行或调用表达式之间的时间间隔，以毫秒计（1s=1000ms）。

  **返回值:**

  一个可以传递给 clearInterval() 从而取消对"代码"的周期性执行的值。

  **调用函数格式(**假设有一个clock()函数**):**

  ```javascript
  setInterval("clock()",1000)
  或
  setInterval(clock,1000)
  ```

  我们设置一个计时器，每隔100毫秒调用clock()函数，并将时间显示出来，**代码如下:**

  ```javascript
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>计时器</title>
  <script type="text/javascript">
    var int=setInterval(clock, 100)
    function clock(){
      var time=new Date();
      document.getElementById("clock").value = time;
    }
  </script>
  </head>
  <body>
    <form>
      <input type="text" id="clock" size="50"  />
    </form>
  </body>
  </html>
  ```

### 取消计时器clearInterval()

- clearInterval() 方法可取消由 setInterval() 设置的交互时间。

  **语法：**

  ```javascript
  clearInterval(id_of_setInterval)
  ```

  **参数说明:**
  id_of_setInterval：由 setInterval() 返回的 ID 值。

  每隔 100 毫秒调用 clock() 函数,并显示时间。当点击按钮时，停止时间,代码如下:

  ```javascript
  <!DOCTYPE HTML>
  <html>
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <title>计时器</title>
  <script type="text/javascript">
     function clock(){
        var time=new Date();                     
        document.getElementById("clock").value = time;
     }
  // 每隔100毫秒调用clock函数，并将返回值赋值给i
       var i=setInterval("clock()",100);
  </script>
  </head>
  <body>
    <form>
      <input type="text" id="clock" size="50"  />
      <input type="button" value="Stop" onclick="clearInterval(i)"  />
    </form>
  </body>
  </html>
  ```

### 计时器setTimeout()

- setTimeout()计时器，在载入后延迟指定时间后,去执行一次表达式,仅执行一次。

  **语法:**

  ```
  setTimeout(代码,延迟时间);
  ```

  **参数说明：**

  1. 要调用的函数或要执行的代码串。
  2. 延时时间：在执行代码前需等待的时间，以毫秒为单位（1s=1000ms)。

  当我们打开网页3秒后，在弹出一个提示框，**代码如下:**

  ```javascript
  <!DOCTYPE HTML>
  <html>
  <head>
  <script type="text/javascript">
    setTimeout("alert('Hello!')", 3000 );
  </script>
  </head>
  <body>
  </body>
  </html>
  ```

  当按钮start被点击时，setTimeout()调用函数，在5秒后弹出一个提示框。

  ```javascript
  <!DOCTYPE HTML>
  <html>
  <head>
  <script type="text/javascript">
  function tinfo(){
    var t=setTimeout("alert('Hello!')",5000);
   }
  </script>
  </head>
  <body>
  <form>
    <input type="button" value="start" onClick="tinfo()">
  </form>
  </body>
  </html>
  ```

  要创建一个运行于无穷循环中的计数器，我们需要编写一个函数来调用其自身。在下面的代码，当按钮被点击后，输入域便从0开始计数。

  ```javascript
  <!DOCTYPE HTML>
  <html>
  <head>
  <script type="text/javascript">
  var num=0;
  function numCount(){
   document.getElementById('txt').value=num;
   num=num+1;
   setTimeout("numCount()",1000);
   }
  </script>
  </head>
  <body>
  <form>
  <input type="text" id="txt" />
  <input type="button" value="Start" onClick="numCount()" />
  </form>
  </body>
  </html>
  ```

- 个人笔记：

  这里自己做的练习有问题：

  1.忘记函数外调用函数，所以input框不显示计时

  2.是<script></script>标签一开始放在<from>之间，<input>之前，

    由于编译器是由上至下解析,所以JS代码无法获取到input的id，

    所以不能正常运行，应该放在</from>标签之后,</body>之前

### 取消计时器clearTimeout()

- setTimeout()和clearTimeout()一起使用，停止计时器。

  **语法:**

  ```javascript
  clearTimeout(id_of_setTimeout)
  ```

  **参数说明:**
  **id_of_setTimeout：**由 setTimeout() 返回的 ID 值。该值标识要取消的延迟执行代码块。

  下面的例子和上节的无穷循环的例子相似。唯一不同是，现在我们添加了一个 "Stop" 按钮来停止这个计数器：

  ```javascript
  <!DOCTYPE HTML>
  <html>
  <head>
  <script type="text/javascript">
    var num=0,i;
    function timedCount(){
      document.getElementById('txt').value=num;
      num=num+1;
      i=setTimeout(timedCount,1000);
    }
      setTimeout(timedCount,1000);
    function stopCount(){
      clearTimeout(i);
    }
  </script>
  </head>
  <body>
    <form>
      <input type="text" id="txt">
      <input type="button" value="Stop" onClick="stopCount()">
    </form>
  </body>
  </html>
  ```

### History 对象

- history对象记录了用户曾经浏览过的页面(URL)，并可以实现浏览器前进与后退相似导航的功能。

  **注意:从窗口被打开的那一刻开始记录，每个浏览器窗口、每个标签页乃至每个框架，都有自己的history对象与特定的window对象关联。**

  **语法：**

  ```javascript
  window.history.[属性|方法]
  ```

  **注意：**window可以省略。

  **History 对象属性**

  <img src="http://img.mukewang.com/53548c030001759e05840068.jpg">

  **History 对象方法**

  <img src="http://img.mukewang.com/53548c200001228206210123.jpg">

  使用length属性，当前窗口的浏览历史总长度，**代码如下：**

  ```javascript
  <script type="text/javascript">
    var HL = window.history.length;
    document.write(HL);
  </script>
  ```

### 返回前一个浏览的页面

- back()方法，加载 history 列表中的前一个 URL。

  **语法：**

  ```javascript
  window.history.back();
  ```

  比如，返回前一个浏览的页面，**代码如下：**

  ```javascript
  window.history.back();
  ```

  **注意：等同于点击浏览器的倒退按钮。**

  back()相当于go(-1),**代码如下:**

  ```javascript
  window.history.go(-1);
  ```

### 返回下一个浏览的页面

- forward()方法，加载 history 列表中的下一个 URL。

  如果倒退之后，再想回到倒退之前浏览的页面，则可以使用forward()方法,**代码如下:**

  ```javascript
  window.history.forward();
  ```

  **注意：等价点击前进按钮。**

  forward()相当于go(1),**代码如下:**

  ```javascript
  window.history.go(1);
  ```

### 返回浏览历史中的其他页面

- go()方法，根据当前所处的页面，加载 history 列表中的某个具体的页面。

  **语法：**

  ```
  window.history.go(number);
  ```

  **参数：**

  <img src="http://img.mukewang.com/5354947e00011a9a06490153.jpg">

  浏览器中，返回当前页面之前浏览过的第二个历史页面，**代码如下：**

  ```javascript
  window.history.go(-2);
  ```

  **注意：和在浏览器中单击两次后退按钮操作一样。**

  同理，返回当前页面之后浏览过的第三个历史页面，**代码如下：**

  ```javascript
  window.history.go(3);
  ```

### Location对象

- location用于获取或设置窗体的URL，并且可以用于解析URL。

  **语法:**

  ```javascript
  location.[属性|方法]
  ```

  **location对象属性图示:**

  <img src="http://img.mukewang.com/53605c5a0001b26909900216.jpg">

  **location 对象属性：**

  <img src="http://img.mukewang.com/5354b1d00001c4ec06220271.jpg">

  **location 对象方法:**

  <img src="http://img.mukewang.com/5354b1eb00016a2405170126.jpg">

### Navigator对象

- Navigator 对象包含有关浏览器的信息，通常用于检测浏览器与操作系统的版本。

  **对象属性:**

  <img src="http://img.mukewang.com/5354cff70001428b06880190.jpg">

  查看浏览器的名称和版本，**代码如下:**

  ```javascript
  <script type="text/javascript">
     var browser=navigator.appName;
     var b_version=navigator.appVersion;
     document.write("Browser name"+browser);
     document.write("<br>");
     document.write("Browser version"+b_version);
  </script>
  ```

### userAgent

- 返回用户代理头的字符串表示(就是包括浏览器版本信息等的字符串)

  **语法**

  ```javascript
  navigator.userAgent
  ```

  几种浏览的user_agent.，像360的兼容模式用的是IE、极速模式用的是chrom的内核。

  <img src="http://img.mukewang.com/535a3a4a0001e03f06870189.jpg">

  使用userAgent判断使用的是什么浏览器(假设使用的是IE8浏览器),**代码如下:**

  ```javascript
  function validB(){ 
    var u_agent = navigator.userAgent; 
    var B_name="Failed to identify the browser"; 
    if(u_agent.indexOf("Firefox")>-1){ 
        B_name="Firefox"; 
    }else if(u_agent.indexOf("Chrome")>-1){ 
        B_name="Chrome"; 
    }else if(u_agent.indexOf("MSIE")>-1&&u_agent.indexOf("Trident")>-1){ 
        B_name="IE(8-10)";  
    }
      document.write("B_name:"+B_name+"<br>");
      document.write("u_agent:"+u_agent+"<br>"); 
  } 
  ```

  **运行结果:**

  <img src="http://img.mukewang.com/535dea1e00017b0b06880265.jpg">

### screen对象

- screen对象用于获取用户的屏幕信息。

  **语法：**

  ```javascript
  window.screen.属性
  ```

  **对象属性:**

  <img src="http://img.mukewang.com/5354d2810001a47706210213.jpg">

### 屏幕分辨率的高和宽

- window.screen 对象包含有关用户屏幕的信息。

  1. screen.height 返回屏幕分辨率的高

  2. screen.width 返回屏幕分辨率的宽

     **注意:**

     1.单位以像素计。

     2.window.screen 对象在编写时可以不使用 window 这个前缀。
     我们来获取屏幕的高和宽，代码如下:

  ```javascript
  <script type="text/javascript">
    document.write( "屏幕宽度："+screen.width+"px<br />" );
    document.write( "屏幕高度："+screen.height+"px<br />" );
  </script>
  ```

### 屏幕可用高和宽度

- 1. screen.availWidth 属性返回访问者屏幕的宽度，以像素计，减去界面特性，比如任务栏。

  2. screen.availHeight 属性返回访问者屏幕的高度，以像素计，减去界面特性，比如任务栏。

  **注意:**

  不同系统的任务栏默认高度不一样，及任务栏的位置可在屏幕上下左右任何位置，所以有可能可用宽度和高度不一样。

  我们来获取屏幕的可用高和宽度，**代码如下：**

  ```
  <script type="text/javascript">
  document.write("可用宽度：" + screen.availWidth);
  document.write("可用高度：" + screen.availHeight);
  </script>
  ```

  **注意:根据屏幕的不同显示值不同。**

### 练习-制作跳转页面

- **要求：**

  1. 如果打开该页面后，如果不做任何操作则5秒后自动跳转到一个新的地址，如慕课网主页。

  2. 如果点击“返回”按钮则返回前一个页面。

  **效果:**

  <img src="http://img.mukewang.com/537d6fed0001572608080402.jpg">

  **注意: 在窗口中运行该程序时，该窗口一定要有历史浏览记录，否则"返回"无效果。**

#### 遇到的问题

- 1.除了用input标签外不知道该用哪个显示秒数

- 2.返回 的跳转设置

- 3.关闭计时器不起作用，参数不知道用哪个——>

  这个的问题出现在没用给setTimeout一个变量用来存值，并且这条语句位置在if语句后，所以出现了问题

- 4.倒计时数字跳转特别快，应该要把x=x-1放在setTimeout的前一句，否则其它位置就会疯狂跳转

上面的问题有点问题，解决办法也有问题，需要修改

## DOM对象，控制HTML元素

### DOM

- 文档对象模型DOM（Document Object Model）定义访问和处理HTML文档的标准方法。DOM 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。

- HTML文档可以说由节点构成的集合，三种常见的DOM节点：

  - 1.元素节点：上图中\<html>、\<body>、\<p>等都是元素节点，即标签。
  - 2.文本节点：向用户展示的内容，如\<li>...\</li>中的JavaScript、DOM、CSS等文本。
  - 3.属性节点：元素属性，如\<a>标签的链接属性href="http://www.imooc.com"。

  **节点属性：**

  <img src="http://img.mukewang.com/5375c953000117ee05240129.jpg">

  **遍历节点树:**

  <img src="http://img.mukewang.com/53f17a6400017d2905230219.jpg">

  **DOM操作:**

  <img src="http://img.mukewang.com/538d29da000152db05360278.jpg">

  **注意:**前两个是document方法。

### getElementsByName()方法

- 返回带有指定名称的节点对象的集合。

  **语法：**

  ```javascript
  document.getElementsByName(name)
  ```

  与getElementById() 方法不同的是，通过元素的 name 属性查询元素，而不是通过 id 属性。

  **注意:**

  1. 因为文档中的 name 属性可能不唯一，所有 getElementsByName() 方法返回的是元素的数组，而不是一个元素。

  2. 和数组类似也有length属性，可以和访问数组一样的方法来访问，从0开始。

- eg:

  <img src="http://img.mukewang.com/5375d5ec00012bac06210322.jpg">

  运行结果：

  <img src="http://img.mukewang.com/53795f0b0001233404580318.jpg">

### getElementsByTagName()方法

- 返回带有指定标签名的节点对象的集合。返回元素的顺序是它们在文档中的顺序。

- **语法:**

  ```
  document.getElementsByTagName(Tagname)
  ```

  **说明:**

  1. Tagname是标签的名称，如p、a、img等标签名。

  2. 和数组类似也有length属性，可以和访问数组一样的方法来访问，所以从0开始。

  看看下面代码，通过getElementsByTagName()获取节点。

  <img src="http://img.mukewang.com/53ec174a0001404206540436.jpg">

#### 三种获取节点方法的区别

- **getElementByID,**

- **getElementsByName,**

- **getElementsByTagName**

  **以人来举例说明，人有能标识身份的身份证，有姓名，有类别(大人、小孩、老人)等。**

  1. ID 是一个人的身份证号码，是唯一的。所以通过getElementById获取的是指定的一个人。

  2. Name 是他的名字，可以重复。所以通过getElementsByName获取名字相同的人**集合**。

  3. TagName可看似某类，getElementsByTagName获取相同类的人集合。如获取小孩这类人，getElementsByTagName("小孩")。

  **把上面的例子转换到HTML中，如下:**

  ```HTML
  <input type="checkbox" name="hobby" id="hobby1">  音乐
  ```

  input标签就像人的类别。

  name属性就像人的姓名。

  id属性就像人的身份证。

  **方法总结如下:**

  <img src="http://img.mukewang.com/5405263300018bcf05760129.jpg">

  **注意：**方法区分大小写

  通过下面的例子(6个name="hobby"的复选项，两个按钮)来区分三种方法的不同:

  ```html
    <input type="checkbox" name="hobby" id="hobby1">  音乐
    <input type="checkbox" name="hobby" id="hobby2">  登山
    <input type="checkbox" name="hobby" id="hobby3">  游泳
    <input type="checkbox" name="hobby" id="hobby4">  阅读
    <input type="checkbox" name="hobby" id="hobby5">  打球
    <input type="checkbox" name="hobby" id="hobby6">  跑步 
    <input type="button" value = "全选" id="button1">
    <input type="button" value = "全不选" id="button1">
  ```

  1. document.getElementsByTagName("input")，结果为获取所有标签为input的元素，共8个。

  2. document.getElementsByName("hobby")，结果为获取属性name="hobby"的元素，共6个。

  3. document.getElementById("hobby6")，结果为获取属性id="hobby6"的元素，只有一个，"跑步"这个复选项。

##### 小节任务：

1.在第27行处补充完整，实现当点击"全选"按钮时，将选中所有的复选项。

```html
提示:document.getElementsByTagName("input")获取的是所有input标签，包括复选项和按钮，所以要判断是否是复选项，如是选中。
```

2.在第33行处补充完整，实现当点击"全不选"按钮时，将取消所有选中的复选项。

3.在第40行处补充完整，在文本框中输入输入1-6数值，当点击"确定"按钮时，根据输入的数值，通过id选中相应的复选项。

- 碰到的问题：

  - 1.不知道获取了标签名后如何设置checked值从而达到全选（还忘记了在全选前设置判断复选框和按钮，是复选框才全选）

  - 2.取消设置的checked值false不能加引号（好奇怪啊ture都可以）

    - 解决办法：

    - 1.getElementsByTagName方法得到的结果是一个数组集合，所以做判断时不能单纯的用if判断，要用for循环，再进行判断：

      for(i = 0;i < hobby.length;i++){
                if(hobby[i].type == "checkbox"){
                 hobby[i].checked = true;  }
               }

      并且要逐个获取input标签的type值来判断是否为复选框再设置checked的值。//（或checked="checked"）——这个括号里的搞错了，设置checked="checked"是设置网页载入后的默认选项，而不是说点这个就默认

    - 注意:true|false是属性语法规定不用加引号的
    
  - 3.任务3不能用switch语句，因为用switch语句要赋初值，但是这个是根据input框用户输入的内容再进行判断给复选框勾选的，所以不行。
  
  - 4.想要设置一个判断，这样当用户输入的是非[1-6]范围

### getAttribute()方法

- 通过元素节点的属性名称获取属性的值。

  **语法：**

  ```javascript
  elementNode.getAttribute(name)
  ```

  **说明:**

  1. elementNode：使用getElementById()、getElementsByTagName()等方法，获取到的元素节点。

  2. name：要想查询的元素节点的属性名字

  看看下面的代码，获取h1标签的属性值：

  ![](http://img.mukewang.com/538d242700019ec809330432.jpg)

  **运行结果:**

  h1标签的ID ：alink
  h1标签的title ：getAttribute()获取标签的属值

### setAttribute()方法

- setAttribute() 方法增加一个指定名称和值的新属性，或者把一个现有的属性设定为指定的值。

  **语法：**

  ```javascript
  elementNode.setAttribute(name,value)
  ```

  **说明：**

  1.name: 要设置的属性名。

  2.value: 要设置的属性值。

  **注意：**

  1.把指定的属性设置为指定的值。如果不存在具有指定名称的属性，该方法将创建一个新属性。

  2.类似于getAttribute()方法，setAttribute()方法只能通过元素节点对象调用的函数。

### 节点属性

- 在文档对象模型 (DOM) 中，每个节点都是一个对象。DOM 节点有三个重要的属性 ：

  1. nodeName : 节点的名称

  2. nodeValue ：节点的值

  3. nodeType ：节点的类型

  **一、nodeName 属性:** 节点的名称，是只读的。

  1. 元素节点的 nodeName 与标签名相同

  2. 属性节点的 nodeName 是属性的名称

  3. 文本节点的 nodeName 永远是 #text

  4. 文档节点的 nodeName 永远是 #document

  **二、nodeValue 属性：**节点的值

  1. 元素节点的 nodeValue 是 undefined 或 null

  2. 文本节点的 nodeValue 是文本自身

  3. 属性节点的 nodeValue 是属性的值

  **三、nodeType 属性:** 节点的类型，是只读的。以下常用的几种结点类型:

  **元素类型   节点类型**
   元素      1
   属性      2
   文本      3
   注释      8
   文档      9

### 访问子节点childNodes

- 访问选定元素节点下的所有子节点的列表，返回的值可以看作是一个数组，他具有length属性。

  **语法：**

  ```javascript
  elementNode.childNodes
  ```

  **注意：**

  如果选定的节点没有子节点，则该属性返回不包含节点的 NodeList。

  **我们来看看下面的代码:**

  ![](http://img.mukewang.com/538405fa00010e6c05630357.jpg)

  **运行结果:**

  **IE:**

  ```javascript
    UL子节点个数:3
    节点类型:1
  ```

  **其它浏览器:**

  ```javascript
     UL子节点个数:7
     节点类型:3
  ```

  **注意:**

  1. IE全系列、firefox、chrome、opera、safari兼容问题

  2. 节点之间的空白符，在firefox、chrome、opera、safari浏览器是文本节点，所以IE是3，其它浏览器是7，如下图所示:

  ![](http://img.mukewang.com/538d2b8a000163e303430127.jpg)

  **如果把代码改成这样:**

  <ul><li>javascript</li><li>jQuery</li><li>PHP</li></ul>
**运行结果:（IE和其它浏览器结果是一样的）**
  
```javascript
    UL子节点个数:3
    节点类型:1
```

### 访问子节点的第一和最后项

- 一、**`firstChild `**属性返回‘childNodes’数组的第一个子节点。如果选定的节点没有子节点，则该属性返回 NULL。

  **语法：**

  ```javascript
  node.firstChild
  ```

  **说明：**与elementNode.childNodes[0]是同样的效果。 

  二、**` lastChild`** 属性返回‘childNodes’数组的最后一个子节点。如果选定的节点没有子节点，则该属性返回 NULL。

  **语法：**

  ```
  node.lastChild
  ```

  **说明：**与elementNode.childNodes[elementNode.childNodes.length-1]是同样的效果。 

  **注意:** 上一节中，我们知道Internet Explorer 会忽略节点之间生成的空白文本节点，而其它浏览器不会。我们可以通过检测节点类型，过滤子节点。

### 访问父节点parentNode

- 获取指定节点的父节点

  **语法：**

  ```html
  elementNode.parentNode
  ```

  **注意:父节点只能有一个。**

  看看下面的例子,获取 P 节点的父节点，代码如下:

  ```javascript
  <div id="text">
    <p id="con"> parentNode 获取指点节点的父节点</p>
  </div> 
  <script type="text/javascript">
    var mynode= document.getElementById("con");
    document.write(mynode.parentNode.nodeName);
  </script>
  ```

  运行结果:

  ```
  parentNode 获取指点节点的父节点
  DIV
  ```

  **访问祖节点:**

  ```
  elementNode.parentNode.parentNode
  ```

  看看下面的代码:

  ```html
  <div id="text">  
    <p>
      parentNode      
      <span id="con"> 获取指点节点的父节点</span>
    </p>
  </div> 
  <script type="text/javascript">
    var mynode= document.getElementById("con");
    document.write(mynode.parentNode.parentNode.nodeName);
  </script>
  ```

  运行结果:

  ```
  parentNode获取指点节点的父节点
  DIV
  ```

  注意: 浏览器兼容问题，chrome、firefox等浏览器标签之间的空白也算是一个文本节点。

### 访问兄弟节点

- 1. nextSibling 属性可返回某个节点**之后**紧跟的节点（处于同一树层级中）。

  **语法：**

  ```javascript
  nodeObject.nextSibling
  ```

  **说明：**如果无此节点，则该属性返回 null。

  2. previousSibling 属性可返回某个节点**之前**紧跟的节点（处于同一树层级中）。

  **语法：**

  ```javascript
  nodeObject.previousSibling  
  ```

  **说明：**如果无此节点，则该属性返回 null。

  注意: 两个属性获取的是节点。Internet Explorer 会忽略节点间生成的空白文本节点（例如，换行符号），而其它浏览器不会忽略。

  **解决问题方法:**

  **判断节点nodeType是否为1, 如是为元素节点，跳过。**

  ![](http://img.mukewang.com/5386e3c80001c25607010856.jpg)

  **运行结果:**

  ```javascript
  LI = javascript
  nextsibling: LI = jquery
  ```

### 插入节点appendChild()

- 在指定节点的最后一个子节点列表之后添加一个新的子节点。

  **语法:**

  ```javascript
  appendChild(newnode)
  ```

  **参数:**

  newnode：指定追加的节点。

  我们来看看，div标签内创建一个新的 P 标签，代码如下:

  ![](http://img.mukewang.com/5398fd020001ad4905890193.jpg)

  **运行结果:**

  ```javascript
  HTML
  JavaScript
  This is a new p
  ```

### 插入节点insertBefore()

- insertBefore() 方法可在已有的**子节点前**插入一个新的子节点。

  **语法:**

  insertBefore(newnode,node);

  **参数:**

  newnode: 要插入的新节点。

  node: 指定此节点前插入节点。

  我们在来看看下面代码，在指定节点前插入节点。

  ![](http://img.mukewang.com/5395318100010c6806960431.jpg)

  **运行结果:**

  ```html
  This is a new p
  JavaScript
  HTML
  ```

  **注意:** otest.insertBefore(newnode,node); 也可以改为: otest.insertBefore(newnode,otest.childNodes[0]); 

### 删除节点removeChild()

- removeChild() 方法从子节点列表中删除某个节点。如删除成功，此方法可返回被删除的节点，如失败，则返回 NULL。

  **语法:**

  ```
  nodeObject.removeChild(node)
  ```

  **参数:**

  node ：必需，指定需要删除的节点。

  我们来看看下面代码，删除子点。

  ![](http://img.mukewang.com/5399744d000153a306060342.jpg)
  
  **运行结果:**
  
  ```
  HTML
  删除节点的内容: javascript
  ```
  
  **注意:** 把删除的子节点赋值给 x，这个子节点不在DOM树中，但是还存在内存中，可通过 x 操作。
  
  如果要完全删除对象，给 x 赋 null 值，代码如下:
  
  ![](http://img.mukewang.com/539975a800017c8e04790082.jpg)

### 替换元素节点replaceChild()

- replaceChild 实现子节点(对象)的替换。返回被替换对象的引用。 

  **语法：**

  ```
  node.replaceChild (newnode,oldnew ) 
  ```

  **参数：**

  newnode : 必需，用于替换 oldnew 的对象。 
  oldnew : 必需，被 newnode 替换的对象。

  我们来看看下面的代码:

  ![](http://img.mukewang.com/539557d70001c3ee07190429.jpg)

  效果: 将文档中的 Java 改为 JavaScript。

  **注意:** 

  1. 当 oldnode 被替换时，所有与之相关的属性内容都将被移除。 

  2. newnode 必须先被建立。 

- 个人笔记：

  要想替换旧对象，首先要建立新的对象，再将旧的替换。

### 创建元素节点createElement

- createElement()方法可创建元素节点。此方法可返回一个 Element 对象。

  **语法：**

  ```javascript
  document.createElement(tagName)
  ```

  **参数:**

  tagName：字符串值，这个字符串用来指明创建元素的类型。

  **注意：**要与appendChild() 或 insertBefore()方法联合使用，将元素显示在页面中。

  我们来创建一个按钮，代码如下：

  ```javascript
  <script type="text/javascript">
     var body = document.body; 
     var input = document.createElement("input");  
     input.type = "button";  
     input.value = "创建一个按钮";  
     body.appendChild(input);  
   </script>  
  ```

  效果：在HTML文档中，创建一个按钮。

  我们也可以使用setAttribute来设置属性，代码如下：

  ```javascript
  <script type="text/javascript">  
     var body= document.body;             
     var btn = document.createElement("input");  
     btn.setAttribute("type", "text");  
     btn.setAttribute("name", "q");  
     btn.setAttribute("value", "使用setAttribute");  
     btn.setAttribute("onclick", "javascript:alert('This is a text!');");       
     body.appendChild(btn);  
  </script>  
  ```

  效果：在HTML文档中，创建一个文本框，使用setAttribute设置属性值。 当点击这个文本框时，会弹出对话框“This is a text!”。

### 创建文本节点createTextNode

- createTextNode() 方法创建新的文本节点，返回新创建的 Text 节点。

  **语法：**

  ```
  document.createTextNode(data)
  ```

  **参数：**

  data : 字符串值，可规定此节点的文本。

  我们来创建一个<div>元素并向其中添加一条消息，代码如下：

  ![](http://img.mukewang.com/53951c200001d32d07130554.jpg)

  **运行结果:**

  ![](http://img.mukewang.com/53951c720001996d04080225.jpg)

### 浏览器窗口可视区域大小

- 获得浏览器窗口的尺寸（浏览器的视口，不包括工具栏和滚动条）的方法:

  **一、对于IE9+、Chrome、Firefox、Opera 以及 Safari：**

  • window.innerHeight - 浏览器窗口的内部高度

  • window.innerWidth - 浏览器窗口的内部宽度

  **二、对于 Internet Explorer 8、7、6、5：**

  • document.documentElement.clientHeight表示HTML文档所在窗口的当前高度。

  • document.documentElement.clientWidth表示HTML文档所在窗口的当前宽度。

  或者

  Document对象的body属性对应HTML文档的\<body>标签

  • document.body.clientHeight

  • document.body.clientWidth

  **在不同浏览器都实用的 JavaScript 方案：**

  ```javascript
  var w= document.documentElement.clientWidth
        || document.body.clientWidth;
  var h= document.documentElement.clientHeight
        || document.body.clientHeight;
  ```

### 网页尺寸scrollHeight

- scrollHeight和scrollWidth，获取网页内容高度和宽度。

  **一、针对IE、Opera:**

  scrollHeight 是网页内容实际高度，可以小于 clientHeight。

  **二、针对NS、FF:**

  scrollHeight 是网页内容高度，不过最小值是 clientHeight。也就是说网页内容实际高度小于 clientHeight 时，scrollHeight 返回 clientHeight 。

  **三、浏览器兼容性**

  ```javascript
  var w=document.documentElement.scrollWidth
     || document.body.scrollWidth;
  var h=document.documentElement.scrollHeight
     || document.body.scrollHeight;
  ```

  **注意:区分大小写**

  scrollHeight和scrollWidth还可获取Dom元素中内容实际占用的高度和宽度。

### 网页尺寸offsetHeight

- offsetHeight和offsetWidth，获取网页内容高度和宽度(包括滚动条等边线，会随窗口的显示大小改变)。

  **一、值**

  offsetHeight = clientHeight + 滚动条 + 边框。

  **二、浏览器兼容性**

  ```javascript
  var w= document.documentElement.offsetWidth
      || document.body.offsetWidth;
  var h= document.documentElement.offsetHeight
      || document.body.offsetHeight;
  ```

### 网页卷去的距离与偏移量

- ![](http://img.mukewang.com/5347b2b10001e1a307520686.jpg)

- **scrollLeft:**设置或获取位于给定对象左边界与窗口中目前可见内容的最左端之间的距离 ，即左边灰色的内容。

  **scrollTop:**设置或获取位于对象最顶端与窗口中可见内容的最顶端之间的距离 ，即上边灰色的内容。

  **offsetLeft:**获取指定对象相对于版面或由 offsetParent 属性指定的父坐标的计算左侧位置 。

  **offsetTop:**获取指定对象相对于版面或由 offsetParent 属性指定的父坐标的计算顶端位置 。

  **注意:**

  **1. 区分大小写**

  **2. offsetParent：布局中设置postion属性(Relative、Absolute、fixed)的父容器，从最近的父节点开始，一层层向上找，直到HTML的body。**

#### 编程练习：

- 制作一个表格，显示班级的学生信息。

  **要求：**

  1. 鼠标移到不同行上时背景色改为色值为 #f2f2f2，移开鼠标时则恢复为原背景色 #fff

  2. 点击添加按钮，能动态在最后添加一行

  3. 点击删除按钮，则删除当前行

- 遇上的问题：

  - 1.给删除按钮添加点击事件后如何得知点击的这个删除的index，再将其删除

    -    function deleteRow(obj){

      ​    var tbody = document.getElementById('table').lastChild; 

      ​    var tr = obj.parentNode.parentNode;

      ​     tbody.removeChild(tr);

         }

  - 2.如何给表格添加一行

    - ​    var tbody = document.getElementById('table').lastChild; 

      ​    var tr = document.createElement('tr'); 

      ​     

      ​     var td = document.createElement("td");

      ​     td.innerHTML = "<input type='text'/>";

      ​     tr.appendChild(td);

      ​     

      ​     td = document.createElement("td"); 

      ​     td.innerHTML = "<input type='text'/>";

      ​     tr.appendChild(td);

      ​     

      ​     td = document.createElement("td"); 

      ​     td.innerHTML = "<a href='javascript:;' onclick='deleteRow(this)'>删除</a>";

      ​     tr.appendChild(td);  

      ​     

      ​     tbody.appendChild(tr);  

      ​    Highlight();

