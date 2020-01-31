# JavaScript进阶篇笔记

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