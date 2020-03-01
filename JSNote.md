# JavaScript

- ```javascript 
  document.write("");//作用在body中输出一个内容
  ```

  ```javascript
  console.log("");//向控制台输出一个内容
  ```

- 通过\<script>标签引用外部js文件。

  写道外部文件中可以在不同的页面同时引用，也可以利用到浏览器的缓存机制，推荐使用的方式。

  script标签一旦用于外部文件，就不能再编写代码了，即使编写了浏览器也会忽略，如果需要则可以再创建一个新的script标签用于编写内部代码。

#### 08-JS注释

- 多行注释 /* */
- 单行注释 //

- JS中严格区分大小写。
- 每条语句以分号（；）结尾。（如果不写分号，浏览器会自动添加，但会消耗一些系统资源，而且有些时候，浏览器会加错分号，所以开发中要加分号）

- JS中会忽略多个空格和换行

##### 09-变量&字面量

###### 字面量

- 都是一些不可改变的值，1，2，3

  字面量都是可以直接使用的，但是一般不会直接使用字面量。

###### 变量

- 可以用来保存字面量，而且变量的值是可以任意改变的，变量可以更加方便我们使用，所以在开发中都是通过变量去保存一个字面量，而很少直接使用字面量

###### 声明变量

- var关键字

  ```javascript
  var a;
  a = 123; //为变量赋值
  console.log(a); //在控制台输出a
  var b = 789; //变量和声明同时进行
  ```

##### 10-标识符

- 在JS中所有的可以自主命名的都可以成为标识符，

  eg:变量名、函数名、属性名

  - 命名规则：
  - 1.可以含有字母、数字、_、$
  - 2.标识符不能数字开头
  - 3.不能是ES中的关键字或保留字
  - 4.标识符一般都采用驼峰命名法：
    - 首字母小写，每个单词开头字母大写，其余字母小写：helloWorld xxxYyyZzz
  - JS底层保存标识符实际上是采用的Unicode编码，所有utf-8中含有的内容都可以作为标识符。

##### 11-数据类型

- 数据类型指的就是字面量的类型(6种)：

  String 字符串

  Number 数值

  Boolean 布尔值

  Null 空值

  Undefined 未定义

  Object 对象

- 其中String Number Boolean Null Undefined属于基本数据类型

- Object属于引用数据类型

  

  - String 字符串 ：在JS中字符串需要用引号引起来，使用单引号双引号都可以，但是不要混用。

  ```javascript
  var str = "hello";
  console.log(str);//输出字面量 字符串str
  console.log(hello);//这是打印hello变量
  ```

  - \ 转义字符
  - \n 换行
  - \t 制表符

- JS中所有数值都是Number类型，包括整数和浮点数。

- typeof运算符检查变量类型

  语法：typeof 变量

  ```javascript
  console.log(typeof b);
  
  console.log(Number.MAX_VALUE);//JS中表示的数值最大值，最小值MIN_VALUE
  //如果使用的数字超过最大值，会返回Infinity,表示正无穷，也是Number类型，-Infinity表示负无穷。
  ```

  - NaN也是Number

- 注意：如果使用JS进行浮点运算，可能得到一个不精确的结果，所以千万不要使用JS进行精确的较高的运算(例如金钱，尽量放到服务器中去运算)

  ```javascript
  var c = 0.1 + 0.2;//结果是0.300000000004
  ```

  

- Boolean 布尔值

  布尔值只有两个:

  true:表示逻辑上的真

  false:表示逻辑上的假

  ```javascript
  var bool = true;
  console.log(typeof bool);//返回boolean
  ```

  

- Null（空值）类型的值：null

  null这个值专门用来表示一个为空的对象

  var a = null;

  console.log(typeof a); //返回object

- Undefined（未定义）类型的值只有一个undefined

  当声明一个值，但并不给其赋值，它的值就是undefined。

- 强制类型转换：将一个数据类型强制转换成其它数据类型，主要是将其它转换为String,Number,Boolean（转换成其它的意义不大）

  - **转换为String**

    - 法一：调用被转换数据类型的toString()方法

      该方法不会影响到原变量，会将转换结果返回。

      ```javascript
      var a = 123;
      a = a.toString();
      //调用a的toString()方法
      //调用xxx的yyy()方法，就是xxx.yyy()
      ```

      但该方法有局限性，null和undefined这两个值没有toStrng()方法

    - 法二：调用String()函数，并将被转换的数据作为参数传递给函数。

      使用String()函数做强制类型转换时，对于Number和Boolean实际上就是调用toString()方法，但是对于null和undefined，就不会调用toString()，它会将null直接转换为"null"，将undefined直接转换为"undefined"

      ```javascript
      a = String(a);
      a = null;
      a = String(a);
      console.log(typeof a);//string
      console.log(a);//"null"
      ```

  - **转换为Number**

    - 法一：使用Number()函数

      - 字符串转数字

        1.如果是纯数字字符串，直接转换为数字

        2.如果字符串中有非数字内容，则转换为NaN

        3.如果字符串是一个空串或者是一个全是空格的字符，则转换为0

      - 布尔转数字

        true --->1

        false --->0

      - null 转数字 --->数字 0

      - undefined转数字 ---->数字 NaN

      ```javascript
      var a = "123";
      a = Number(a);
      console.log(typyof a)；
      console.log(a);
      //var a="  "; 结果是numer 0
      ```

      法二：专门用于对付字符串

      - parseInt() 把一个字符串转换为一个整数：可以将一个字符串中有效的**整数**内容取出来（小数不会取）
      
        还可以用来间接取整

      - parseFloat() 把一个字符串转换为一个浮点数：作用和pareInt()类似，不同的是它可以获得**有效的小数**
      
        - 如果对于非String使用parseInt()，parseFloat()，它会先将其转换为String然后再操作
      
      ```javascript
a = "123.456px";//转化为数字
      //parseInt()--> 123
      //parseFloat()-->123.456
      ```
      
      ```javascript
      a = true;
      a = parseInt(a);
      console.log(typeof a); //number，
//布尔true转为数字是1，这句有问题，正确应该是,将a转换为String然后再转为数字,所以是number类型，而不是true转为数字是1，因为是非字符串所以为NaN（因为本身parseInt()函数就是为了转换为数字的所以是number类型）
      console.log(a); //NaN，因为a是true，为非字符串，所以先将a转为字符串，然后字符串为非数字,返回NaN
  //a= true   =>   a = "true"  => Number(a)  => NaN
      
      ```
      
    
  - **转换为Boolean**
  
    法一：将其它的数据类型转换为Boolean,使用Boolean()函数.
  
    - 数值--->布尔
  
      除了0和NaN是false,其它都是true
  
    - 字符串--->布尔
  
      除了空串，其余都是true
  
    - null 和 undefined 都会转换为false
  
    - 对象也会转换为true
  
    ```javascript
    var a = 123;//true
    a = 0; //false
    a = Infinity; //true
    a = NaN; //false
    
    a = "false"; //true
    a = ""; //false
    
    a = null;//false
    a = undifined;//false
    //调用Boolean()函数来将a转换为布尔值
    a = Boolean(a);
    
    console.log(typeof a);//boolean
    console.log(a);
    ```
  
    法二：隐式类型转换
    
    - 为任意的数据类型做两次非运算，即可将其转换为布尔值。
    
      ```javascript
      var a = "hello";
      a = !!a; //true
      ```
    
      

##### 12-进制数

- 16进制

  - 在js中，如果需要表示16进制的数字，则需要以0x开头。

  ```javascript
  a = 0x10; //"16"
  a = 0xff; //"255" 十六进制
  ```

  - 如果需要表示8进制，需要以0开头

    ```javascript
    a = 070;//56 八进制
    
    a = parseInt(a);
    console.log(typeof a);//String
    console.log(a);//像"070"这种字符串，有些浏览器会当成8进制解析返回"56"，有些会当成10进制解析返回"70"
    //解决方法：在parseInt()中传递第二个参数,来指定数字的进制数
    a = parseInt(a,10);
    ```

  - 如果需要表示2进制，需要以0b开头(但一些浏览器不支持IE)

    ```javascript
    a = 0b10;//二进制
    ```

    

##### 13-运算符（操作符）

- 通过运算符可以对一个或多个值进行运算，并获取运算结果。

  例如：typeof就是运算符，可以来获得一个值的类型，它会将该值的类型以**字符串**的形式返回。

