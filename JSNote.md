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