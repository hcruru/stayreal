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