- 算数运算符

  当对非Number类型的值进行运算时，会将这些值转换为Number然后再运算.(有特例)

  任何值和NaN做运算返回的都是NaN

  ```javascript 
  var a = 123;
  result = a + 1;//124
  result = true + 1;//2
  result = true + false;//1
  result = 2 + null;//2
  result = 2 + NaN; //NaN
  //特例
  
  ```

  - **+**

    - **+ ** 可以对两个值进行加法运算，并将结果返回

    - 如果两个字符串进行加法运算，则会做拼串，会将两个字符串拼接为一个字符串，并返回

      任何的值和字符串做加法运算都会先转换为字符串，再和字符串做拼串操作。
      
      - 可以利用这一特点，将一个任意的数据类型转换为String，只需要为任意的数据类型 + 一个""（空串）。即可将其转换为String，这是一种隐式的类型转换，由浏览器自动完成，实际上也是调用String()函数。
      
        ```javascript
        c = null;
        c = c + "";
        c = String(c); //两种是相同的，只是第一种会更简单。
        ```
      
        ```javascript
        result = 1 + 2 + "3"; //33
        result = "1" + 2 + 3; //123
        ```
    
  - **-**
  
    - **-** 可以对两个值进行减法运算，并进行返回。
  
      ```javascript
      result = 100 - 5;//95
      result = 100 - true;//99
      result = 100 - "1"; //1
      ```
  
  - **\***
  
    - **\*** 可以对两个值进行乘法运算
  
  - **\\** 
  
    - **\\** 可以对两个值进行除法运算
  
      ```javascript
      //乘
      result = 2 * 2;//4
      result = 2 * "8";//16
      result = 2 * undefined;//NaN
      result = 2 * null;//0
      //除
      result = 4 / 2;//2
      result = 3 / 2;//1.5
      ```
  
  - 任何值做 - * / 运算时都会自动转换为Number，
  
    可以利用这一特点做隐式的类型转换，通过为一个值 -0 *1 /1来将其转换为Number，原理和Number()函数一样，使用起来更加简单。
  
  - **%** 
  
    - **%** 取模运算(取余数)
  
      ```javascript
      result = 9 % 3;//0
      result = 9 % 4;//1
      result = 9 % 5;//4
      ```

##### 14-一元运算符

- 只需要一个操作数：

  \+ 正号 ：不会对数字产生任何影响

  \-  负号 ：负号可以对数字进行负号的取反

  对于非Number类型的值，会将其先转换为number再进行运算。

  - 可以对一个其它的数据类型使用+，来将其转换为number,它的原理与Number()函数相同

  ```javascript
  var a = 123;
  a = +a;//123
  a = -a;//-123 
  
  a = true;
  a = -a; // a=-1;number;
  a = "10";
  a = -a;// a=-10;number;
  ```

  ```javascript
  var result = 1 + "2" +3;//123
  var result = 1 + +"2" +3;//6
  //隐式类型转换
  ```

##### 15-自增和自减

- 自增 ++ ：通过自增可以使变量再自身基础上增加1,对于一个变量自增后，原变量的值会立刻自增1。

  - 自增分为两种：a++ (后++)，++a (前++)

    无论是a++ 还是 ++a ，都会立即使原变量的值自增1

    - 不同的是a++ 和 ++a 的值不同 （表达式a++的值与变量a的值是不一样的)

      - a++ 的值等于原变量的值（自增前的值）
      - ++a 的值等于原变量的新值（自增后的值）

      ```javascript
      var c = 10;
      c++; //第一次在10的基础上自增
      c++; //第二次在11的基础上自增
      console.log(c);//11
      ```

      ```javascript
      var d = 20;
      var result = d++ + ++d + d;//64
      ```

      ```javascript
      var d = 20;
      d = d++;// 20; d自增值为21，表达式的值为自增前d的原值20,再赋值给d，所以是20。即d++是多少,d就是多少
      //想当于 var e = d++;
      // d = e;
      ```

      

- 自减 -- ：通过自减可以使变量在自身的基础上减1

  - 自减分为两种：a-- 和 --a 

    无论是--a 还是 a-- ，都会立即使原变量的值自减1

    - 不同的是--a 和 a-- 的值不同 （表达式a--的值与变量a的值是不一样的)
      - a-- 的值等于原变量的值（自减前的值）
      - --a 的值等于原变量的新值（自减后的值）

  ```javascript
  var n1 =10;
  var n2 = 20;
  var n = n1++; // n1 = 11; n = 10;
  console.log(n);//10
  console.log(n1);//11
  n = ++n1;
  console.log(n);//12
  console.log(n1);//12
  n = n2--; 
  console.log(n);//20
  console.log(n2);//19
  n = --n2;
  console.log(n);//18
  console.log(n2);//18
  ```

  

##### 16-逻辑运算符

- JS中提供了三种逻辑运算符

  - ！ 非

    - ！可以用来对一个值进行非运算，就是对一个布尔值进行取反操作，true变false，false变true

    - 对值进行两次取反!!它不会变换

    - 如果对非布尔值进行运算，则会将其转换为布尔值，然后再取反

      所以可以利用该特点，来将一个其他的数据类型转换为布尔值。(为一个任意数据类型取两次反，来将其转换为布尔值，原理和Boolean()函数一样)

  - && 与

    - &&可以对符号两侧的值进行与运算并返回结果
    - 运算规则：
      - 两个值只要有一个值为false，就返回false，两个值都为true，才返回true
      - JS中，对于与，若第一个值为false，第二值不再执行第二值

  - || 或

    - ||可以对符号两侧的值进行或运算并返回结果
    - 运算规则：
      - 两个值中只要有一个true，就返回true；如果两个值都为false，才返回false
      - JS中，对于或，如果第一个值为true，则不会检查第二个值，如果第一个为false,则会检查第二个

- && || 非布尔值的情况

  - 对于非布尔值进行与或运算时，会将其转换为布尔值，然后再运算，并且返回原值。

  - 与运算：

    - 如果第一个值为true,则必然返回第二个值
    - 如果第一个值为false，则必然返回第一个值

    ```javascript
    //与运算：
    //如果两个值都为true，则返回后边的。
    //如果两个值中有false，则返回靠前的false
    var result = 2 && 1;
    console.log(result);//1
    result = 0 && 2;//0
    result = NaN && 0;//NaN
    ```

  - 或运算

    - 如果第一个值为true,则直接返回第一个值
    - 如果第一个值为false，则必然返回第二个值

    ```javascript
    result = 2 || 1;//2
    result = NaN || 1;//1
    result = "" || "hello";//"hello"
    ```

    

##### 17-赋值运算符

- = 

  - 可以将符号右侧的值赋值给符号左侧的变量

- +=

  -  a += 5 等价于  a = a + 5;

  ```javascript
  var a = 10;
  //a = a + 5;
  a += 5;//效果相同
  
  ```

- -=

  -  a -= 5 等价于  a = a - 5;

- *=

  -  a *= 5 等价于  a = a * 5;

- \=

  -  a \= 5 等价于  a = a \ 5;

- %=

-  a %= 5 等价于  a = a % 5;

##### 18-关系运算符

- 通过关系运算符可以比较两个值之间的大小关系，如果关系成立则会返回true,如果关系不成立则返回false



- \> 大于号
  - 判断符号左侧的值是否大于右侧， 如果关系成立，返回true，否则false

-  \>= 大于等于
  - 同上
- \<= 小于等于



- 非数值的情况

  - 对于非数值进行比较，将其先转换为数字再进行比较
  - 如果符号两侧的值都是字符串时，不会将其转换为数字进行比较，而会分别比较字符串中字符的Unicde编码
  
  ```javascript
  console.log(1 > true); //false
  console.log(1 >= true);//true
console.log(1 > "0");//true
  console.log(10 > null);//true
  //任何值和NaN做任何比较都是false
  console.log(10 > "hello");//true
  console.log(10 < "hello");//false
  console.log(true > false);//true
  
  console.log("1" < "5");//true
  console.log("11" < "5");//true
  //比较两个字符串时，比较的是字符串的字符编码
  //比较字符编码是一位一位进行比较，如果两位一样，则比较下一位
  console.log("a" < "b");//true
  console.log("abc" < "b");//true; a比b小，之间返回true
  console.log("bbc" < "b");//false
  console.log("abc" < "bcd");//true
  //借用字符串比较来对英文进行排序
  console.log("11" < "5");//true
  //先拿1和5的编码进行比较，1比5小，直接返回true
  
  //如果比较的两个字符串型的数字，可能会得到不可预期的结果。
  //注意：再比较两个字符串型数字时，一定要转型
  ```
  
  

##### 19-编码

- 在字符串中用转义字符输入Unicode编码，\u四位编码 

```javascript
console.log("\u2620");//输出unicode编码为2620的符号
```

```html
<!--在网页中使用Unicode编码
	&#编码; 这里的编码需要的是10进制
-->
	<h1>&#9760;//2620的十进制</h1>
```

##### 20-相等运算符

- 用来比较两个值是否相等，如果相等会返回true，否则返回false。
- 使用 == 来做相等运算
  - 当使用 == 来比较两个值时，如果值的类型不同，则会自动进行类型转换，将其转换为相同的类型，然后在比较

```javascript
console.log(1 == 1);//true
console.log("1" == 1);//true
console.log(true == "1");//true
console.log(true == "hello");//false
console.log(null == 0);//false

```

- undefined 衍生自 null

  - 所以这两个值做相等判断时，会返回true

- NaN不和任何值相等，包括它本身

  ```javascript
  console.log(undefined == null);//true
  console.log(NaN == NaN);//false
  //判断b值是否为NaN
  //console.log(b == NaN);这种方法不可以
  //通过isNaN()函数来判断一个值是否是NaN
  //对于判断分数，假如输入的不是数字时可以用isNaN()进行判断
  ```

  

**不相等**

- 不相等用来判断两个值是否不相等，如果不相等返回true，否则返回false
  - 使用 != 来做不相等运算
  - 不相等也会对变量进行自动的类型转换，如果转换后相等它也会返回false

**=== 全等**

- 用来判断两个值是否全等，它和相等类似，不同的是它不会做自动的类型转换。

  如果两个值的类型不同，直接返回false

