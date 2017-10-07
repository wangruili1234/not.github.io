##  js高级

### 1 面向对象

**1 面向过程**:我们将解决问题的关注点,放在解决问题的具体细节上,我们关注是如何一步一步的实现功能;

**2 面向对象**:我们将解决问题的关注点,放在解决问题所需要的一系列对象上,重点是找对象,设计对象;

**面向对象本质上是对面向过程的封装**

**面向对象是一种解决问题的思路,一种编程思想**

对象:必须是实实在在存在的东西;万物皆对象

**JavaScript中对象是什么?**JavaScript中,所谓对象就是无序的键值对的集合;(属性和方法);

**3 面向对象的三大特性**:

​	3-1$$ 封装: js中对象本身就是对象属性和方法的封装     我们要实现一个功能,只需要对外界暴露一个接口,外界可以通过接口使用我们的功能,不需要关注内部实现;

​	3-2$$ 继承: js中的继承一个对象拥有一些属性和方法,另一个对象可以通过继承来实现;

​	3-3 多态: 用父 类的变量指向子类的对象(了解 js语法不能直接支持多态);

### 2 构造函数

创建对象的方法:1 new Object 2 字面量 3 自定义构造函数.

###### 自定义构造函数:

######       1 作用:用于创建对象;

######       2 $ 构造函数特点:

​	2-1: 构造函数的函数名首字母大写;

​	2-2: 构造函数 要配合new关键字进行作用;

​	2-3: 构造函数中this指向新创建的对象;

​	2-4: 构造函数不需要返回值,默认返回的是新创建的对象;

###### 	3 $ 构造函数的执行过程:

​	  3-1: new 关键字会开辟内存空间,创建新的对象,并且会用函数内部this指向空对象;

​	  3-2: 构造函数开始执行,开始给this指向的空对象进行赋值;

​	  3-3: 当构造函数执行完成,会将新创建的对象当做返回值进行返回;

###### 	4 注意点:

​	    4-1: 如果写了返回值后果;

​		4-1-1: 如果返回值是值类型,没有影响;

​		4-1-2: 如果返回值是引用类型,会用引用类型的数据替换新创建的对象;

​	     4-2:把构造函数当做普通函数执行(函数里的this指向的就是window);

###### 	5 解决构造函数问题

​	    5-1: 性能问题

​		通过new关键字创建的对象,每个对象都会开辟内存空间,包含对象的方法也会开辟内存空间

​		每个对象的取值不同,但是所有对象的方法代码是一样的,可以共享一份;但是构造函数会给每个对象的方法单独开辟空间造成内存浪费问题

​		解决方案:让所有对象共享一个方法可以解决(原型);

### 3 原型

  **1  原型定义**:每个构造函数在创建出来的同时,系统会自动给构造函数关联一个空的对象,这个对象就是原型;

写在原型中的属性和方法,可以被构造函数创建的所有对象共享;

  **2  原型的访问方式**

​	**构造函数名.prototype**(对象).属性/方法;

​	对象就是实例;实例化就是创建对象的过程;

  **3 原型的使用**

​	3-1 动态添加属性和方法

​	3-2  将与方法和属性的对象赋值给原型

   **4 原型使用注意事项**

​	4-1 使用对象,属性名去获取对象属性的时候,会先在自身函数里找,自身没有再去原型中找,原型也没有  就是 undefind; 

​	4-2 使用对象.属性名去设置属性时,只会在自身查找,自身有则是修改,没有则是添加 跟原型没有关系;

​	4-3 一般情况下不会将属性放在原型中,只会将方法放在原型中;

​	4-4 在替换原型的时候,替换之前创建的对象.和替换之后创建的对象原型不一致;

​	**4-5 内置对象的原型不能覆盖**;

##### 5 对象直接访问原型

​	对象名.`__proto__(两个下滑线)`,非标准的属性,开发不建议使用;

##### 6 原型对象的constructor属性

​      **构造函数名.prototype.constructor**(原型指向构造函数);

```javascript
var obj={
  name="zs"
}
var obj1={}
for(var k in obj){
  obj1[k]=obj[k];
}
```



##### 7 原型继承 

​	1 混入式继承  只能给单个创建的对象继承

```javascript
var obj={
  name="zs"
}
function Person(){}
for(var k in obj){
  person.prototype[k]=obj[k];
}

var p=new Person
```



​	2 原型继承

​	      2-1 原型混入式

​	      2-2  直接替换原型继承   替换原型后constructor属性会丢失;(可以手动添加);[person.prototype.constructor=person];

