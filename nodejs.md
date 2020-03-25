### ES6

#### 常量

```javascript
//ES5
Object.defineProperty(window,"PI2", {
    value:3.1415926,
    writable:false,
})

//ES6 常量的写法
const PI = 3.141592653
console.log(PI)
```

#### 作用域

```javascript
//ES5中的作用域
var callbacks = []
for (var i=0; i<=2 ;i++) {
    callbacks[i] = function() {
        return i * 2
    }
}
console.table([
    callbacks[0](), //6
    callbacks[1](), //6
    callbacks[2](), //6
])
//ES6
const callbacks2 = []
for (let j = 0; j<=2; j++){
    callbacks2[j] = function() {
        return j * 2
    }
}
console.table([
    callbacks2[0](), //0
    callbacks2[1](), //2
    callbacks2[2](), //4
])
//用let声明的变量有块作用域的概念，
//这个时候的闭包，它是取决于当前的块作用域即花括号
//会把当前块作用域下的变量的值保存供后面的闭包使用
//每循环一次就会重新生成一个新的作用域，闭包就导向闭包作用域里的变量，所以是0,2,4
```

#### 箭头函数

```javascript
//ES5
function a(){
    
}

//ES6
()=>{
    
}
```

```javascript
//ES3,ES5
{
    var evens = [1,2,3,4,5];
    var odds = evens.map(function(v) {
      return v+1;
    });
    console.log(evens , odds);
};

//ES6
{
    let evens =[1,2,3,4,5];
    let odds = evens.map(v => v+1);
    console.log(evens,odds);
}
```

```javascript
//ES3,ES5
{
  var factory = function(){
      this.a = a;
      this.b = 'b';
      this.c = {
          a:'a+',
          b:function() {
              return this.a
          }
      }
  }  
  console.log(new factory().c.b());//a+
    //因为c调用b方法，而c是一个对象 this指向c
};

//ES6
{
  var factory = function(){
      this.a = 'a';
      this.b = 'b';
      this.c = {
          a:'a+',
          b:() => {
              return this.a
          }
      }
  }  
  console.log(new factory().c.b());//a
    //箭头函数函数体中this的指向是函数体定义时的指向
    //b在定义这个函数的时候，this指向的是函数体中的this，这个this指向的是构造函数function的实例
    //虽然调用的是b对象，但是b对象中的this指向的是实例new factory，而new factory的实例是a，所以结果是'a'
};
```

#### 默认参数

```javascript
//ES3,ES5
{
    function f(x, y, z) { 
    	if(y === undefined) {
            y = 7;
        }
        if(z === undefined) {
            z = 42;
        }
        return x + y + z;
    }
    console.log(f(1,3));//46
}
//ES6
{
    function f(x, y = 7, z = 42) {
        return x + y + z
    }
    console.log(f(1,3));//46
}


{
    function checkParameter() {
        throw new Error('can\'t be empty')
    }
    function f(x = checkParameter(), y = 7, z = 42) {
        return x + y + z
    }
    console.log(f(1));
    try {
        f()
    } catch (e) {
        console.log(e);
    } finally {
        
    }
}
```

```javascript
//ES3,ES5可变参数
{ 
    function f(){
        var a = Array.prototype.slice.call(arguments);
        var sum = 0;
        a.forEach(function(item){
            sum+=item*1;
        })
        return sum
    }
    console.log(f(1,2,3,6));//12
}
//ES6可变参数
{
    function f(...a){//...a表示a就是可变参数的列表并且是个数组，...是扩展运算符
        var sum=0;
        a.forEach(item=>{
            sum+=item*1;
        });
        return sum
    }
    console.log(f(1,2,3,6));//12
}
```

```javascript
//ES5合并数组
{
    var params = ['hello',true,7];
    var other =[1,2].concat(params);
    console.log(other);
}
//ES6 利用扩展运算符合并数组
{
    var params = ['hello', true, 7];
    var other = [
        1, 2, ...params
    ];
    console.log(other);
}
//[1,2,"hello",true,7]
```

#### 对象代码