**!== 不全等**

- 用来判断两个值是否不全等，和不等类似，不同的是它不会做自动的类型转换，如果两个值的类型相同，直接返回true

```javascript
console.log("123" == 123);//true
console.log("123" === 123);//false
console.log(null === undefined);//false
console.log(1 != "1");//false
console.log(1 !== "1");//true


```

##### 21-条件运算符（三元运算符）

- 语法：

  - 条件表达式? 语句1:语句2;

    - 执行的流程：

      条件运算符在执行时，首先对条件表达式进行求值.

      ​	如果该值为true，则执行语句1，并返回执行结果；如果该值为false，则执行语句2，并返回执行结果.

      

```javascript
true?alert("语句1"):alert("语句2"); 
var a = 10, b = 20;
a > b ? alert("a大"):alert("b大");//b大
//获取ab中的最大值
var max = a > b ? a : b;
var c = 50;
//这种方法不推荐使用，不方便阅读
var max = a > b ? (a > c ? a : c) : (b > c ? b : c);//50;
```

```javascript
"hello"?alert("语句1"):alert("语句2");//语句1
```

##### 22-运算符优先级

-  ，逗号运算符：使用 , 可以分割多个语句，一般可以在声明多个变量时使用

- 和数学中一样，JS中运算符也有优先级，JS优先级表格中越前优先级越高，若优先级相同，从左往右计算。
- 可以使用（）来改变优先级从而判断哪个优先级更高
  - 先乘除后加减， 
  - && 与 优先级高于 ||或

##### 23-语句Statement

- 我们的程序是由一条一条语句构成的，语句是按照自上向下的顺序一条一条执行的，在JS中可以使用{}来为语句进行分组。
  - 一个{}中的语句要不都执行，要不都不执行，一个{}中的语句也称为一个代码块。在代码块的后边不再需要编写 ;
  - JS中 的代码块，只具有分组的作用，没有其它用途，代码块内的内容，在外部是完全可见的。

###### 24-流程控制语句

- JS中的程序是从上到下一行一行执行，通过流程控制语句可以控制程序执行流程，使程序可以可以根据一定条件来选择执行。

- 分类：
  - 1.条件判断语句
    - 使用条件判断语句在执行某个语句之前进行判断。  
  - 2.条件分支语句
  - 3.循环语句

###### 25-循环语句

```javascript
while(true){
    var score = prompt("请输入成绩(1-100):");
    if(score >= 0 && score <= 100){
        break;//满足该条件则证明用户输入合法，瑞出循环。
    }
    alert("请输入有效的分数！");
}
//while循环可以用于判断用户输入数据是否规范
```

- while循环

- for循环：

  - 1.执行初始化表达式
  - 2.执行判断表达式
  - 3.执行循环语句
  - 4.执行更新表达式
  - 再234循环

  如果for循环中不写任何表达式，只写两个; 则是死循环

```javascript
//打印1-100之间所有7的倍数的个数及总和
var sum = 0;
var count = 0;
for (var i=1 ; i <=100 ; i++) {
    //判断i是否为7的倍数
    if (i % 7 == 0){
        sum += i;
        count++;
    }
}
console.log(sum);
console.log(count);
```

```javascript
//水仙花数-是指一个三位数，它的每个位上的数字的3次幂之和为它本身（1^3 + 5^3 + 3^3 = 153），打印所有的水仙花数
for (var i=100 ; i<1000 ; i++) {
    //获取i的百位 十位 个位 
    var bai = parseInt(i/100);//获取百位
    var shi = parseInt((i-bai*100)/10);//获取十位
    var ge = i % 10;//获取个位
    //判断是否为水仙花数
    if (bai*bai*bai + shi*shi*shi + ge*ge*ge == i){
        console.log(i);
    }  
}

```

```javascript
//在页面中接受一个数字，并判断这个数字是否为质数
//质数：只能被1和它自身整除的数，1不是质数也不是合数，质数必须是大于1的数。
var num = prompt("请输入一个大于1的整数:");
//判断这个值是否合法
if (num <= 1){
    alert("该值不合法");
}else{
    //创建一个变量来保存当前数的状态，默认当前num为质数
    var flag = true;
    
    //判断num是否是质数
    //获取2-num之间的数
    for (var i=2 ; i<num ; i++) {
        if(num % i == 0){
            //如果num能被i整除，则一定不是质数
            //设置flag为fasle
            flag = false;
        }
    }
    //如果num是质数则输出
    if(flag){
        alert(num + "是质数！" );
    }else{
        alert("这个数不是质数");
    }
}
//当判断一个数是否为质数时，判断5，则234都要判断，此时反过来当其中一个数能整除，说明它不是质数，则可排除
```

```javascript
//质数练习改进，对于for循环中的判断，i<num，将num改为Math.sqrt(i),缩小取值范围，可以提高程序性能，取某个数的因数，将其取根号，只要在这之间进行判断，不需要从头判断至该数本身
```



- 嵌套for循环

- break; continue;

  - break只能在循环语句中使用，在if中不可以，会立即终止离它最近的那个循环语句

  - 可以为循环语句创建一个label，来标识当前的循环

    - label:循环语句
    - 使用break语句时，可以在break后面跟着一个label，这样break将会结束指定的循环，而不是最近的。

    ```javascript
    outer:
    for (var i=0 ; i<5 ; i++) {
        console.log("outer:"+i);
        for (var j=0 ; j<5 ; j++) {
            break outer;
            console.log("in:"+j);
        }
    }
    ```

  - continue关键字用来跳过当此循环，同样也是对最近的循环语句作用

##### 26-对象

Object 对象 - 引用数据类型 

除了5种基本数据类型，其它值只要不是其中5种，全都是对象。基本数据类型都是单一的值，值和值之间没有任何的联系。

- 对象属于一种复合的数据类型，在对象中可以保存多个不同数据类型的属性。
- 对象的分类：
  - 1.内建对象
    - 由ES标准中定义的对象，在任何的ES的实现中都可以使用。
    - 比如：Math String Number Boolean Function Object...
  - 2.宿主对象
    - 由JS的运行环境提供的对象，目前主要指由浏览器提供的对象
    - 比如 BOM DOM
  - 3.自定义对象
    - 由开发人员自己创建的对象 

```javascript
//1.创建对象
/*
 * 使用new关键字调用的函数，是构造函数constructor
 *  构造函数是专门用来创建对象的函数
 */
var obj = new Object();

//在对象中保存的值称为属性
//2.向对象中添加属性
//语法：对象.属性名 = 属性值;
obj.name = "haha";
//3.读取对象中的属性
//语法： 对象.属性名
console.log(obj.name);
//如果读取对象中没有的属性，不会报错而是会返回undefined
//4.修改对象属性值
//语法： 对象.属性名 = 新值
obj.name = "tom";
//5.删除对象属性
//语法: delete 对象.属性名
delete obj.name;
```

###### 属性名和属性值

- 属性名

  - 对象的属性名不强制要求遵守标识符的规范
  - 如果需要特殊的属性名，不能采用.方式来操作,要采用另一种方式
    - 语法：  对象["属性名"] = 属性值
    - obj["123"] = 789;    //存
    - console.log(obj["123"]);  //取

  - 使用[] 这种形式操作属性，更加的灵活，在[ ]种可以直接传递一个变量，这样的变量值是多少就会读取那个属性

    ```javascript
    obj["123"] = 789;
    obj["hello"] = "你好";
    
    var n = "123";
    console.log(obj[n]);//789
    ```

    

- 属性值
  
  - JS对象的属性值，可以是任意的数据类型，甚至也可以是一个对象



- in 运算符
  - 通过该运算符可以检查一个对象种是否含有指定的属性，有返回true，否则返回false
  - 语法：
    - "属性名" in 对象
    - console.log("name" in obj);//true

##### 27-基本和引用数据类型

- 基本数据类型: 

  String Number Boolean Null Undefined

- 引用数据类型：

  Object



- JS中的内存都是保存在栈内存中的

  - 基本数据类型的值直接在栈内存中存储，值与值之间是独立存在，修改一个变量不会影响其它变量

  ```javascript
  var a = 123;
  var b = a;
  a++;
  ```

  | 变量 | 值   |
  | ---- | ---- |
  |      |      |
  | b    | 123  |
  | a    | 124  |

  - 对象（引用数据类型）是保存在堆内存中的,每创建一个新的对象，就会在堆内存中开辟出一个新的空间，而变量保存的是对象的内存地址（对象的引用），如果两个变量保存的是同一个对象引用，当一个通过一个变量修改属性时，另一个也会受到影响。

    - 想象一下巫蛊娃娃
    - 当同时指向同一变量的值为null时，另一个不会受影响。

  - 

    | 0x123       |
    | ----------- |
    | name = swk; |

- 当比较两个基本数据类型的值时，就是比较值： 1 == 1

  而比较两个引用数据类型时，它是比较的对象的内存地址，当两个对象是一模一样的但是地址不同，也会返回false

- 简短一句话：基本数据类型保存值，引用数据类型保存的是引用地址

##### 28-对象字面量

```javascript
var obj = new Object();//创建一个对象
var obj = {};//使用对象字面量来创建一个对象
//两种方式一样
```