​	3 经典继承

```javascript
Object.create(原型对象) 静态方法 //在方法内部会创建一个对象,并且让创建的这个对象的原型为参数传进来的这个原型对象(es5,有兼容型问题);


//兼容性处理  浏览器能力检测
var obj1=null;
if(Object.create){
  Object.create(obj);
}else{
  function F(){}
  F.prototype=obj;
  obj1=new F();
}

//函数封装 obj作为原型对象
function create(obj){
  if(Object.create){
    return Object.create(obj);
  }else{
     function F(){}
  	 F.prototype=obj;
  	return new F();
  }
}
```



##### 8 原型链

​	对象有原型,原型本身也是对象,原型也有原型,这样会构成一个链式结构,这个结构就是原型链;

所有的原型链最终都会指向null;

变量搜索原则:

​	当我们用 对象名.属性名去访问一个属性时

​	1 首先会在对象自身中查找,如果找到直接使用,

​	2 如果没有找到,去对象的原型中找,如果找到直接使用;

​	3 如果没找到 会继续去原型的原型中去查找,依次类推,如果找到直接使用

​	4 如果没找到会找到null为止

```	
 function person(){}
  var p=new person();
  console.log(p);
  console.log(p.__proto__);//person的原型
  console.log(p.__proto__.__proto__);//object的原型
 console.log(p.__proto__.__proto__.__proto__);//null
```

### 4 instanceOf 关键字 

####        **instanceof  关键字**

		(1)语法    对象1 instancef 类型1 
		   判断  对象是否是指定的类型(不准确);
		   
	    (2)语法    对象 instanceof 构造函数(本身就是类型)
	       返回的值 是布尔类型;
	       判断该构造函数的原型是否存在于该对象的原型链上

### 5 Object.prototype的属性和方法

​	所有对象都可以使用object.prototype的方法

##### 	5-1 constructor  在原型中 用于指向该原型相关的那个构造函数(属性)

##### 	5-2 hasOwnProperty  

```
	(1)语法  对象.hasOwnProperty(属性名);
	
	判断对象自身是否拥有指定属性和方法
	(2)语法  属性 in 对象 
	判断对象自身 或者对象的原型链上是否拥有指定的属性和方法
```



##### 	5-3 isPrototyprOf

​		

```text
对象1. isPrototyprOf(对象2);

返回值是布尔类型

	判断对象1是否在对象2的原型链上
```

##### 	5-4 propertyIsEnumerable

​	

```text
	判断对象的成员是否可用被for-in遍历,前提是该属性存在
	
	对象.propertyIsEnumerable(属性);
```





##### 	5-5 toString();将数据转成字符串

##### 	toLocalString();将数据转成字符串

```text
	对象.toString();
	对象.toLocalString();
```





##### 	5-6 valueOf()获取当前对象的值

```javascript
	在参与比较时,系统会自动调用valueOf方法 进行求值
    
	对象.valueOf()(返回的数据本身);
	我们可以在创建对象时自己重写valueOf方法,在后续将引用类型转值类型时,就可以使用valueOf方法
 function Person(){
      this.name="zc";
      this.age="12";
      this.gender="nan"
    }
    Person.prototype.valueOf=function(){
      return this.name;
    }//给Person的原型添加一个valueOf这个方法;
    var p=new Person();
    console.log(p.valueOf());//打印出来的是p的构造函数
```

### 6 静态方法和实例方法

​	静态方法 

​		构造函数名.方法名();

​	实例方法

​		对象名.方法名();

```javascript
var arr=new Array();
arr.push("a");//实例方法

Math.random()//静态方法(不需要开辟内存空间)
//静态方法的使用场景,我们只需要使用构造函数的功能,不需要创建对象
```



### 7 Funtion(了解)

##### 创建函数的几种方式:

Function 可以将js代码进行执行(前提:符合js语法规范 ,函数要被调用)

```javascript
1 函数声明 函数字面量
	function test(){};
2 函数表达式
	var test=function(){};
3 new Function()构造函数
	var test=new Function();
new Function(参数1,参数2,参数3...,函数体) 也可以被当做一个构造函数(参数和函数体只能是字符串的数据类型);
 //通过Function new出来函数可以被当做是实例化的对象
  //那么Function这个构造函数也有原型对象
  //Function的原型对象是一个空的函数
  //Function的原型对象的原型对象是Object.prototype

es6字符串新语法  反引号定义字符串 字符串可以随便换行
```

