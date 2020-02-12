# JavaScript深入浅出笔记

### try  catch

- try catch提供了一个异常捕获的机制，首先try块中代码，若抛出异常，catch语句捕获并执行，若没有，则不执行，最终一定会执行finally。
- try后一定要接一个catch或者finally语句

### 函数

- 函数声明 和 函数表达式

  - 前者在声明前调用函数——函数前置，可以调用成功
  - 后者函数表达式不可以

  ​	//fd(); //true

  ​	function fd (){

  ​	return true;

  ​	}//函数声明

  ​	//函数表达式

  ​	//fe(); //TypeError

  ​	var fe = function () {

  ​		//do sth;

  ​	};

### 严格模式

- 严格模式是一种特殊的执行模式，它修复了部分语言上的不足，提供更强的错误检查，并增强安全性。

  function func () {

  'use strict';

  }

  或

  'use strict'

  function func () { }

## Ch4

### 属性读写

- var obj = {x:1, y:2};

  obj.x;   // 1

  obj["y"];  //2

  一般采用.的形式进行读

  对于循环需要遍历，采用 obj['x'+i] 这种方式

#### 属性读写-异常

- var yz; 

  if (obj.y) {

  ​	yz = obj.y.z;

  }

- var yz = obj && obj.y && obj.y.z;  //存在返回z的值，不存在返回undefined；采用运算符实现链式读取

### 属性删除

- var person = {age : 28, title : 'fe'};

  delete person.age;//true;

  person.age;//undefined

  delete person.age; // true;

- 注意：delete返回true并不一定代表删除了属性，只能说明属性不存在，因为当属性已经删除再对不存在属性进行delete返回的依旧是true。

- Object.prototype属性是不允许删除的，会返回false

  - delete Object.prototype; //false

    var descriptor = Object.getOwnPropertyDescriptor(Object, 'prototype');

    descriptor.configurable;  //false

    最后一句中的描述器descriptor调用可配置属性configurable，返回false，决定了第一句delete的返回false,并且不会生效。

- 用var定义的全局变量，局部变量，仍然不能被删除

  - var globalVal = 1;

    delete globalVal;   //false

  - (function() {

    ​	var localVal = 1;

    ​	return delete localVal;

    }());   //false

- 函数声明同理，不管是全局函数还是在函数内部局部作用域的函数，同样不能删除：

  - function fd () {}

    delte fd; //false

  - (function() {

    ​	function fd() {};

    ​	return delete fd;

    }());   //false

- 隐式创建的全局变量可以删除(一般不建议)

  ohNo = 1;

  window.ohNo; //1

  delete ohNo; // true

- eval中定义的也可以删除

### 属性检测

- var cat = new Object;

  cat legs = 4;

  'legs' in cat;//true；注意，in会返回到原型链查找，所以假如返回true也可能是原型链中的属性而不是对象中的

  "toString" in cat; // true,inherited property

  cat.hasOwnProperty('toString'); //false

  - 属性是否可被枚举

  cat.propertyIsEnumerable('legs');//true

  cat.propertyIsEnumerable('toSring'); //false

#### 设置枚举属性

- Object.defineProperty(cat,'price',{enumerable:false, value :1000})  //这种方式设置默认为false，其它的是默认为true

  cat.propertyIsEnumerable('price');  //false

  cat.hasOwnProperty('price');   //true

#### 属性枚举

- 在onenote笔记中

### 对象标签

#### extensible标签

- 是否可扩展

- 当调用seal属性，会将configurable设置为false

  ```javascript
  Object.seal(obj);
  Object.getOwnPropertyDescriptor(obj,'x');
  //Object {value: 1, writable: true, enumerable: true, configurable: false}
  Object.isSealed(obj);//true 这个方法用来判断是否被隐藏即被seal
  ```

### 对象序列化

- 对于前端数据传给后端，要对数据进行序列化，通过全局的JSON对象的stringify做序列化处理。

```javascript
var obj = {x : 1. y : true, z : [1, 2, 3], nullVal : null};
JSON.stringify(obj);   //通过这个方法会返回一个字符串"{"x":1,"y":true,"z":[1, 2, 3],"nullVal":null}"
```

【注意】

​	1.假如某个属性是"undefined"则这个属性值不会出现在序列化中。

​	2.NaN,Infinity会转化为null,Date会转化为时区时间（这个词不太确定

- 将后端传入的数据解析成JavaScript

  ```javascript
  obj = JSON.parse('{"x" : 1}');
  obj.x; //1
  ```

  这样就拿到了一个1

### 小结

- 对象的结构
- 创建对象
- 属性操作
- getter setter
- 属性标签
- 对象标签
- 序列化
- 对象方法

## Ch5

### 数组

- 数组是值的有序集合。每个值叫做元素，每个元素在数组中都有位置编号，即索引。

  JS中的数组是弱类型的（不同于Java等其它语言),数组中可以含有不同类型的元素。

  数组元素甚至可以是对象或其它数组。

  ```javascript
  var arr = [1, true, null, undefined, {x:1}, [1, 2, 3]];
  ```

  - arr[0]
  - arr[3]
  - arr[4].x
  - arr[5]返回一个子数组,arr[5]\[1]得到数字2