- 使用对象字面量，可以在创建对象时，直接指定对象中的属性

  ​	语法：

  - {属性名：属性值，属性名：属性值...}

    ```javascript
    var obj2 = {
        name:"abc",
        age:22,
        gender:"女"
    }
    ```

    - 对象字面量的属性名可以加引号也可以不加，建议不加，如果要使用特殊名字，则必须加
    - 属性名和属性值是一组一组的名值对结构，名和值之间用：连接，多个名值用  ,  隔开。属性之后没有其它属性则不需要写添逗号

##### 29-函数function

函数也是一个对象。

- 函数中可以封装一些功能（代码），在需要时可以执行这些功能。可以保存一些代码在需要的时候调用

- 创建函数对象

  ```javascript
  var fun = new Function();
  console.log(typeof fun);//function
  
  //可以将要封装的代码以字符串的形式传递给构造函数
  var fun = new Funtion("console.log('hello 这是我的第一个函数');");//这种方式在实际开发中很少用
  
  //封装到函数中的代码不会立即执行，函数中的代码会在函数调用时执行
  ```

  调用函数： 函数对象()

  当调用函数时，函数中的封装的代码会按照顺序执行	

```javascript
    fun();
```

- **使用函数声明来创建一个函数**

  语法：

​		 function 函数名([形参1，形参2...形参n]) {

​				语句......

​		}

```javascript
function fun2() {
    console.log("The second function");
}
//调用fun2
fun2();
```

- **使用函数表达式来创建一个函数**

  var 函数名 = function([ 形参1，形参2...形参n]) {

  ​	语句......

  }

```javascript
function() {
    console.log("我是匿名函数中封装的代码");
}//匿名函数就这样用不了
var fun3 = function() {
    console.log("我是匿名函数中封装的代码");
};//创建一个对象fun3,变量保存的是匿名函数对象
//创建一个匿名函数，将匿名函数对象赋值给变量
fun3();//调用
```

###### 30-函数的参数

```javascript
//定义一个求两个数和的函数，可以在函数的()中来指定一个或多个形参,多个形参之间使用逗号隔开，声明形参相当于在函数内部声明了对应的变量但并不赋值
function sum(a,b){   //相当于声明 var a;var b;
    console.log(a+b);
}
//在调用函数时，可以在()中指定实参(实际参数)，实参将会赋值给函数中对应的形参
sum(1,3);//相当于 var a = 1; var b = 2;
```

- 调用函数时解析器不会检查实参的类型

  所以要注意，是否可能会接受到非法的参数，如果可能则需要对参数进行类型检查。

- 调用函数时解析器不会检查实参的数量

  多余的实参不会被赋值。

  如果实参的数量少于形参的数量，则么有对于的实参的形参将是undefined

  ```javascript
  function sum(a,b){ 
      console.log(a);    
      console.log(b);
      console.log(a+b);
  }
  sum(123);
  //123;undefined;NaN
  ```

-  可以使用return来设置函数的返回值

  语法: 

  ​		 return 值

  - return后的值将会作为函数的执行结果返回，可以定义一个变量，来接收该结果。
  - 在函数中return后的语句都不会执行。
  - 如果return语句后不跟任何值就相当于返回一个undefined，如果函数中不写return，也会返回undefined。
  - return后可以跟任意类型的值

```javascript
//定义一个函数，判断一个数字是否是偶数，如果是则返回true，否则返回false
function isOu (num) {
   // if(num % 2 == 0){
   //     return true;
   // }else{
   //     return false;
   // }
    return num % 2 == 0;
}

var result = isOu(3);
console.log("result"+result);//false
```

```javascript
//定义一个函数，可以根据半径计算一个圆的面积，并返回计算结果
function area(num) {
    return 3.14*num*num;
}
```

- 实参可以是一个对象，也可以是一个函数
  - area()    调用函数，相当于使用函数的返回值
  - area       函数对象，相当于直接使用函数对象

- 返回值可以是任意的数据类型，可以是对象，也可以是函数

  ```javascript
  function fun1(){
      function fun2(){
          console.log("fun2");
      }
      fun2();
  }
  
  a = fun1();
  console.log(a);//fun2
  a();//调用fun2
  //相当于 fun1()();
  ```

  

###### 31-立即执行的函数

```javascript
function() {
    alert("我是一个匿名函数");
}//直接这也写会报错，除非创建一个对象
//用括号来把匿名函数圈起来表明这是一个整体，不是独立的，就不会报错
(function() {
    alert("我是一个匿名函数");
})
//调用——立即执行函数
(function() {
    alert("我是一个匿名函数");
})();//在括号后加一对括号，表明函数定义完，立即被调用。
//作用：立即执行函数往往只会执行一次

(function(a,b){
    console.log("a = "+a);
    console.log("b = "+b);
})(123,456);//立即执行函数也要传参数
```

##### 32-对象补充知识

```javascript
var obj = new Object();
//向对象中添加属性
obj.name = "孙悟空";
obj.age = 18;
//对象的属性值可以是任何的数据类型，也可以是个函数
obj.sayName = function(){
    console.log(obj.name);
};
function fun() {
    console.log(obj.name);
}
//调方法
obj.sayName();//孙悟空
//调函数
fun();
```

- 函数也可以称为对象的属性，如果一个函数作为一个对象的属性保存，那么我们称这个函数是这个对象的方法，调用这个函数就说调用对象的方法(method)，
- 但这只是名称上的区别
  - 调用obj的sayName方法

###### 33-枚举对象中的属性 for ... in 语句

```javascript
var obj = {
    name:"孙悟空",
    age:18,
    gender:"男",
    address:"花果山"
};
//当想查看某个对象中的属性时，枚举对象中的属性
//使用for ... in 语句
for (var n in obj){
    console.log("属性名"+n);
    //console.log(obj[n]);//取属性值
}//name age gender address
```

for ... in 语句

- 语法：

  ​	for (var 变量 in 对象){

  }

  - for ... in 语句 对象中有几个属性，循环体就会执行几次，每次执行时，会将对象中的一个属性的名字赋值

##### 34-作用域

- 作用域指一个变量的作用的范围

- 在JS中一共有两种作用域：

  - 1.全局作用域

    - 直接编写在script标签中的JS代码，都在全局作用域

    - 全局作用域在页面打开时创建，在页面关闭时销毁

    - 在全局作用域中有一个全局对象window，它代表的是一个浏览器的窗口，它由浏览器创建我们可以直接使用

    - 在全局作用域中：

      - 创建的变量都会作为window对象的属性保存。

        ```javascript
        var a = 10;
        console.log(a);
        console.log(window.a);//a作为window对象的属性保存
        ```

    - 全局作用域中的变量都是全局变量，在页面的任意部分都可以访问的到

  - 2.函数作用域

    - 调用函数时创建函数作用域，函数执行完毕后，函数作用域销毁

    - 每调用一次函数就会创建一个新的函数作用域，它们之间是相互独立的。

    - 在函数作用域中可以访问到全局作用域的变量

      - 在全局作用域中无法访问到函数作用的变量

    - 当在函数作用域操作一个变量时，它会现在自身作用域中寻找，如果有直接使用，如果没有则向上一级作用域中寻找，直到找到全局作用域，

      如果全局作用域依然没有找到，则会报错RefernceError

    - 在函数中如果要访问全局的变量，就使用window.变量名 

    ```javascript
    //在函数作用域中也有声明提前特性，使用var关键字声明的变量，会在函数中所有代码执行之前被声明
    //函数声明也会在函数中所有代码执行之前被声明
    function fun() {
        console.log(a);//undefined; //函数声明提前，所以返回undefined而不是报错
        var a = 35;
        
        function fun2(){
            alert("I am fun2");
        }
    }
    fun();//会弹出alert框 
    ```

- 在函数中，不使用var声明的变量都会成为全局变量

```javascript
var c = 33;
function fun3(){
    console.log("c = "+c);
    c = 10;
}
fun3();//c = 10;
//函数中的c没有用var声明，所以就会找到全局中的变量，并将10赋给它，所以调用函数得到结果是10

```

```javascript
function fun4(){
    d = 100;//在函数中不使用var声明的变量都会变成全局变量，d没有使用var关键字，则设置为全局变量，相当于window.d = 100; 所以一般在函数中要使用var关键字声明变量
}
fun4();
//在全局中输出c
console.log("d = "+d);//d = 100;
```

```javascript
var e = 23;
function fun5() {
    alert(e);
}
fun5();//23
//若传参数
function fun6(e) {
    alert(e);
}
fun6();//undefined 
//这里为啥是undefined?
//因为定义形参就相当于在函数作用域中声明了变量 var e
fun6(20);//20
```





###### 变量声明提前

- 使用 var 关键字声明的变量，会在所有的代码执行之前被声明，但是如果声明比哪里时不使用var关键字，则变量不会被声明提前

###### 函数声明提前

- 使用函数声明形式创建的函数 function 函数() {}

  它会在所有的代码执行之前就被创建，所以可以在函数声明前来调用函数。

  使用函数表达式创建的函数，不会被声明提前，所以不能在声明前调用。

  ```javascript
  fun();//"111"
  fun2();//报错，undefined is not a function
  //函数声明，会被提前创建
  function fun(){
      console.log("111");
  }
  //函数表达式，不会被提前创建
  var fun2 = function() { 
  	console.log("222");
  };//这是函数表达式，不能在声明之前使用
  ```