### 8 eval函数(了解  存在安全问题)

​     eval 可以把字符串当做js代码进行解析(字符串符合js语法规则),预解析不会被提前;

```javascript 
eval 计算器案例

<input type="text" id="text-1">
<select name="" id="operate">
  <option value="+">+</option>
  <option value="-">-</option>
  <option value="*">*</option>
  <option value="/">/</option>
</select>
<input type="text" id="text-2">
<button>=</button>
<input type="text" id="text-3">

<script>
  document.querySelector("button").onclick=function(){
    var inpu1=document.querySelector("#text-1");
    var inpu2=document.querySelector("#text-2");
    var inpu3=document.querySelector("#text-3");
    var operate=document.querySelector("#operate");
    inpu3.value=eval(inpu1.value+operate.value+inpu2.value);
</script>
}
```

#### 通过原型链得出的结果:

```
1 所有的原型链最终都会指向Object.prototype

2 所有的函数都是由Function构造创建出来的,包括Function自己

3 Funtion 和Object是js中最核心的类型

4 Function构造函数的原型在Object对象的原型链上

    Object构造函数的原型在Function对象的原型链上
```

#### $Funtion 和Object的关系

**Object的原型  在Object对象和Function对象的原型链上**

**Function的原型  在Object对象和Function对象的原型链上**

###  9 arguments对象

```
这个对象会将传递给函数的实参封装成一个伪数组

(1)属性 length:表示实参的个数;

(2)属性 callee: 表示当前arguments对象所在函数自身;(匿名函数的递归);
```

### 10 函数的属性

```	
(1) 函数名.length //形参的个数

(2) 函数名.name//函数名

(3) 函数名.caller//,如果是全局输出null;如果在函数内部调用获取当前函数的调用者;
```

##### 函数名的扩展(在函数表达式)

```javascript
函数表达式后面的匿名函数也可以添加一个函数名,这个函数名只能在内部调用
var test=function aa(){
  aa();//自调用
}
test();//调用函数
```

### 11 递归函数

11-1   递归:函数直接或间接调用自身的过程

11-2    条件:1 函数调用自身;

​	            2 递归必须有结束条件;

11-3     化归思想:将一个问题由难化简,由繁到简

##### 11-4    通过递归获取后代元素

```javascript

递归实现获取页面所有子元素的思路:求该元素下面的子元素,通过递归调用即可
//版本1
var arr=[];//用于存放所有获取的元素
function getEle(ele){
  var eles=ele.children;//获取ele下面的直接子元素 是伪数组
  for (var i = 0; i < eles.length; i++) {
    arr.push(eles[i]);//将获取的直接子元素添加到arr中来
    getEle(eles[i]);//获取每个子元素下面的子元素
  }
}
  getEle(document.body);

//优化版本

  function getEle(ele){
    var allEle=[];//用于存放所有子元素的数组
    var eles=ele.children;
    for (var i = 0; i < eles.length; i++) {
      allEle.push(eles[i]);
      var tamp=getEle(eles[i]);
      allEle=allEle.concat(tamp);
    }
//    console.log(allEle);
    return allEle;
  }
console.log(getEle(document.body));;

```

### 12 变量作用域(变量起作用的范围)

```
1 函数作用域 : js函数会构成独立作用域
2 块级作用域 : 代码块的内部会构成独立的作用域
	(代码块:if(){} for(){} try{}catch(e){})
	定义块级作用域的变量: let num=200;
3 词法作用域(js): 变量解析根据代码的书写属性来解析的
4 动态作用域: 变量的解析是变量的执行环境进行解析的
			
```

### 13 变量/函数提升(预解析)

#####     13-1  js代码的执行

​	  1-预解析

​		js代码在执行之前会将代码中的 变量的声明和函数的声明 提升到当前作用域的顶部;

​	  2-执行js代码

#####     13-2 不能被提升的情况

​	  1 函数表达式

​	  2 Function创建的构造函数(new Function()不会被提升)

​	  3 未使用var声明的变量

#####     13-3  变量提升中的特殊情况

##### 	  	1 当函数和变量重名时,函数的优先级高,最终提升的是函数;

##### 	  	2 函数和函数重名时,后面的函数会覆盖前面的函数;	

```javascript
	函数表达式 var fn=function(){};
    			function fn(){};
    预解析时函数表达式fn会当变量名进行解析,执行代码时函数表达式fn会当函数名
```



#####     13-4 预解析是分段的

​	   预解析是分script标签的,代码的执行不分段;