```javascript
//ES3,ES5 数据保护
{
    var Person = function(){
        var data = {
            name:'es3',
            sex: 'male',
            age:15
        }
        this.get = function(key) {
            return data[key]
        }
        this.set = function(key,value) {
            if(key !== 'sex') {
                data[key] = value
            }
        }    
    }
    
    //声明一个实例
    var person = new Person();
    //读取
    console.table({
        name: person.get('name'),sex:person.get('sex'), age: person.get('age')
    });
    //修改
    person.set('name','es3-cname');
    console.table({name: person.get('name'),sex:person.get('sex'), age: person.get('age')});
    person.set('sex','female');
    console.table({name: person.get('name'),sex:person.get('sex'), age: person.get('age')});
}

//ES5
{
    var Person = {
        name: 'es5',
        age:15
    };
    Object.defineProperty(Person,'sex',{
        writable:false;
        value:'male'
    });
	
    console.table({
        name:Person.name,
        age:Person.age,
        sex:Person.sex
    });
    Person.name='es5-cname';
    console.table({
        name:Person.name,
        age:Person.age,
        sex:Person.sex
    });
    //改性别就不行

	
    try{
      Person.sex='female';
      console.table({
    	name:Person.name,
        age:Person.age,
        sex:Person.sex
     });
    } catch (e) {
        console.log(e);
    }
}
//ES6
{	
    //声明对象
    let Person={
        name:'es6',
        sex:'male',
        age:15
    };
    //Proxy代理
    //person是暴露给用户将来操作的对象，把声明的Person保护下来
    //暴露出的person通过Proxy和Person挂钩，Proxy代理的是原始数据
    let person = new Proxy(Person, {
        get(target,key) {
        //target是代理的数据，key是属性
            return target[key]
        },
        //与es3类似但是方便很多，可以在set里写各种限制
        set(target,key,value){
            if(key!=='sex'){
                target[key]=value;
            }
        }
    });
    console.table({
        //person是用户访问到代理后的对象
    	name:Person.name,
        age:Person.age,
        sex:Person.sex
    });
    try {
        person.sex = 'female';
    } catch (e) {
        console.log(e);
    } finally {
        
    }
}
```





### Node.js

### 模块

###### 引入其他模块

- 在node中，通过require()函数来引入外部的模块

- require()可以传递一个文件的路径作为参数，node将会自动根据该路径来引入外部模块

  ​    这里路径，如果使用相对路径，必须以.或..开头

- 使用require()引入模块以后，该函数会返回一个对象，这个对象代表的是引入的模块

- 我们使用require()引入外部模块时，使用的就是模块标识，我们可以通过模块标识来找到指定的模块

  \- 模块分成两大类

​    核心模块

​      \- 由node引擎提供的模块

​      \- 核心模块的标识就是，模块的名字

​    文件模块

​      \- 由用户自己创建的模块

​      \- 文件模块的标识就是文件的路径（绝对路径，相对路径）

​        相对路径使用.或..开头

//var md = require("./02.module");

var math = require("./math");

var fs = require("fs");



//console.log(md);

console.log(math.add(123,456));

//console.log(fs);

- 在node中有一个全局对象 global，它的作用和网页中window类似

​    在全局中创建的变量都会作为global的属性保存

​    在全局中创建的函数都会作为global的方法保存

- 当node在执行模块中的代码时，它会首先在代码的最顶部，添加如下代码

​      function (exports, require, module, __filename, __dirname) {

  在代码的最底部，添加如下代码

​      }

- 实际上模块中的代码都是包装在一个函数中执行的，并且在函数执行时，同时传递进了5个实参

​     exports

​      \- 该对象用来将变量或函数暴露到外部



​     require

​      \- 函数，用来引入外部的模块



​     module

​      \- module代表的是当前模块本身

​      \- exports就是module的属性

​      \- 既可以使用 exports 导出，也可以使用module.exports导出



​     __filename

​      C:\Users\lilichao\WebstormProjects\class0705\01.node\04.module.js

​      \- 当前模块的完整路径



​     __dirname

​      C:\Users\lilichao\WebstormProjects\class0705\01.node

​      \- 当前模块所在文件夹的完整路径



###### exports 和 module.exports

- 通过exports只能使用.的方式来向外暴露内部变量

​      exports.xxx = xxx

- 而module.exports既可以通过.的形式，也可以直接赋值

​      module.exports.xxx = xxxx

​      module.exports = {}

### 包package

#### NPM - Node Package Manager

### fs（文件系统）