练习：

```javascript
var a = 123;
function fun(){
    alert(a);//这里的a是undefined，因为函数中用var关键字声明了变量a,只是此时还没有进行赋值（假如函数中没有声明变量a就会向上级查找到全局变量a,值为123)
    var  a = 456;
}
fun();//undefined
alert(a);//123；因为函数中修改的是局部的变量a，对全局的没有影响
```

```javascript
var a = 123;
function fun(){
    alert(a);//函数中没有局部变量a，所以往上级查找
    a = 456; //给全局变量a赋值
}
fun();//123
alert(a);//456
```

```javascript
var a = 123;
function fun(a){
    alert(a);
    a = 456; 
}
fun();//undefined
alert(a);//123
```

```javascript
var a = 123;
function fun(a){
    alert(a);
    a = 456; 
}
fun(123);//123 局部
alert(a);//123 全局
```



##### 35-debug

打断点看watch查看

##### 36-this

- 解析器在调用函数每次都会向函数内部传递进一个隐含的参数，这个隐含的参数就是this。

- this指向的是一个对象，这个对象我们成为函数执行的上下文对象，根据函数的**调用方式**不同，this会指向不同的对象：

  - 1.以函数的形式调用时，this永远都是window
  - 2.以方法的形式调用时，this就是调用方法的那个对象

  ```javascript
  function fun() {
      console.log(this.name);
  }
  //创建一个对象 
  var obj = {
      name:"孙悟空",
      sayName:fun
  };
  var name = "全局的name属性";
  fun();// 全局的name属性
  //[object window] 以函数形式调用，this是window
  obj.sayName();//孙悟空 
  //以对象的形式调用，this是调用方法的对象
  ```

  

##### 37-使用工厂方法创建对象

```javascript
function createPerson(name, age, gender){
    //创建一个新对象
    var obj = new Object();
    obj.name = name;
    obj.age = age;
    obj.gender = gender;
    obj.sayName = function(){
        alert(this.name);
    };
    //将新的对象返回
    return obj;
}

var obj2 = createPerson("猪八戒",20,"男");
var obj3 = createPerson("白骨精",20,"女");
var obj4 = createPerson("蜘蛛精",20,"女");

//使用工厂方法创建的对象，使用的构造函数都是Object
//所以创建的对象都是Object这个类型，导致无法区分出多种不同类型的对象。（人也是Object,狗也是Object）
```

##### 38-构造函数

- 创建一个构造函数，专门用来创建Person对象的（为了解决37种不管什么类型的人、物都是Object类型）

- 构造函数就是一个普通的函数，创建方式和普通函数没有区别，不同的是构造函数习惯上首字母大写

- 构造函数与普通函数的区别就是调用方式的不同，普通函数就是直接调用，而构造函数需要使用new关键字来调用。

- 构造函数的执行流程

  - 1.立刻创建一个新的对象

  - 2.将新建的对象设置为函数中的this ，在构造函数中可以使用this来引用新建的对象

    ```javascript
    function Person(){
        alert(this);//这个this就是新建的对象per
        this.name = "孙悟空";
    }
    var per = new Person();
    console.log(per);//[object Object]
    ```

  - 3.逐行执行函数中的代码

  - 4.将新建的对象作为返回值返回

```javascript
//使用instanceof可以检查一个对象是否是一个类的实例
//语法：
//    对象 instanceof 构造函数 
//   如果是返回true,否则返回false
console.log(per instanceof Person);//true
```



```javascript
//11111111
function Person(name , age , gender) {
    this.name = name;
    this.age = age;
    this.gender = gender;
//    this.sayName = fun() {
//      	alert("大家好，我是"+this.name);  
//   };
    //这种方法会导致构造函数每执行一次就会创建一个新的sayName方法，即所有实例的sayName方法都是唯一的；执行一次就创建一个新方法，执行一万次创建一万个，而这一万个方法都是一样的，是没有必要的，可以使所有对象共享一个方法。
    this.sayName = fun; //向对象中添加一个新的方法
}
//将sayName方法在全局作用域中定义
function fun() {
  	alert("大家好，我是"+this.name);  
};
```

11111111这个例子也有问题，当把sayName函数定义在全局作用域，污染了全局作用域的命名空间，而且定义在全局作用域中也很不安全。

##### 39-原型 prototype

- 我们所创建的每一个函数，解析器都会向函数中添加一个属性prototype

  这个属性对应着一个对象，这个对象就是我们所谓的原型对象。

- 如果函数作为普通函数调用prototype没有任何作用，当函数以构造函数的形式调用时，它所创建的对象中都会有一个隐含的属性

  指向该构造函数的原型对象，我们可以通过 \_proto_ 来访问该属性 

![](C:\Users\jimmy\AppData\Roaming\Typora\typora-user-images\image-20200223165308813.png)

- 原型对象就相当于一个公共的区域，所有同一个类的实例都可以访问到这个原型对象。

  可以将对象中共有的内容，统一设置到原型对象中

  ```javascript
  function MyClass() { 
  }
  //向MyClass的原型中添加属性a
  MyClass.prototype.a = 123;
  var mc = new MyClass();
  console.log(mc.a);//123
  ```

  ![](C:\Users\jimmy\AppData\Roaming\Typora\typora-user-images\image-20200223165752520.png)

- 当我们访问对象的属性和方法时，会现在对象自身中寻找，如果有则直接使用，如果没有则会取原型对象中寻找，如果找到则直接使用

```javascript
//修改11111111例子中的sayName方法

//function fun() {
//  	alert("大家好，我是"+this.name);  
//};
Person.prototype.sayName = function(){
    alert("大家好，我是"+this.name);
};//即确保了函数只有一个，又不影响到全局作用域
```

- 创建构造函数时，可以将这些对象共有的属性和方法，统一添加到构造函数的原型对象中，这也不用分别为每一个对象添加，也不会影响到全局作用域，就可以使每个对象都具有这些方法和属性了。

###### 40-原型

```javascript
//22222222
//使用in检查对象中是否含有某个属性时，如果对象中没有但是原型中有，也会返回true
function MyClass(){
}
//向MyClass原型中添加一个name属性
MyClass.prototype.name = "我是原型中的name";
var mc = new MyClass();
console.log("name" in mc);//true;使用in会找到原型去

//使用对象的hasOwnProperty()来检查对象自身中是否含有该属性，该方法只有当对象中含有属性时，才会返回true
console.log(mc.hasOwnProperty("name"));//false

console.log(mc.hasOwnProperty("hasOwnProperty"));//false
console.log(mc._proto_.hasOwnProperty("hasOwnProperty"));//false
```

- 原型对象也是对象，所以它也有原型，当我们使用一个对象的属性或方法时，会现在自身中寻找，

  如果原型对象中有，则使用，如果没有则去原型的原型中寻找,

  直到找到Object对象的原型，Object对象的原型没有原型，如果在Object中依然没有找到，则返回undefined

```javascript
//接上2222222
console.log(mc._proto_._proto_.hasOwnProperty("hasOwnProperty"));//true
```

##### 41-toString

- 当我们直接在页面中打印一个对象时，实际上是输出的对象的toString()方法的返回值

##### 42-垃圾回收（GC）

- 程序运行过程中也会产生垃圾，当垃圾积攒过多，会导致程序运行的速度过慢，需要一个垃圾回收的机制，来处理程序运行过程中产生的垃圾。
- 当一个对象没有任何的变量或属性对它进行引用，此时我们将永远无法操作该对象，此时这种对象就是一种垃圾，这种对象过多会占用大量内存空间，导致程序运行变慢，所以这种垃圾必须进行清理。
- 在JS中拥有自动的垃圾回收机制，会自动将这些垃圾对象从内存中销毁，我们不需要也不能进行垃圾回收的操作。
- 我们需要做的只是要将不再使用的对象设置null即可。

##### 43-数组

数组（Array）也是一个对象。

- 数组和普通对象功能类似，也是用来存储一些值的，不同的是普通对象是使用字符串作为属性名的，而数组使用数字作为索引操作元素

  - 索引：从0开始的整数就是索引。

- 数组的存储性能比普通对象号，在开发中经常使用数组来存储一些数据。

  - 向数组中添加元素

    语法：

    ​	数组[索引] = 值

  - 读取数组中的元素

    语法：

    ​	数组[索引]

    ​		如果读取不存在的索引，不会报错而是返回undefined

  - 获取数组的长度

    语法：

    ​	数组[length]

    - 可以使用length属性来获取数组的长度（元素的个数）
    - 对于连续的数组，使用length可以获取到数组的长度（元素的个数）
    - 对于非连续的数组，使用length会获取到数组的最大索引+1
    - 尽量不要创建非连续的数组

  - 修改length

    - 如果修改的length大于原长度，则多出部分会空出来
    - 如果修改的length小于原长度，则多出的元素 会被删除

  - 向数组的最后一个位置添加元素

    语法：

    ​	数组[数组.length] = 值;

```javascript
//创建数组对象
var arr = new Array();
console.log(typeof arr);//object
//向数组中添加元素

```

##### 44-使用字面量创建数组

```javascript
//创建一个数组
var arr = new Array();
```

```javascript
//使用字面量
var arr = [];
```

