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