- JS中的数组是动态的，无需指定大小

### 数组元素增删

- 增

  ```javascript
  var arr = [];
  arr.[0] = 1;
  //在最后一个元素之后添加元素
  arr.push(2); //用push方法
  arr; //[1,2]
  arr[arr.length] = 3; //length
  arr;//[1,2,3]
  //在第一个元素之前添加元素,通过unshift方法
  arr.unshift(0);
  arr; //[0, 1, 2, 3]
  ```

- 删

  ```javascript
  delete arr[2];
  arr; // [0, 1, undefined, 3, 4]
  arr.length; // 5
  2 in arr; // false
  
  arr.length -= 1;
  arr; // [0, 1, undefined, 3, 4],  4 is removed
  
  arr.pop(); // 3 returned by pop
  arr; // [0, 1, undefined], 3 is removed
  
  arr.shift(); // 0 returned by shift
  arr; // [1, undefined]
  
  ```

  

### 数组方法

#### 1~5这5种方法都是继承prototype的方法

#### 1-Array.map 数组映射

```javascript
var arr = [1, 2, 3];
arr.map(function(x) {
    return x + 10;
}); //[11, 12, 13]
arr; //[1, 2, 3]
//原始数组未改变，map返回映射结果
```

#### 2-Array.filter数组过滤

```java
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
arr.filter(function(x, index) {
     return index % 3 === 0 || x >= 8;
}); // returns [1, 4, 7, 8, 9, 10]
arr; // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
//原始数组未改变
```

#### 3-Array.every & some 数组判断

- every即每一个都要符合

  ```javascript
  var arr = [1, 2, 3, 4, 5];
  arr.every(function(x) {
       return x < 10;
  }); // true
  
  arr.every(function(x) {
       return x < 3;
  }); // false
  
  ```

  ```javascript
  var arr = [1, 2, 3, 4, 5];
  arr.some(function(x) {
       return x === 3;
  }); // true
  
  arr.some(function(x) {
       return x === 100;
  }); // false
  
  ```

  

#### 4-Array.reduce & reduceRight

- 两两进行操作遍历,最后聚合成唯一的一个结果

  ```javascript
  var arr = [1, 2, 3];
  var sum = arr.reduce(function(x, y) {
       return x + y
  }, 0); // 6
  arr; //[1, 2, 3]
  //第一次1作为x,0作为y进行加法运算得到1，此时结果1作为x，2作为y进行运算，得到结果作为新的x进行运算，遍历到最后得到结果6
  ```

  ```javascript
  arr = [3, 9, 6];
  var max = arr.reduce(function(x, y) {
       console.log(x + "|" + y);
       return x > y ? x : y;
  });
  // 3|9
  // 9|6
  max; // 9
  //返回最大值9
  ```

  

- reduceRight从右往左开始遍历

  ```javascript
  max = arr.reduceRight(function(x, y) {
       console.log(x + "|" + y);
       return x > y ? x : y;
  });
  // 6|9
  // 9|3
  max; // 9
  
  ```

#### 5-Array.indexOf & lastIndexOf

- indexOf从左至右查找
- lastIndexOf从右至左查找

```javascript
var arr = [1, 2, 3, 2, 1];
arr.indexOf(2); // 1
arr.indexOf(99); // -1
arr.indexOf(1, 1); // 4
arr.indexOf(1, -3); // 4
arr.indexOf(2, -1); // -1
arr.lastIndexOf(2); // 3
arr.lastIndexOf(2, -2); // 3
arr.lastIndexOf(2, -3); // 1

```

#### 判断数组isArray

```javascript
Array.isArray([]); // true

```

```javascript
[] instanceof Array; // true
({}).toString.apply([]) === '[object Array]'; // true
[].constructor === Array; // true

```

### 数组小结

#### 数组 VS 一般对象

- 相同：

  都可以继承，数组是对象，对象不一定是数组，

  都可以当做对象添加删除属性

- 不同：

  数组自动更新length，按索引访问数组常常比访问一般对象属性明显迅速。

  数组对象继承Array.prototype上的大量数组操作方法

#### 数组 VS 字符串

```javascript
var str = "hello world";
str.charAt(0); // "h"
str[1]; // e

Array.prototype.join.call(str, "_");
// "h_e_l_l_o_ _w_o_r_l_d"

```

## Ch6

### bind与new

- bind方法：
  - 1.改变this指向
  - 2.科里化，把函数拆成不同功能子函数

```javascript
function foo() {
    this.b = 100; //创建了全局变量b赋值为100
    return this.a; //返回一个全局变量a属性
}
var func = foo.bind({a:1}); //用bind方法传入一个参数字面量属性a
func();  //1 直接调用this会指向bind参数，执行this.a会返回1，由于执行了this.b，相当于对象会有一个属性b值为100,但不会作为返回值
new func(); // {b:100} 
//用new会更特殊，因为return不是对象，就会把this作为返回值，并且this会被初始化为默认的一个空对象，对象的原型是foo.prototype,这里用new调用虽然用了bind方法，但是this仍然会指向没有bind所指向的，这里的空对象b属性设置为100，整个对象又会作为返回值返回，忽略return。
//用new调用，bind的方法对于this这个层面上就会被忽略掉
```