- 使用字面量创建数组时，可以在创建时就指定数组中的元素

```javascript
var arr = [1,2,3,4];
```

- 使用构造函数创建数组时，也可以同时添加元素，将要添加的元素作为构造函数的参数传递

  ```javascript
  var arr2 = new Array(10,20,30);
  //创建一个长度为10的数组
  arr2 = new Array(10);
  //创建一个数组，数组中只有一个元素10
  arr = [10];
  ```

- 数组中的元素可以是任意的数据类型

- 数组中也可以放数组

  arr = [[1,2,3],[3,4,5],[4,5,6]]; //二维数组

  console.log(arr[0]);// 输出第一个数组

  

##### 45-数组的方法

```javascript
var arr = ["monkey","pig","dog"];
arr.push("person");
```

- push()

  - 该方法可以向数组的末尾添加一个或多个元素，并返回数组的新长度

    可以将要添加的元素作为方法的参数传递，这样这些元素将会自动添加到数组的末尾

- pop()
  
  - 该方法可以删除数组的最后一个元素，并将删除的元素作为返回值返回
  
- unshift()
  - 向数组的开头添加一个或多个元素，并返回新的数组长度
  - 向前边插入元素以后，其它的元素索引会依次向后调整
  
- shift()
  
  - 可以删除数组的第一个元素，并将被删除的元素作为返回值返回
  
- slice()

  - 从已有数组中返回选定的元素
  - 参数
    - 1.截取开始的位置的索引，包含开始索引
    - 2.截取结束的位置的索引，不包含结束索引
      - 第二个参数可以省略不写，此时会截取从开始索引往后的所有元素
    - 索引可以传递一个负值，如果传递一个负值，则从后往前计算

- splice()

  - 可以用于删除数组中的指定元素
  - 使用splice()会影响到原数组，会将指定元素从原数组中删除，并将删除的元素作为返回值返回
  - 参数
    - 1.表示开始位置的索引
    - 2.表示删除的数量
    - 3.及以后：可以传递一些新的元素，这些元素会自动插入到开始位置索引前边

```javascript
//去除数组中重复的数字
var arr = [1,2,3,2,1,3,4,2,5];
//获取数组中的每一个元素
for (var i=0 ; i<arr.length ; i++) {
    //获取当前元素后的所有元素
    for (j=i+1 ; j<arr.length; j++) {
        if(arr[i] == arr[j]){
            arr.splice(j,1);
            //当删除了当前j所在的元素后，后壁那的元素会自动补位
            //此时不会比较这个元素，需要再比较一次j所在位置的元素
            //使j自减；
            j--;
        }
    }
}
console.log(arr);
```

- concat()
  - 可以连接两个或多个数组，并将新的数组返回
  - 该方法不会对原数组产生影响

- join()

  - 该方法可以把数组转换为一个字符串

  - 该方法不会对原数组产生影响，而是将转换后的字符串作为结果返回

  - 在join()中可以指定一个字符串作为参数，这个字符串将会成为数组中元素的连接符

    result = arr.join("#");

- reverse()

  - 该方法用来反转数组
  - 该方法会直接修改原数组

- sort()

  - 可以用来对数组进行排序

  - 会影响原数组，默认会按照Unicode编码进行排序

    - 即使对于除数字的数组，使用sort()排序时，也会按照Unicode编码进行排序，所以对于数字排序时，可能会得到错误的结果
    - 可以自己来指定排序的规则，可以在sort()添加一个回调函数，来指定排序规则。
      - 回调函数中定义两个参数，浏览器将会分别使用数组中的元素作为实参去调用回调函数，使用哪个元素调用不确定，但是肯定的是在数组中a一定在前边
    - 浏览器会根据回调函数的返回值来决定元素的顺序
      - 如果返回一个大于0的值，则元素会交换位置
      - 如果返回一个小于0的值，则元素位置不变
    - 如果需要升序排列，则返回a-b;降序返回b-a；

    ```javascript
    arr = [5,4,3,2,1,6];
    arr.sort(function(a,b){
    //    if(a>b){
    //        return -1;
    //    }else if(a<b){
    //        return 1;
    //    }else{
    //        return 0;
        return a - b;//升序排列
        //return b-a;//降序排列
        }
    })
    ```

    

##### 46-数组的遍历

```javascript
var arr = ["monkey","pig","dog"];
//所谓遍历数组，就是将数组中的所有元素都取出来
console.log(arr[0]);//第一个
console.log(arr[1]);//第一二个
```

```javascript
//创建一个函数，可以将perArr中的满18岁的Person提取出来，然后封装到一个新的数组中并返回

function Person(name , age , gender){
    this.name = name;
    this.age = age;
}
//修改Person原型的toString
Person.prototype.toString = function(){
    return "Person[name="+this.name+",age="+this.age+"]";
};

//创建一个Person对象
var per = new Person("monkey",18);
var per2 = new Person("pig",28);
var per3 = new Person("dog",58);
var per4 = new Person("cat",15);
var per5 = new Person("horse",18);
//将person对象放入到一个数组中
var perArr = [per,per2,per3,per4,per5];

//arr, 形参，要提取信息的数组
function getAdult(arr){
    //创建一个新的数组
    var newArr = [];
    //遍历arr,获取arr中Person对象
    for(var i=0; i<arr.length ; i++ ) {
        var p = arr[i];
        //console.log(arr[i]);
    }
    //判断Person对象的age是大于等于18
    if(p.age >= 18){
    //如果大于等于18，则将这个对象添加到newArr中
    	newArr.push(p);
    }
    //将新的数组返回
    return newArr[];
}

var resule = getAdult(perArr);
//console.log(result);
```

###### 47-forEach

- JS中提供了一个方法来遍历数组，但这个方法只支持IE8以上的浏览器
- forEach()方法需要一个函数作为参数
  - 像这种函数，由我们创建但是不由我们调用的，成为回调函数
  - 数组中有几个函数，就会执行几次，每次执行时，浏览器会将遍历到的元素以实参的形式传递进来，我们可以定义形参，来读取这些内容。
  - 浏览器会在回调函数中传递三个参数
    - 第一个参数，就是当前正在遍历的元素
    - 第二个参数，当前正在遍历元素的索引
    - 第三个参数，当前正在遍历的数组

```javascript
arr.forEach(function() {
    console.log("hhh");
});
```

##### 48-函数的方法

- call() 和 apply()

  - 这两个方法都是函数对象的方法，需要通过函数对象来调用

  - 当对函数调用call()和apply()都会调用函数执行

  - 在调用call()和apply()可以将一个对象指定为第一个参数，此时这个对象将会成为函数执行时的this

  - call()方法可以将实参在对象之后一次传递

  - apply()方法需要将实参封装到一个数组中统一传递

    ```javascript
    fun.call(obj,2,3);
    fun.apply(obj,[2,3]);
    ```

    

- this的情况
  - 1.以函数的形式调用，this永远都是window
  - 2.以方法形式调用，this是调用方法的对象
  - 3.以构造函数的形式调用时，this是新创建的那个对象
  - 4.使用call和apply调用时，this是指定的那个对象

##### 49-arguments

在调用函数时，浏览器每次都会传递进两个隐含的参数：

​	1.函数的上下文对象this

​	2.封装实参的对象arguments

		- arguments是一个类数组对象，它也可以通过索引来操作数据，也可以获取长度
  - 在调用函数时，我们所传递的实参都会在arguments中保存
    - arguments.length可以用来获取实参的长度
    - 即使不定义形参，也可以通过arguments来使用实参
      - arguments[0]表示第一个实参
      - arguments[1]表示第二个实参
- arguments的一个属性callee
  - 这个属性对应一个函数对象，就是当前正在指向的函数的对象

```javascript
function fun() {
    console.log(arguments[1]);
}
fun("hello",true);//"true";0是hello

```

##### 50-Date对象

- 在JS中使用Date对象来表示一个时间

```javascript
//如果直接使用构造函数创建一个Date对象，则会封装为当前代码执行的时间。
var d = new Date();
console.log(d);
```

```javascript
//创建一个指定的时间对象，需要在构造函数中从传递一个表示时间的字符串作为参数
//日期的格式 月/日/年 时:分:秒
var d2 = new Date("2/27/2020 17:54:00");
var date = d2.getDate();
var day = d2.getDay();
console.log(date);
//getDate() 获取当前日期对象是几日
//getDay() 获取当前日期对象是周几，会返回一个0-6的值，0表示周日，1周一
//getMonth()
```



- getDate() 获取当前日期对象是几日
- getDay() 获取当前日期对象是周几
  - 会返回一个0-6的值，0表示周日，1周一
- getMonth() 获取当前时间对象的月份
  - 会返回一个0-11的值
  - 0表示1月
  - 1表示2月
  - 所以平时要+1表示真实月份

- getFullYear() 以四位数字返回当前年份

- getTime() 
  - 获取当前日期对象的时间戳
  - 时间戳：指的是从格林威治标准时间的1970年1月1日，0时0分到当前日期所花费的毫秒数(1秒 = 1000毫秒)
    - 计算机底层在保存时间时使用的都是时间戳

##### 51-包装类

- JS中提供了三个包装类，通过这三个包装类可以将基本数据类型转换为对象
  - String()
    - 可以将基本数据类型字符串转换为String对象
  - Number()
    - 可以将基本数据类型转换为Number对象
  - Boolean()
    - 可以将基本数据类型转换为Boolean对象