#####     13-5条件式函数声明(if条件语句里面定义的函数不会被预解析)

```javascript
test();//报错
console.log(test);//undefined (if判断里的函数向当与var test=new Function();所以变量会提升)
if(true){
  function test(){
    console.log(1);
  }
}
test()//输出1

//在if里面出现同名变量和函数在谷歌中会报错,在ie中不会报错
```

### 14 作用域链

**在js中函数可以构成独立的作用域,函数的内部又可以定义函数,函数内部又可以有新的作用域,这样多次嵌套,就会构成作用域链**

### 15 变量的搜索原则

##### 	1 当要获取变量信息时,首先会在当前的作用域中查找对应变量,如果找到直接使用

​	**2 如果没有找到,会去上一级作用域中查找,如果找到直接使用**

​    	 **3 如果没有找到继续向上一级查找,以此类推**

​	 **4 一直会找到全局为止,如果没有找到就会报错**

```javascript
(function(a){
  console.log(a);//输出结果为100;
  var a=10;
})(100);
```

#### 复杂面试题:

```javascript
function Foo() {
    getName = function(){ alert(1); };
    return this;
  }
  function getName(){ alert(5); };//被alert(4)覆盖了
  Foo.getName = function() { alert(2); };
  Foo.prototype.getName = function(){ alert(3); };
  var getName = function() { alert(4); };
//  function getName(){ alert(5); };//函数提升
//  getName = function(){ alert(1); };//Foo()调用之后将getName全局变量进行赋值,覆盖了var getName=function(){alert(4);};

  Foo.getName();//   2
  getName();//   4
  Foo().getName();//window.getName();  1
  getName();//   1
  new Foo.getName();//   2
  new Foo().getName();//    3
  new new Foo().getName();//    3
```



拓展内置对象

```javascript
var arr=new Array();
function Person (){};
Person.prototype=arr
var p=new Person();
p.push(1);
```



### 16 闭包函数

**一个具有封闭的对外不公开的, 包裹结构, 或空间.**

**js中的闭包就是函数**

闭包的原理就是作用域访问原则:上级作用域无法访问下级作用域中的变量

```javascript
function foo(){
  var num=123;
 return function (a){
    num=a;
    console.log(num);
  }
}
var func=foo();
func(789);
```

闭包要解决的问题:在函数外部访问函数内部分的数据;

闭包基本模式

在外部函数内创建函数,在内部函数中,可以操作外部函数中的变量,将外部函数的返回值设置为内部函数

在外部调用外部函数,就可以接受到返回值(内部函数),使用内部函数,就可以在外部对外部函数的变量进行修改;

闭包操作的是同一个数据

js是单线程,同一时间只能做一件事

js中代码的执行分为主要任务和次要任务

js代码会先执行主要任务再开始执行次要任务

主要任务:写在js代码中的主逻辑

次要任务:定时器,事件,ajax;

   

```
//childNode获取到到的节点包含了各种类型的节点
//但是我们只需要元素节点  通过nodeType去判断当前的这个节点是不是元素
```

函数名和变量名重名,变量名会被覆盖; 

######   

**js沙箱模式:**

##### 为了保护沙箱内部数据,不受外界的影响(立即执行函数表达式[函数自调用]);

```javascript
//沙箱模式实际开发中用的不多,封装插件,封装框架会大量使用;
(1) (function(window){
  var num=100;
  window.num=num;//沙箱内部把外界需要的数据暴露给外界;
})(window);
//推荐使用,将window以实参的形式传入沙箱
//1 原则上沙箱的内外互不影响,不建议直接在沙箱内部操作沙箱外部的数据
//2 不利于代码压缩
// 代码压缩时:(1)会去除不必要的空白
//(2)会将变量名替换成
(2)(function(){
  var num=100;
  window.num=num;
})();//不推荐
```

### 17 缓存

##### 提高网站访问速度方式:

```text 
1 精灵图: 将多张小图有规律的放在一张大图上
2 代码压缩: 会将代码中不必要的空格去除,把变量名换成单个字符
3 浏览器缓存: 在请求页面返回后,将网页中的图片,js,css等静态资源缓存在本地,下次访问网页时,直接从本地缓存获取,不用请求服务器,从而减少服务器的压力, 
4 图片压缩技术: 可以使用专业的图片压缩软件,把图片的体积变小,图片的品质变化不大;
5 CDN 内容分发网络: 使用户就近取得所需内容,解决Internet网络拥挤的状况,提高用户访问网站的响应速度;
```