- 但是：实际过程中不使用基本数据类型对象，因为对象比较是比较地址，容易出现值相同但是比较为false，做一些比较可能会带来一些不可预期的结果。

```javascript
//创建一个Number类型的对象
//num = 3; 这个是基本数据类型
var num = new Number(3);
console.log(typeof num);//object

```



- 方法和属性只能添加给对象，不能添加给基本数据类型

  - 当我们对一些基本数据类型的值去调用属性和方法时，浏览器会临时使用包装类将其转换为对象，然后再调用对象的属性和方法，调用以后，再将其转换为基本数据类型。

    ```javascript
    var s = 123;
    s = s.toString();
    s.hello = "你好"; //这里转换了两次
    console.log(s.hello);//undefined
    //这里s.hello是想调用s对象的基本数据类型里的hello属性
    //但是对象里没有这个属性，上一句转换的两次不是同一个对象
    console.log(typeof s);//string
    ```

    

##### 52-字符串相关方法

- 再底层字符串是以字符数组形式保存的

  ["h","e","l"]

###### length

- 可以获取字符串的长度

###### charAt()

- 可以返回字符串中指定位置的字符

- 根据索引获取指定的字符

  ```javascript
  str = "Hbcdefg";
  str.charAt(0);
  console.log(str);//"H"
  ```

###### charCodeAt()

- 获取指定位置字符串的字符编码（Unicode编码)

  ```javascript
  result = str.charCodeAt(0);
  console.log(result);//72
  ```

###### formCharCode()

- 可以根据字符编码去获取字符

  ```javascript
  result = String.formCharCode(72);
  console.log(result);//H
  ```

###### concat()

- 连接两个或多个字符串
- 作用和+号一样

###### indexOf()

- 该方法可以检索一个字符串中是否含有指定内容
- 如果字符串含有该内容，则会返回其第一次出现的索引，如果没有找到指定内容，则返回-1
- 可以指定第二个参数，指定查找位置

```javascript
str = "abcda";
result = str.indexOf("a");
console.log(result);//0
result = str.indexOf("a",1);
console.log(result);//4
```

###### lastIndexOf()

- 该方法和indexOf()一样，不同的是indexOf从前往后找，lastIndexOf从后往前找

###### slice()

- 从字符串总截取指定的内容

- 不会影响原字符串，将截取的内容返回

  - 参数

    1.开始的位置

    2.结束位置的索引（不包括结束的位置）

    如果省略第二个，则截取到后边所有的

    也可以传递一个负数作为参数，负数会从后边计算。

###### substring()

- 截取一个字符串，与slice()类似

  - 参数

    - 1.开始的位置

    - 2.结束位置的索引

      不同的是：这个方法不能接受负值作为参数，如果传递一个负值，则默认使用0

      而且还自动调整参数的位置，如果第二个参数小于第一个，则自动交换

###### substr()

- 截取字符串
  - 参数
    - 1.截取开始位置索引
    - 2.截取长度

###### split()

- 将字符串拆分为一个数组
  - 参数
    - 需要一个字符串作为参数，将会根据该字符串去拆分数组
    - 如果传递一个空串作为参数，则会将每个字符都拆开

###### toUpperCase()

- 将一个字符串转换为大写并返回

##### 53-正则表达式

- 用于定义一些字符串的规则，计算机可以根据正则表达式，来检查一个字符串是否符合规则，获取将字符串中符合规则的内容提取出来

- 语法：

  - var 变量 = new RegExp("正则表达式","匹配模式");
  - 使用typeof检查正则对象，会返回object
  - var reg = new RegExp("a");这个表达式可以用来检测字符串中是否含有a ，严格区分大小写
    - 在构造函数中可以传递一个匹配模式作为第二个参数，可以是
      - i 忽略小写
      - g 全局匹配模式

  ```javascript
  //创建正则表达式的对象
  var reg = new RegExp("a");
  console.log(reg);// "/a/"
  console.log(typeof reg);//object
  
  //正则表达式的方法：
  //	test()
  // 使用这个方法可以用来检查一个字符串是否符合正则表达式，如果符合返回true，否则返回false
  var str = "a";
  var result = reg.test(str);
  console.log(result);//true
  cosnole.log(reg.test("abc"));//true
  cosnole.log(reg.test("ddc"));//false
  ```

###### 使用字面量来创建正则表达式

- 语法： var 变量 = /正则表达式/匹配模式

  - 使用字面量来创建更加简单，使用构造函数创建更加灵活。

  ```javascript
  //var reg = new RegExp("a");
  var reg = /a/i;
  ```

```javascript
//创建一个正则表达式，检查一个字符串中是否有a或b
// 使用 | 表示 或的意思
reg = /a|b/;
cosnole.log(reg.test("bcd"));//false
```

```javascript
//创建一个正则表达式检查一个字符串中是否有字母
// []里的内容也是或的关系
// [ab] == a|b
// [a-z] 任意小写字母
// [A-Z] 任意大写字母
// [A-z] 任意字母
reg = /[a-z]/;//任意小写字母
```

-  \[^ ] 除了

  ```javascript
  reg = /[^ab]/;//除了ab以外
  ```

###### 量词

- 通过量词可以设置一个内容出现的次数
- 两次支队它前边的一个内容起作用
- {n} 正好出现n次
- {m,n} 出现m-n次
- {m,} m次以上
- \+ 至少一个，相当于{1,}
- \* 0个或多个，相当于{0,}

- ？ 0个或1个，相当于{0，1}
- ^ 表示开头
- $ 表示结尾
- \w 任意字母、数字、_ 相当于[A-z0-9_]
- \W 除了字母、数字、_ 相当于[A-z0-9_]
- \d 任意的数字 [0-9]
- \D 除了数字
- \s 空格 大写除了空格
- \b 单词边界

```javascript
var reg = /ab{3}/;
console.log(reg.test("abbb"));//true
reg = /(ab){3}/;
console.log(reg.test("ababab"));//true
```

```javascript
reg = /^a/;//以a开头
reg = /^a$/;
console.log(reg.test("aaa"));//false;这个reg表示a既是开头又是结尾
console.log(reg.test("a"));//true
```

```javascript
//创建一个正则表达式，用来检查一个字符串是否是一个合法手机号
//手机号规则：
// 1 5 111115678 (11位)
// 1.以1开头
// 2.第二位3-9任意数字
// 3.第三位以后任意数字9个

// ^1 [3-9] [0-9]{9}$

var phoneStr = "1511115678";
var phoneReg = /^1[3-9][0-9]{9}$/;
```

```javascript
//检查一个字符串中是否有 .
// . 表示任意字符
reg = /\./;
//注意：在使用构造函数时，由于它的参数是一个字符串，而\是字符串中的转义字符，如果要使用\则要用\\来代替
```

```javascript
//检查一个字符串是否含有单词world
reg = /\bchild\b/;
```

```javascript
//去掉字符串中的空格
//去除空格就是使用 ""来替换空格
var str = "            hello    ";
str = str.replace(/\s/g , "");//hello
str = "     he  llo      ";
//去除开头空格 
//如果不加*就只会去除开头的1个空格
str = str.replace(/^\s*/ , "");//he  llo 
//去结尾的空格
str = str.replace(/\s*$/ , "");//     he  llo
//整合
str = str.replace(/^\s*|\s*$/g , "");//he    llo
```

##### 54-字符串和正则相关的方法

###### split() 

- 将字符串拆分一个数组

- 方法中可以传递一个正则表达式作为参数，这样方法将会根据正则表达式去拆分字符串

  ```javascript
  //根据任意字母来拆分字符串
  var str = "1h2k3k5l6o";
  var result = str.split(/[A-z]/);
  cosnole.log(result);//1,2,3,4,5,6
  ```

###### search()

- 可以搜索字符串中是否含有指定内容
- 如果搜索到指定内容，则会返回第一次出现的索引，如果没有搜索到返回-1
- 它可以接收一个正则表达式作为参数，然后会根据正则表达式去检索字符串
- search只会查找第一个，即使设置全局匹配也没用

```javascript
str = "hello abc aaa ddd";
result = str.search("abc");
cosnole.log(result);//6
```

###### match

- 可以根据正则表达式，从一个字符串中符合条件的内容提取出来
  - 默认情况下match只会找到第一个符合的内容，找到后就停止检索，可以设置正则表达式为全局模式，这样就会匹配到所有的内容
  - 可以为一个正则表达式设置多个匹配模式，且顺序无所谓

- match()会将匹配到的内容封装到一个数组中返回，即使只查询到一个结果

###### replace

- 可以将字符串中指定的内容替换为新的内容

  - 参数

    - 1.被替换的内容
    - 2.新的内容

    默认只会替换第一个

    ```javascript
    result = str.replace("a","@_@");
    ```

    

##### 55-邮件规则

hello .nihao @ abc .com .cn

任意字母数字下划线 .任意字母数字下划线 @ 任意字母数字 .任意字母（2-5位） .任意字母（2-5位）

\w{3,} (\\.\w+)*  @  [A-z0-9]+   (\\.[A-z]{2,5}){1,2} 

```javascript
var emailReg = /^\w{3,}(\\.\w+)*[A-z0-9]+(\\.[A-z]{2,5}){1,2}$/;// ^ 和 $ 不能少 表明整个邮件是一个整体
var email = "abc.hello@163.com";
console.log(emailReg.test(emal));
```

- 平时可以去找常用的正则表达式

#### DOM-Document Object Model

文档对象模型

##### 56-DOM

- 作用：JS通过DOM来操作网页

- 文档：

   	   - 表示整个HTML网页文档

- 对象：

  ​		- 将网页中的每一个部分都转换为了一个对象

- 模型：

  ​		- 使用模型来表示对象之间的关系，方便获取对象。

##### 57-事件

- 就是文档或浏览器窗口中发生的一些特顶的交互瞬间。（用户和浏览器之间的交互行为：点击按钮，移动鼠标，关闭窗口等）
- JS与HTML之间的交互是通过事件实现的

###### onload

- 在整个页面加载之后才触发

- 为window绑定一个onload事件

  - 该事件对应的响应函数会在页面加载完成之后执行，这也可以确保代码执行时所有的DOM对象已经加载完毕了

  ```java
  window.onload = function(){
      alert("hello");
  };
  ```

###### 获取元素节点

- 通过document对象调用
  - 1.getElementById() 通过id获取一个元素节点对象
  - 2.getElementsByTagName() 通过标签名获取一组元素节点对象
  - 3.getElementsByName() 通过name获取一组元素节点对象
- 
- innerHTML用于获取元素内部的HTML代码
  - 对于自结束标签，这个属性没有意义
- 如果需要读取元素节点属性，直接使用 元素.属性名
  - 元素.id 元素.name 元素.value
  - 但：class属性不能采用这种方式，因为class是JS中的保留字,所有读取class属性时需要使用 **元素.className**

###### childNodes

- 获取所有子节点，包括空白文档

###### children

- 获取当前元素的所有子元素

###### firstChild

- 可以获取到当前元素的第一个子节点(包括空白文本节点)
- lastChild同理

###### firstElementChild

- 获取当前元素的第一个子元素（不包括空白
- 但此方法只支持ie9以上的浏览器

##### 58-DOM查询剩余的方法

###### body

- 在document中有个属性body，它保存的是body的引用

  ```javascript
  var body = document.body;
  ```

###### html

- document.documentElement保存的是html根标签

  ```javascript
  var html = document.documentElement;
  ```

###### all

- document.all代表页面中的所有元素

  ```javascript
  var all = document.all;
  all = document.getElementsByTagName("*");
  //两种方法相同 得到的length都是一样的
  ```

###### 根据元素的class属性查询一组元素节点对象

getElementsByClassName() 该方法不支持IE8以下的浏览器

###### querySelector()

- 需要一个选择器的字符串作为参数，可以根据一个CSS选择器来查询一个元素节点对象.

  - 虽然IE8中没有getElementsByClassName,但是可以使用querySelector()代替

  ```javascript
  document.querySelector(".box1 div");
  ```

- 使用该方法总会返回唯一的一个元素，如果满足条件的元素有多个，那么它只会返回第一个

###### querySelectorAll()

- 该方法和querySelector()类似，不同的是它会将符合条件的元素封装得到一个数组中返回
- 即使符合条件的元素只有一个，也会返回一个数组

##### 59-DOM增删改

###### createElement()

- document.createElement()

  可以用于创建一个元素节点对象，

  它需要一个标签名作为参数，将会根据该标签名创建元素节点对象，并将创建好的对象作为返回值返回。

  ```javascript
  11111111
  //创建一个广州节点<li>广州</li>
  //创建li元素节点
  var li = document.createElement("li");
  ```

###### createTextNode()

- document.createTextNode()

  可以用来创建一个文本节点对象

  需要一个文本内容作为参数，将会根据该内容创建文本节点，并将新的节点返回

  ```javascript
  22222222
  //创建广州文本节点
  var gzText = document.createTextNode("广州");
  ```

###### appendChild()

- appendChild()

  向一个父节点中添加一个新的字节点

  用法：父节点.appendChild(字节点);

  ```javascript
  33333333
  li.appendChild(gzText);
  //获取id为city的节点
  var city = document.getElementById("city");
  //将广州添加到city下
  city.appendChild(li);
  ```

  

**11111111-3333333 是创建一个节点并添加**

###### insertBefore()

- 可以在指定**子节点**前插入新的字节点

  语法：

  ​	父节点.insertBefore(新节点，旧节点);

```javascript
44444444
//将"广州"节点插入到#bj前面
myClick("btn02",function(){
    //创建一个广州
    var li = document.getElementById("li");
    var gzText = document.createTextNode("广州");
    li.appendChild(gzText);
    //获取id为bj的节点
    var bj = document.getElementById("id");
    //获取city
    var city = document.getElementById("city");
    city.insertBefore(li , bj);
});
```

###### replaceChild()

- 可以使用指定的子节点替换已有的字节点

  语法：

  ​	父节点.replaceChild(新节点,旧节点);

```javascript
55555555
//使用“广州”节点替换#bj节点
myClick("btn03",function(){
    //创建一个广州
    var li = document.getElementById("li");
    var gzText = document.createTextNode("广州");
    li.appendChild(gzText);
    //获取id为bj的节点
    var bj = document.getElementById("id");
    //获取city
    var city = document.getElementById("city");
    city.replaceChild(li , bj);
});
```

###### removeChild()

- 可以删除一个字节点
- 语法：
  - 父节点.removeChild(字节点);
  - 字节点.parentNode.removeChild(字节点);
    - 当不知道父节点是什么的时候，使用parentNode

```javascript
66666666
//删除#bj节点
myClick("btn04",function(){

    //获取id为bj的节点
    var bj = document.getElementById("id");
    //获取city
    //var city = document.getElementById("city");
    //city.removeChild(bj);
    bj.parentNode.moveChild(bj);
});
```

###### innerHTML

```javascript
//读取#city内的HTML代码
myClick("btn05",function(){
    //获取city
    var city = document.getElementById("city");
    alert(city.innerHTML);
});
```

```javascript
//设置#bj内的HTML代码
myClick("btn06",function(){
    //获取bj
    var bj = document.getElementById("bj");
    bj.innerHTML = "昌平";
});
```

```javascript
//向city中添加广州使用innerHTML方法
myClick("btn07",function(){
    //获取bj
    var city = document.getElementById("city");
    //city.innerHTML = "<li>广州</li>";只这样写会导致所有按钮都消失变为只有一个广州
    city.innerHTML += "<li>广州</li>";
    //改成+= 就会在原来的基础上添加一个广州
    //但是！！这个方法虽然简单，但是每次修改都会把原来所有内容先删除再增加，动静太大，不建议这么用
});
```

- 使用innerHTML也可以完成DOM的增删改相关操作，一般会两种方式结合使用

```javascript
//创建一个li
var li = document.createElement("li");
//向li中设置文本
li.innerHTML = "广州";
//将li添加到city中
city.appendChild(li);
```

###### 练习-添加删除记录

- 想要使超链接点击后不跳转有两种方法：
  - 1.在函数里设置 返回 return false；
  - 2.在HTML代码设置超链接 href="javascript:;"

```javascript

```

##### 60-操作内联样式

- 通过JS修改元素的样式：

  语法：元素.style.样式名 = 样式值

- 注意：

  ​		如果CSS的样式种含有 - ,

  ​		这种名称在JS中是不合法的,如background-color,需要将这种样式改为驼峰命名法，去掉-，然后将-后的字母大写

- 我们通过style属性设置的样式都是内联样式，而内联样式有较高的优先级，所以通过JS修改的样式往往会立即执行。

  - 但如果写了!important，则此时样式会有最高的优先级，即使通过JS也不能覆盖该样式，此时将会导致JS修改样式失效，所以尽量不要为样式添加!important

- 通过style属性设置和读取的都是内联样式，无法读取样式表中的样式

###### getComputedStyle()

- 用这个方法来获取当前的样式 (currentStyle.width只有IE能用)，该方法不支持IE8及以下浏览器,通过currentStyle和getComputedStyle()读取到的样式都是只读的，不能修改，如果要修改必须通过style属性

- 这个方法是window的方法，可以直接使用

  - 参数：

    1.要获取样式的元素

    2.可以传递一个伪元素，一般都传null

  - 该方法会返回一个对象，对象中封装了当元素对应的样式,通过 对象.样式名来读取样式

    如果获取的样式没有设置，则会获取到真实的值，而不是默认值

    ​	如：没有设置width，不会获取到auto，而是一个长度

```javascript
var obj = getComputedStyle(box1.nll);
alert(obj.width);
```

###### 获取指定元素的当前样式

- 定义一个函数，获取指定元素的当前样式

  参数：

  ​	obj 要获取样式的元素

  ​	name 要获取的样式名

```javascript
function getStyle(obj, name) {
    //正常浏览器的方式
    //return getComputedStyle(obj, null)[name];
    //IE8的方式
    //return obj.currentStyle[name];
    if(window.getComputedSyle){//如果不加window. 原来的getComputedSyle是一个变量，要去作用域中寻找，如果没找到就会报错，但是加了window之后就是一个属性，没找到就返回undefined
        return getComputedStyle(obj, null)[name];
    }else{
        return obj.currentStyle[name];
    }
}
```