**缓存**: 把数据临时存储起来,以提高响应速度;

缓存分类:

1-浏览器的缓存;

2-CDN内容分发网络;

3-硬件缓存 内存;

4-数据库缓存 ;

​	4-1关系型:mySql   orcale 把数据存在硬盘上;

​	4-2非关系型 : redies mongoDB 把数据存在内存中;

缓存要存储多个数据:

​	1 数组

​		优点:有索引,有顺序,存储多个数据

​		缺点:数组的索引是没有意义的不方便取值

​	2 对象

​		优点:对象的键是有意义的,方便取值

​		缺点:没索引,没顺序;

### 18 函数的四种调用模式

```javascript
1 函数调用模式(在不同的调用模式下,this的指向是不同的;在同一调用模式下,this的指向是相同的)
	语法  函数名();
	this==> window;
	function test(){};
	test();
2 方法调用模式(在对象里叫方法)
	语法 对象名.方法名
	this==> 当前对象;(obj)
	var obj={
		say:function(){}
	}
	obj.say();
3 构造函数调用模式
	语法 new 构造函数名();
	this==> new新创建的对象
	function Dog(){
      this.name="啸天";
      this.owner="lala";
	}
	var d=new Dog();
//前三中函数中的this不能被赋值,不能被改变
4 上下文调用模式(可以改变函数中this的指向)
	4-1 函数名.call(对象(this的指向),参数1,参数2....);(这个方法是Function.prototype的原型中);
    	语法说明:
		对象:用于改变this指向的对象
   		参数1:对应传递给前面的函数作为第一个参数
		参数2:对应传递给前面的函数作为第二个参数
        参数n:对应传递给前面的函数作为第n个参数
    4-2函数名.apply(对象(this的指向),[参数1,参数2....])
      语法说明:
		对象:用于改变this指向的对象
        伪数组参数:
   		参数1:伪数组中第一个元素 对应传递给前面的函数作为第一个参数
		参数2: 伪数组中第二个元素 对应传递给前面的函数作为第二个参数
        参数n: 伪数组中第n个元素 对应传递给前面的函数作为第n个参数

    function test(a,b,c){
       this.a=a;
       this.b=b;
    }
	var obj={};
	test.call(obj,100,200,300); //this指向obj
  或test.apply(obj,[100,200,300]);//this指向obj
	
	//call和apply的注意点
	(1) 特殊情况:对象是 
    	数字//转化为Number  number-->Number
   		字符串//转化为String  string-->String
        true // boolean-->Boolean
        //如果对象是值类型数据,会将数值类型转化成对应的引用类型的数据,this指向该引用类型的数据
        null 和 undefined //this均指向window;
    	
```

### 19 创建对象的模式

```javascript
1 工厂模式 this==>window
function factory(name,age,sex){
  var obj=new Object();
  obj.name=name;
  obj.age=age;
  obj.sex=sex;
  return obj;
}
var factory=factory('as',11,'nan');
2 构造函数模式 this==>new 新创建的对象
function Person(){
  this.name='zs';
  this.age='12';
}
var obj1=new Person();
3 寄生虫模式 this=>new 新创建的对象
function Dog(name,age,sex){
  var obj={};
  obj.name='zs';
  obj.age="12";
  return obj
}
var d=new Dog();
```

### 20 js中垃圾回收

```
当一个数据的引用数量为0就会触发垃圾回收机制
```



#### Object.defineProperty()

##### 

```javascript
语法 Object.defineProperty(obj,prop,descriptor)
参数
```

### 21 forEach和map 遍历的方法

```javascript
var data=[1,2,3,4];
data.forEach(function(ele,index,data){
  //要执行的代码
});
data.map(function(ele,index,data){
  //将变化的数据放到一个新数组中返回
})
```

*24、**以下代码产生什么输出？                                
var length = 10;
   function fn() {
​      console.log(this.length);
}
var obj = {
​    length: 5,
​    method: function (f) {
​        f();
​        arguments[0]();
​        arguments[0].call(this);
}
}
obj.method(fn);*



*、**以下代码产生什么样的输出？              
function fn(a) {
​      console.log(a);
​      var a = 2;
​      console.log(a);
}
fn();
fn(200);*



*21、**以下代码产生什么输出？                               
var x = 1, y = z = 0;
function add(n) {
​    return n = n + 1;
}
y = add(x);
z = add(x);
function add(n) {
​    return n = n + 3;
}
console.log(‘x’+ x + ‘y’+ y + ‘z’+ z);*

