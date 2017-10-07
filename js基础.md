

#1.javascript介绍

> JavaScript（缩写：JS）是一门脚本语言,不需要编译,直接解释执行(同时也是一门弱类型语言).

JavaScript是非常通用的.可以实现页面的动态效果(轮播图)和服务器交互(ajax)。随着你学习的深入，你可以创建 游戏、2d动画、3d图像、数据库驱动的综合应用程序,以及更多!



它是Mozilla项目联合创始人的Brendan Eich发明的。

​	 ![js-farther](Brendan_Eich.jpg)

> 布兰登·艾奇（Brendan Eich，1961年～），1995年在网景公司，发明的JavaScript。一开始JavaScript叫做LiveScript，但是由于当时Java这个语言特别火，所以为了傍大牌，就改名为JavaScript.同时期还有其他的网页语言，比如VBScript、JScript等等，但是后来都被JavaScript打败，所以现在的浏览器中，只运行一种脚本语言就是JavaScript。
>
> #### js的组成:
>
> 1 ECMAScript  (制定了js的组成语法规范 是标准  通用:es3;最新:es6;  会有兼容问题  TypeScrip完全兼容es6的语法);
>
> 2 DOM:提供一套操作页面元素的API
>
> 3 BOM:提供了一套操作浏览器相关的API
>
> ​	3-1window 
>
> ​		(1)open();打开新的窗口
>
> ​		(2)close();关闭当前窗口
>
> ​		(3)onload加载
>
> ​	3-2location
>
> ​		(1)href:设置或获取当前页面的地址
>
> ​		(2)reload();刷新页面
>
> ​		(3)search;以?号开始的地方获取
>
> ​	3-3screen
>
> ​		(1)width
>
> ​		(2)height
>
> ​	3-4navigator
>
> ​		(1)userAgent :获取系统和浏览器的版本信息

### 1.1. javascript在浏览器和node环境下运行

>起初,javascript只能在浏览器当中运行,后来有了node.js之后,也可以在node环境下运行开发后台程序.

### 1.2. javascript的应用编年史

- 2003年之前，JavaScript被认为“牛皮鲜”，用来制作页面上的广告，弹窗、漂浮的广告(页面上的动态的特效)。什么东西让人烦，什么东西就是JavaScript开发的。所以浏览器就推出了屏蔽javascript的功能。

- 2004年JavaScript命运开始改变了，那一年谷歌公司，开始带头使用Ajax技术了，Ajax技术就是JavaScript的一个应用,实现了与后台服务器的交互。自此,javascript逐渐被广泛使用

- 2007年乔布斯发布了iPhone，这一年开始，进入移动端时代,手机移动端由原来的原生开发(java,object-c),发展为混合开发(移动web),前端技术应用更加广泛.

  - 2011年，Node.js诞生，使JavaScript能够开发服务器程序了。




- 现在html5标准被广泛使用,用canvas配合javascript既可以网页开发游戏,也可以运用react等框架,开发出原生的app来(移动app)

  ​

  ### 1.3. javaScript和ECMAScript（ES）的关系

ECMAScript是一种由Ecma国际前身为欧洲计算机制造商协会,英文名称是European Computer ManufacturersAssociation，制定的标准。

简单来说ECMAScript不是一门语言，而是一个标准。符合这个标准的比较常见的有：JavaScript、Action Script（Flash中用的语言）。

ECMAScript在2015年6月，发布了ECMAScript 6版本，es6增加了很多新的关键字.从es6中我们可以发现,未来js的发展也在往强类型语言的方向发展.

**总之:**

javascript的书写方式按照ECMAScript的标准



 # 2.javascript的书写位置

### 2.1.嵌入式

```html
<script type="text/javascript">
  	...
</script>
<!-- 1.type属性 可写可不写
	 2.script 标签可写在html页面中的任意位置
-->
```

### 2.2.外链式

```html
<head>
   <meta charset="utf-8">
   <script src="javascript文件的url"></script>
</head>

<!--script标签属性:
async	async	规定异步执行脚本（仅适用于外部脚本）。
charset	charset	申明外部脚本文件中使用的字符编码。
defer	defer	规定是否对脚本执行进行延迟，直到页面加载为止。
src	URL	规定外部脚本文件的 URL。
-->
```



# 3.javascript的执行顺序和注释

- js的执行顺序是从上到下,从左到右.依次执行代码,如遇到错误则停止执行

- js中的注释

  ```javascript
  // 单行注释
  /* 多行注释 */ 
  ```

# 4.javascript初体验

>输入输出的语句

```javascript
alert("hello world");//浏览器会弹出一个小对话窗口,括号里的内容会显示在小框口中

console.log(123456);  // 括号里的内容会显示在浏览器的控制台里

prompt("你好,你叫什么名字呀?")
/*浏览器会弹出一个窗口,括号里的内容会显示在小窗口中,并且这个小框口有一个输入框,供用户使用*/

document.write() //往网页中写入内容

confirm("你确定吗?"); //确认框
/*
注意:
    括号里面的内容,在javascript中叫做字面量或者直接量
*/
```



# 5.变量

> 变量就是存储数据的容器,因为可以任意改变存在里面的值,所以称之为**变量**
>
> 在运算时,可以把变量当做他存储的那个值.

### 5.1 变量的申明

```javascript

/*var 关键字是javascript一直使用的关键字,目前也被广泛使用  标识符*/
var a; 
console.log(a)   // 变量申明后 ,默认值都是undefined;

//现在ec6新的标准又增加了一个let的关键字,用于变量的申明,用法与var类似.(后面有时间,会给大家介绍)

```

### 5.2 给变量赋值

```javascript
//最基本的赋值;
var a; 
a = 123;

//这种方式是前者的连写;
var b = 123;

//这种方式是连续声明方式
var name="Gates", age=56, job="CEO";

//连续赋值方式,这种方式是有问题的.不建议使用
var a = b = c = 1;

//也可以计算完成后在赋值
var c = 123+456;
console.log(c); //579;
```

### 5.3 给变量命名(标识符)

- 变量名只能由英文字母，数字，下划线以及$符号组成，并且数字不能放在名称开头。（如果名称带有下划线，那么后面就算直接跟数字也是可以的）.
- 变量的命名不能使用javascript中的关键字和保留字。

关键字：已经被javascript内部使用过的。

```javascript
break   do  instanceof  typeof

case    else    new  var

catch   finally  return   void

continue    for  switch  while

debugger*   function    this    with

default if  throw   delete

in  try
```

保留字：还没有被javascript内部使用，但是可能有一天会被使用到。

```javascript
abstract    enum    int  short

boolean  export  interface   static

byte    extends  long    super

char    final   native  synchronized

class   float   package throws

const   goto    private transient

debugger    implements  protected   volatile

double  import  public
```

### 5.4 变量的类型

给变量赋值为什么类型,则变量就是什么类型

### 5.5 变量之间的相互赋值以及变量可以和直接量一起输出

```javascript
//变量之间可以相互赋值
var a = 123;
var b = a;

//变量可以和直接量一起输出
var a = 123;
console.log(a + "abc");
```

### 5.6 变量提升

```javascript
var a ;
a = 1 ;
console.log(a)  //1
console.log(b)  //undefined
b = 2;
var b;         

/*实际上,js解析器,在运行代码之前,会扫描代码(预解析),当看到var时,会默认把这些变量先声明出来,你可以理解为浏览器默认把声明的变量的代码写在了赋值代码的前方.所以叫做变量提升*/

/*
注意:
不用var 声明的变量是不提升的
*/

console.log(c)
c = 3            // Uncaught ReferenceError: d is not defined
```

- 变量存储基本数据类型时,存储的就是这个值


- 变量存储引用数据类型时,存储的是这个引用数据内存中的地址值





# 6.数据类型

>前六种数据类型是：Undefined、Null、布尔值（Boolean）、字符串（String）、数值（Number）、对象（Object）。ECMAScript6(es6)引入了一种新的原始数据类型Symbol，表示独一无二的值。它是JavaScript语言的第七种数据类型，

```javascript
我们在学习和使用当中,为了方便,又将这些数据类型分为了两大类:基本数据类型(原始数据类型,简单数据类型)和引用数据类型(复杂数据类型)

/*基本数据类型:

 	1.number  数值  整数,小数都叫数值 
				还有一个特殊的 NaN (表示不是一个数值),任何数据和NaN运算返回的都是NaN
				
	2.string  字符串  用引号包括起来的就叫做字符串

	3.boolean 布尔值  只有 true 和 false  代表 是 与 非

	4.undefined 比较特殊,代表未定义
	5.null(变量的结果不会默认为null一定是手动赋值的结果;将变量赋值为null,有利于js内存进行垃圾回收)
null==undefind ==> true
引用类型(object):
	1.array  数组 
	2.function 函数 
	3.object
	4.包装类型 Number String Boolean
	5.Data
	6.Math
	7.RegExp(正则)
	8.Symbol 是es6标准新增的,表示独一无二并且不可修改(扩展内容)
*/
```



### 6.1 如何判断数据类型

###### typeof 变量  返回的是string 类型的数据

注意:typeof可以准确的获取基本类型数据的类型,如果是复合类型返回的结果是object,函数返回的是function

变量名.constructor.name  可以准确获取复合类型的数据类型

```javascript
两种书写方式:

console.log(typeof 111);
console.log(typeof "123");
console.log(typeof true);
console.log(typeof undefined);
console.log(typeof null);

console.log(typeof("你好"));
console.log(typeof(333));
console.log(typeof(NaN));
```

### 6.2 数据类型之间的转换

#### 6.2.1 强制类型转换


- Boolean(value) - 把给定的值转换成 Boolean 型；

  ​

  ```javascript
  当要转换的值是至少有一个字符的字符串、非 0 数字或对象时，Boolean() 函数将返回 true。如果该值是空字符串、数字 0、undefined 或 null，它将返回 false。

  Boolean("");		//false - 空字符串
  Boolean("hello");		//true - 非空字符串
  Boolean(50);		//true - 非零数字
  Boolean(null);		//false - null
  Boolean(0);		//false - 零
  Boolean(new object());	//true - 对象
  Boolean(NaN)      //false
  Boolean(Symbol("foo"))  //true
  ```

  ​

- Number(value) - 把给定的值转换成数字（可以是整数或浮点数）；

  ```javascript
  Number(false)	0
  Number(true)	1
  Number(undefined)	NaN
  Number(null)	0
  Number("1.2")	1.2
  Number("12")	12
  Number("1.2.3")	NaN
  Number("123ab") NaN
  Number(new object())	NaN
  Number(50)	50
  Number(Symbol())  // Uncaught TypeError: Cannot convert a Symbol value to a number
  ```

  ​

- String(value) - 把给定的值转换成字符串；

  ```javascript
  * 它可把任何值转换成字符串

  String(null);	//"null"
  String(undefined)  //"undefined"
  String(1) //"1"
  String(1.2)  //"1.2"
  String(true)  //"true"
  String(Symbol("foo")) //"Symbol(foo)"
  ```

#### 6.2.2 其他显式的转换方式

- 其他类型转换成字符串: toString()方法

  ```javascript
  true.toString();     //"true"
  false.toString(); 	//"false"

  var a = 123;
  a.toString();       // "123"
  123.toString();     // Uncaught SyntaxError: Invalid or unexpected token ? 因为js解析引擎把456后面的点						当做了小数点

  4577.8.toString()   //"4577.8"
  "4577.8"
  var a = 456.7;
  a.toString();      // "456.7"

  undefined.toString()  //Uncaught TypeError: Cannot read property 'toString' of undefined
   
  null.toString()       //Uncaught TypeError: Cannot read property 'toString' of null
     
  Symbol().toString()  //"function Symbol() { [native code] }"

  var a  = 10;
  a.toString(2)  //"1010"  转换成2进制
  "1010"
  a.toString(8)  //"12"    转换成8进制转换

  a.toString(16)  //"a"    转换成16进制转换
   
  ```

  ​

- 转换成数值: parseInt(),parseFloat()

  > 前者把值转换成整数，后者把值转换成浮点数(小数)。只有对 String 类型调用这些方法，它们才能正确运行；对其他类型返回的都是 NaN。

  ```javascript
   parseInt("12345red");	//返回 12345
   parseInt("red12345");  //返回 NaN
   parseInt("123red45");  //返回 123
   parseInt("0xA");	//返回 10  0xA表示十六进制的10 0xB表示11 ...
   parseInt("56.9");	//返回 56
   parseInt("red");	//返回 NaN

   parseFloat("12345red");	//返回 12345
   parseFloat("0xA");	//返回 NaN   浮点数中不存在16进制
   parseFloat("11.2");	//返回 11.2
   parseFloat("11.22.33");	//返回 11.22
   parseFloat("0102");	//返回 102
   parseFloat("red");	//返回 NaN

   
  ```

  ​


#### 6.2.3 隐式类型转换

遇到以下三种情况时，JavaScript会自动转换数据类型，即转换是自动完成的，对用户不可见。

```javascript
// 1. 不同类型的数据互相运算
123 + 'abc'                 // "123abc"    与字符串相加时,其他都转换为字符串,然后拼接
123 - 'abc'                 // NaN   字符串做减法(或乘法,除法)时需要将'abc'转换为数值,但是'abc'转数值会转成NaN   
123 + true                     // 124    boolean值计算时,true转换为1 ,false 转换为0
123 - false                    // 123    

// 2. 对非布尔值类型的数据求布尔值

if ('abc') {                    // "hello"  在语句中需要将"hello"转换成boolean值, 有内容的字符串会转换成true
  console.log('hello')
} 
 
// 3. 对非数值类型的数据使用一元运算符（即“+”和“-”）

+ {foo: 'bar'} // NaN
- [1, 2, 3] // NaN 

+true
```

自动转换的规则是这样的：预期什么类型的值，就调用该类型的转换函数。比如，某个位置预期为字符串，就调用String()函数进行转换。如果该位置即可以是字符串，也可能是数值，那么默认转为数值。

由于自动转换具有不确定性，而且不易除错，建议在预期为布尔值、数值、字符串的地方，全部使用Boolean、Number和String函数进行显式转换。

##### 6.2.3.1 自动转换为布尔值

- 当JavaScript遇到预期为布尔值的地方（比如`if`语句的条件部分），就会将非布尔值的参数自动转换为布尔值。系统内部会自动调用Boolean()函数。

```因此除了以下六个值，其他都是自动转为true。

```

```javascript
undefined

null

-0

0或+0

NaN

''（空字符串）

注意: 这里有个特殊情况
NaN != NaN  //true
```

- 当使用 ! 或者 !! 运算符的时候,会默认转换为boolean类型

```javascript
!1   //false

!!1   //true
```




##### 6.2.3.2  自动转换为字符串

当JavaScript遇到预期为字符串的地方，就会将非字符串的数据自动转为字符串。系统内部会自动调用String()函数。

字符串的自动转换，主要发生在加法运算时。当一个值为字符串，另一个值为非字符串，则后者转为字符串。

```javascript
'5' + 1  // '51'
'5' + true  // "5true"
'5' + false  // "5false"
'5' + {}  // "5[object Object]"   
'5' + {x:1}   // "5[object Object]"
'5' + []  // "5"
'5' + [1,2,3,4]  //"51,2,3,4"
'5' + function (){}  // "5function (){}"
'5' + undefined  // "5undefined"
'5' + null  // "5null"

```

##### 6.2.3.3 自动转换为数值

当JavaScript遇到预期为数值的地方，就会将参数值自动转换为数值。系统内部会自动调用`Number`函数。

除了加法运算符有可能把运算子转为字符串，其他运算符都会把运算子自动转成数值。

```javascript
'5' - '2' // 3
'5' * '2' // 10
true - 1  // 0
false - 1 // -1
'1' - 1   // 0
'5' * []    // 0
false / '5' // 0
'abc' - 1   // NaN
undefined-1 //NaN
null - 1 //-1
'5' % '2'
```

上面代码中，运算符两侧的运算子，都被转成了数值。

一元运算符也会把运算子转成数值。

```javascript
+'abc' // NaN
-'abc' // NaN
+true // 1
-false // 0
```

​	

# 7.运算符:

### 7.1.一元运算符:

> 一次操作只有一个操作数

```javascript
++, --    递增,递减
delete    用于删除对象的属性
void   	  用于丢弃表达式的返回值
typeof    判断数据类型
+    一元加运算符将其操作数转换为数字类型。
-    一元否定运算符将其操作数转换为Number类型，然后将其否定。
!    逻辑非运算符
!!   负负得正
```

### 7.2.算数运算符:

> 算术运算符将数值（文字或变量）作为操作数，并返回单个数值。

```
+ 加法运算符。 
- 减法运算符。 
/ 除法运算符。 
* 乘法运算符。 
％ 取余运算符。 
```

### 7.3.关系运算符(比较运算符)

> 关系运算符 比较其操作数，并根据比较是否为真返回一个布尔值。

```
in     in操作符确定对象是否具有给定属性。 
instanceof     instanceof运算符确定对象是否是另一个对象的实例。 
<   小于运算符。 
>   大于运算符。 
<=  小于或等于运算符。 
>=  大于或等于运算符。 
== 平等运算符。
!= 不等式运算符。
=== 全等运算符。
!== 不全等运算符
```

#### 7.3.1相等运算符

> == 比较值是否相等,内部会进行强制类型转换  === 比较值之前,会比较数据类型是否相等

| x                   | y                   | `==`    | `===`   |
| ------------------- | ------------------- | ------- | ------- |
| `undefined`         | `undefined`         | `true`  | `true`  |
| `null`              | `null`              | `true`  | `true`  |
| `true`              | `true`              | `true`  | `true`  |
| `false`             | `false`             | `true`  | `true`  |
| `"foo"`             | `"foo"`             | `true`  | `true`  |
| `Symbol()`          | `Symbol()`          | `false` | `false` |
| `0`                 | `0`                 | `true`  | `true`  |
| `+0`                | `-0`                | `true`  | `true`  |
| `0`                 | `false`             | `true`  | `false` |
| `""`                | `false`             | `true`  | `false` |
| `""`                | ``0``               | true    | false   |
| `"0"`               | `0`                 | `true`  | `false` |
| `"17"`              | `17`                | `true`  | `false` |
| `[1,2]`             | `"1,2"`             | `true`  | `false` |
| `new String("foo")` | `"foo"`             | `true`  | `false` |
| `null`              | `undefined`         | `true`  | `false` |
| `null`              | `false`             | `false` | `false` |
| `undefined`         | `false`             | `false` | `false` |
| `{ foo: "bar" }`    | `{ foo: "bar" }`    | `false` | `false` |
| `new String("foo")` | `new String("foo")` | `false` | `false` |
| `0`                 | `null`              | `false` | `false` |
| `0`                 | `NaN`               | `false` | `false` |
| `"foo"`             | `NaN`               | `false` | `false` |
| `NaN`               | `NaN`               | `false` | `false` |

### 7.4.赋值运算符:  

> 赋值运算符根据其右操作数的值为其左操作数赋值。

```
  =  直接赋值运算符  
  *= 乘法赋值运算符  
  /= 除法赋值运算符  
  ％= 取余赋值运算符   
  += 加法赋值运算符  
  -= 减法赋值运算符
```

### 7.5.逻辑运算符:

> 逻辑运算符通常与布尔（逻辑）值一起使用，返回一个布尔值。

```javascript
＆ 按位与运算。 底层会进行二进制运算(不建议使用) 
| 按位或运算符。 底层会进行二进制运算(不建议使用)

! 非运算符 
!! 取反两次运算符
&& 双与运算符(所有操作数都是都为true时,返回最后一个操作数.如果其中有false则,返回第一个false)

|| 双或运算符(只要有一个true则返回这个true,如果没有则返回最后一个false)
```

### 7.6运算符的优先级

```javascript
// () > 逻辑运算符 > 算数运算符 >   比较运算符 > 赋值运算符 
var resulte =  1 + 2 * 8 / 4 ;    //5
var resulte1 =  (1 + 2) * (8 / 4) ;   //6
var resulte2 = !true + !false >= 1;   //true
var resulte3 = !true + (!false >= 1);   //1
var resulte4 = !(true + false)      //false
```

### 7.7. 条件(三元)运算符

> （条件表达式？ifTrue：ifFalse） 条件运算符根据条件的逻辑值返回两个值之一。

### 7.8. 逗号运算符

> 逗号运算符允许在单个语句中评估多个表达式，并返回最后一个表达式的结果。



# 8.语句

### 8.1 条件判断语句(if..else)

```javascript
 
if(表达式){
  //如果表达式结果为true ,则执行此处的代码.否则不执行
}
```

```javascript
if(表达式0){
  //如果表达式0结果为true ,则执行此处的代码
}else{
   //如果表达式0结果为false ,则执行此处的代码
}
```

```javascript
if(表达式1){
 //如果表达式1结果为true ,则执行此处的代码
}else if(表达式2){
  //如果表达式1结果为false ,则判断表达式2是否为true
}
```

```javascript
//示例  判断输出结果

  if(true){
    console.log(1)
  }else if(true){
    console.log(2)
  }else{
    console.log(3)
  }  
 // 1
```

### 8.2 条件判断语句(switch)

```javascript
switch (expression) {
  case value1:
    // 当 expression 的结果与 value1 匹配时，从此处开始执行
    [break;]
  case value2:
    // 当 expression 的结果与 value2 匹配时，从此处开始执行
    [break;]
  case valueN:
    // 当 expression 的结果与 valueN 匹配时，从此处开始执行
    [break;]
  default:
    // 如果 expression 与上面的 value 值都不匹配时，执行此处的语句
    [break;]
}
```

**注意:**

如果不加break,则会造成case穿透,如以下示例代码

```javascript
switch (1) {
  case 1:
    
    console.log(1)
   
  case 2:
    
    console.log(2)
   
  case 1:
  
     console.log("另一个1")
   
  default:
  
     console.log("都不符合")
   
}
```

### 8.3 迭代器(for)

```javascript
for (表达式用于初始化计数器; 表达式用于判断是否下一次循环; 最后执行的表达式) {
   console.log(i);
 
}
```

```javascript
for (var i = 0; i < 9; i++) {
   console.log(i);
 
}
```

### 8.4迭代器(while)

```javascript
while (表达式) {
//如果表达式,为true则不停的执行此处代码
}
```

```javascript
var n = 0;
var x = 0;

while (n < 3) {
  n++;
  x += n;
}
```

### 8.5 迭代器(do...while)

>跟while的区别是,先执行一次大括号里的代码,然后再判断while表达式,所以不论如何,代码都是执行一次

```javascript
do {
   i += 1;
   console.log(i);
} while (i < 5);
```

### 8.6 迭代器(for...in)

>**for...in **语句以任意顺序遍历一个对象的可枚举属性。对于每个不同的属性，语句都会被执行。

```javascript
var obj = {a:1, b:2, c:3};
    
for (var prop in obj) {
  console.log("obj." + prop + " = " + obj[prop]);
}
// 输出:
// "obj.a = 1"
// "obj.b = 2"
// "obj.c = 3"
```

### 8.7 控制流程(break , continue)

>[`break`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/break)
>
>终止当前的循环，switch中,跳出switch.
>
>[`continue`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/continue)
>
>终止执行当前循环的语句，直接执行下一个迭代循环。

```javascript
for (var i = 0; i < 9; i++) {
  console.log(i)
   if(i == 8){
     break;
   }else if(i == 5){
     continue;
   }
  console.log(i)
}
```



# 9.数组

> 数组也是对象,数组是为了存储数据

### 9.1创建数组

- 常规方式:

  ```javascript
  var myCars=new Array(); 
  myCars[0]="Saab";       
  myCars[1]="Volvo";
  myCars[2]="BMW";
  ```

  ​

- 简洁方式:

```javascript
var myCars=new Array("Saab","Volvo","BMW");
```

- 字面量(最常用):

```javascript
var myCars=["Saab","Volvo","BMW"];
```

### 9.2 访问数组和给数组赋值

```javascript
var arr = ["老王","老宋","老司机"];
console.log(arr[0]);
console.log(arr[1]);
console.log(arr[2]);

arr[0] = "老司机没有车"
arr[4] = "老司机会开车"
console.log(arr);
```

### 9.3 二维数组和多维数组

```javascript
var arr2 = [1,true,[3,4,5]]  //二维数组
var arrMore = ["多维数组",false,[3,4,[1,2,0]]] //多维数组

console.log(arr2[2][2]);
console.log(arrMore[2][2][2]);
```



# 10.函数

>函数也是对象,函数的作用是为了代码的复用

### 10.1 函数的三要素

- 函数名   一个函数的名称
- 参数       传给一个函数的值
  - 写在函数上的叫做形式参数
  - 形式参数,可写,可不写.(相当于在函数中申明了变量)
- 返回值    函数执行完毕返回的值 ; 
  - 如果不写return 则默认返回undefined
  - 如果写了return 但return后面没有值,也返回undefined
  - 如果写了return,后面跟着值,则返回这个值
  - 如果return后面写表达式,则先计算表达式,然后将表达式的结果返回
  - 一个函数中,return后面的代码不执行(return跳出函数)

**使用 function 关键字定义一个函数**

```javascript
function 函数名(参数1,参数2,参数3){
  return 要返回的值;
}
```

```javascript
function add(x,y){
  return x+y;
}
```

### 10.2 函数声明 和 函数表达式

```javascript
//声明的函数,函数会提升,当函数名和变量名重复,函数会覆盖变量
function a(){
  
}

//函数表达式 不会提升
var a = function(){
  
}
```

### 10.3 匿名函数

>没有名字的函数叫做匿名函数.主要用于回调或自调用函数,回调处不需要定义函数名.
>
>看一下代码示例,我们可以发现,函数的三要素:函数名,参数,返回值都可以不写.

```javascript
function(){
  
}
```

### 10.4  函数的调用

>函数声明,函数里面的代码是不会执行的.只有调用函数时,
>
>函数里面的代码才执行,那么如何调用呢?

```javascript
function add(x,y){   //定义函数时,函数中写的x,y叫做形式参数
  console.log(x+y);
}
//调用函数:函数名();
add(1,2);           //调用函数时,括号中写的数据叫做实际参数

/*
注意:
	调用函数时,如果不写实际参数,默认传进去的是undefined
*/
```

```javascript
var a = 1;
var b = 2;
function add(x,y){   
  console.log(x+y);
}
add(a,b);   
```



### 10.5 自调用函数

```javascript
var i = 10; 
(function (a) {
	
   console.log(a)
       
 })(i);

/*自调用函数时,后面这个括号用于传递实参*/
```



# 11.作用域

>js中,一个函数拥有一个自己的作用域,
>
>我们要知道我们的js代码会加载到计算机内存中运行

### 11.1  全局作用域

> 全局作用域就相当于是整个js代码占用的那块内存空间


### 11.2  局部作用域

>局部作用域就相当于是某个函数在js代码占用的内存空间中的一个小部分



```javascript
var a = 1;  //在全局作用域中
function demo(){
  var a = 2;  //在局部作用域中
  console.log(a); 
}
demo();
console.log(a);
```

### 11.3 一个特殊情况

>在局部作用域当中给一个变量赋值,如果该变量没有用var申明的话

```javascript
var a = 1;
function one(){
  var a =2;
  function two(){
    a = 3;
    console.log(a)
  }
  two();
  console.log(a)
}
one();
console.log(a);

//如果父级作用域中有用var申明的同名的变量,则覆盖父级的同名变量,如果父级中没有,则相当于创建了一个全局变量
```



# 12.对象

>对象就是一个包含属性和方法的实体
>
>对象的动态特性:对象在创建完成后,可以随时给对象添加成员(属性和方法)
>
>语法:对象名.属性名=值;
>
>​	 对象名[属性名]=值

### 12.1 对象的创建方式

#### 12.1.1 使用Object创建一个对象 

```javascript
var myCar = new Object();
myCar.make = "Ford";
myCar.model = "Mustang";
myCar.year = 1969;
myCar.run = function(){
  console.log("漂移")
}
```

#### 12.1.2 构造函数法

```javascript
function GF(name,age){
    this.name = name;
    this.age = age;
    this.sayWhat = function(){
       console.log(this.name+"说:我喜欢的是邻居老王")
    }
}
var gf1 = new Gf("vivian","f");
var gf2 = new Gf("vivian2","f");
```

#### 12.1.3 字面量法

```javascript
var house = {
  type:"别墅",
  area:"60平米",
  feature:"门口有地铁"
}
```

### 12.2 访问和修改对象的属性以及方法

#### 12.2.1 点语法

```javascript
var person = {
  name:"老王",
  type:"同桌",
  feature:"多情"
}

console.log(person.name);
person.name = "老宋";
```



#### 12.2.2 方括号标记法

```javascript
var animal = {
  type:"dog",
  name:"小宋",
  feature:"能吃"
}
console.log(person["name"]);//注意方括号中属性要写成字符串形式的
person["feture"] = "胖";
```



## 基本包装类型

> **简单数据类型是没有方法的**。为了方便操作基本数据类型，JavaScript还提供了三个特殊的引用类型：String/Number/Boolean。

基本包装类型：把基本类型包装成复杂类型。

```javascript
var str = “abc”;
var result = str.indexOf(“a”);
//内部发生了三件事情
//1. 把简单类型转换成复杂类型：var s = new String(str);
//2. 调用包装类型的indexOf方法：var result = s.indexOf(“a”);
//3. 销毁刚刚创建的复杂类型（过河拆桥、卸磨杀驴）
```



# 13.内置对象(全局对象)

> JS内置对象就是指Javascript自带的一些对象，供开发者使用，这些对象提供了一些常用的api(application interface)。
>
> 常见的内置对象有Math、String、Array、Date等

## Math对象

> Math对象中封装很多与数学相关的属性和方法。

- 属性PI

  ```javascript
  Math.PI  //圆周率，一个圆的周长和直径之比，约等于 3.14159.
  ```

- 最大值/最小值

  ```javascript
  Math.max(x,[y,[x[,...]]]);//返回0个到多个数值中最大值.
  Math.min(x,[y,[x[,...]]]); //返回0个到多个数值中的最小值
  ```

- 取整

  ```javascript
  Math.ceil(x);// 返回x的向上取整的值   天花板
  Math.floor(x);//返回x向下取整的值     地板
  Math.round(x);//返回x四舍五入后的整数值 
  Math.trunc(x); //返回x的整数部分,去掉小数
  ```

- 随机数

  ```javascript
  Math.random();//返回一个0~1之间的随机数，包括0,不包括1
  //练习
  //返回1-100的随机数
  //Math.floor(Math.random()*100)+1
  ```

- 绝对值

  ```javascript
  Math.abs(x);//返回x的绝对值.
  ```

- 次幂

  ```javascript
  Math.pow(num, power);//求num的power次方
  ```

- 平方根

  ```javascript
  Math.sqrt(x) //返回x的平方根
  ```




## Array对象

> 数组对象在javascript中非常的常用

- 数组判断

  ```javascript
  //语法：Array.isArray(obj)//作用：用来判断一个对象是否是一个数组
  var a = 100;
  var b = true;
  var c = [1,2,3,4,5,6];
  console.log(Array.isArray(a));  //false
  console.log(Array.isArray(b));   //false
  console.log(Array.isArray(c));   //true
  ```


- 数组转换

  ```javascript
  //语法：array.join() //作用：将数组的值拼接成字符串
  var arr = [1,2,3,4,5];
  arr.join();   //不传参数，默认按【,】进行拼接
  arr.join("-");  //参数是字符串类型 按【-】进行拼接
  ```

- 数组的增删操作

  ```javascript
  array.push(value,[value[,...]]);//将一个或多个元素添加到数组的结尾，并返回新的长度。

  array.pop();//从数组中删除最后一个元素，并返回该元素的值,改变了数组的长度

  array.unshift(value,[value[,...]]);//将一个或多个元素添加到数组的开头，并返回新的长度。

  array.shift();//从数组中删除第一个元素，并返回该元素的值,改变了数组的长度
  //练习1
  var arr = ["曹操"];
  //添加数据后变成：["司马懿","曹丕","杨修","曹植","曹操"]
  //删除数据后变成：["司马懿","曹丕"]
  //练习2
  var arr = ["司马懿","曹丕","杨修","曹植","曹操"]
  //把数组的最后一个元素变成数组的第0个元素
  //把数组的第0个元素变成数组的最后一个元素
  ```

- 数组的翻转与排序

  ```javascript
  array.reverse();//翻转数组,返回翻转过的数组
  array.sort();//默认元素会按照转换为的字符串的诸个字符的Unicode位点进行排序
  //如果是数字,10 小于 2 ,比较第一位
  var arr = [1,3,10,2,4,40,5]
  arr.sort()//[1, 10, 2, 3, 4, 40, 5]

  //sort方法可以传递一个函数作为参数，这个参数用来控制数组如何进行排序
    var arr = ["ba","bb","a"];
    //arr = [1,2,10,4,40,5];

    arr.sort(function(a,b){
      
        if(a>b){ //a , b 代表数组中每一个值

          return 1; //如果a>b 成立,返回1则按照正序排列,返回-1按照倒序

        }else{

          return -1;  //如果a<b 成立,返回-1 则按照倒序排列,返回1按照正序
        }   
    })

  /*注意:
    如果 compareFunction(a, b) 小于 0 ，那么 a 会被排列到 b 之前；
    如果 compareFunction(a, b) 等于 0 ， a 和 b 的相对位置不变。备注： ECMAScript 标准并不保证这一行为，而且   也不是所有浏览器都会遵守（例如 Mozilla 在 2003 年之前的版本;
    如果 compareFunction(a, b) 大于 0 ， b 会被排列到 a 之前。
   
    */
    
     //练习：
    //将[3, 6, 1, 5, 10, 2,11]从小到大排列
    //将字符串数组按照字符长度从小到大排列
    //将学生数组按照年龄从小到大排列(如何将对象排序)
  ```



- 数组的拼接与截取

  ```javascript
   //concat：数组合并，不会影响原来的数组，会返回一个新数组。
  var arr = [1,2,3]
  var arr1 = ["a","b","c"]
  var newArray = arr.concat(arr1);//[1,2,3,"a","b","c"];

  //slice:复制数组的一部分到一个新数组，并返回这个新数组 
  //原来的数组不受影响，包含头，不包含尾 
  var newArray = array.slice(begin, end);

  var arr = [1,2,3,4,5];
  arr.slice(0,3) //[1,2,3]
  arr.slice(-3,-1) //[3,4]

  //splice: 以新元素来替换旧元素，以此来修改数组的内容，返回被替换的内容,原数组被改变
  //start:开始位置  deleteCount:删除的个数  items:替换的内容  
  array.splice(start, deleteCount, [items[,items...]);

  var arr = [1,2,3,4,5]
  var newArray = arr.splice(0,3,"a","b","c")
  console.log(newArray)//[1, 2, 3]
  console.log(arr)//["a", "b", "c", 4, 5]

   //练习：
    var arr = [4, 6, 7, 8, 3, 46, 8];
    //从数组中截取一个新的数组[6,7,8,3],返回新的数组
    //删除[6,7,8,3]并替换成[1,1,1]
  ```


 

- 数组查找元素

  ```javascript
   //indexOf方法用来查找数组中某个元素第一次出现的位置，如果找不到，返回-1  
  array.indexOf(search, [fromIndex]);
  //astIndexOf()从后面开始查找数组中元素出现位置,如果找不到，返回-1  
  array.lastIndexOf(search, [fromIndex]);
  ```

- 操作数组里的元素

  ```javascript
  var arr = [12,34,56,89,78,23,45,19];

  //1.filter方法返回一个由符合函数要求的元素组成的新数组
  //调用数组的filter方法，添加过滤方法，符合规则的元素会被存放到新数组里
  //element:表示数组里的元素;
  //index:表示索引值;
  //array:表示传入的数组

  //filter方法的数组。
  var newArr = arr.filter(function(element,index,array){
    return element > 30; //返回true表示保留该元素（通过测试），false则不保留。
  });
  console.log(arr);  //filter方法不会改变原数组里的数据[12,34,56,89,78,23,45,19];
  console.log(newArr);  //新数组里保存符合要求的元素[34, 56, 89, 78, 45]

   //2.map方法让数组中的每个元素都调用一次提供的函数，将调用的后的结果存放到一个新数组里并返回。
    newArr = arr.map(function(element,index,array)){
          //在数组里的每一个元素的最后面都添加一个字符串"0"
  		return element + "0";
    });
    console.log(newArr);  //["120", "340", "560", "890", "780", "230", "450", "190"]
    console.log(arr);    //map方法不会改变原数组里的数据 [12,34,56,89,78,23,45,19]

   //3.forEach() 方法对数组的每个元素执行一次提供的函数,且这个函数没有返回值
    var result = arr.forEach(function (element, index, array) {
      //数组里的每一个元素都会被打印
  	console.log("第" + index + "个元素是" + element);
    });
    console.log(result);   //函数没有返回值

    //4.some() 方法测试数组中的某些元素是否通过由提供的函数实现的测试.
    result =  arr.some(function (element,index,array) {
      //数组里否有一些元素大于50.只要有一个元素大于，就返回true
  	console.log(element);//12,34,56
  	return element > 50;
    });
    console.log(result);  //true

    //5.every() 方法测试数组的所有元素是否都通过了指定函数的测试。
  result =  arr.every(function (element,index,array) {
    //数组里是否每一个元素都大于50.只有在所有的数都大于50时，才返回true
    console.log(element);  //12.  第0个数字就已经小于50了，就没有再比较的意义了
    	return element > 50;
    });
  console.log(result);   //false
  ```



- 清空数组

  ```javascript
  //1．array.splice(0,array.leng);//删除数组中所有的元素
  //2．array.length = 0;//直接修改数组的长度
  //3．array = [];//将数组赋值为一个空数组，推荐   
  ```



- 数组综合练习

  ```javascript
  var arr = ["c", "a", "z", "a", "x", "a", "a", "z", "c", "x", "a", "x"]
  //1. 找到数组中第一个a出现的位置
  //2. 找到数组中最后一个a出现的位置
  //3. 找到数组中每一个a出现的位置
  //4. 数组去重，返回一个新数组
  //5. 获取数组中每个元素出现的次数
  ```

  ​

## String对象

> 字符串可以看成是一个字符数组。因此字符串也有长度，也可以进行遍历。String对象很多方法的名字和和Array的一样。

- 查找指定字符串

  ```javascript
  //indexOf:获取某个字符第一次出现的位置，如果没有，返回-1
  //lastIndexOf:从后面开始查找第一次出现的位置。如果没有，返回-1
  ```

- 去除空白

  ```javascript
  trim();//去除字符串两边的空格，内部空格不会去除
  ```

- 大小写转换

```javascript
  toUpperCase()//全部转换成大写字母
  toLowerCase()//全部转换成小写字母
```

- 字符串拼接与截取

  ```javascript
  //字符串拼接
  //1.可以用concat，用法与数组一样(返回新的字符串)，但是字符串拼串我们一般都用 + 号

  //字符串截取的方法有很多，记得越多，越混乱，因此就记好用的就行
  //slice ：从start开始，end结束，包含头,不包含尾 ,返回一个新的字符串,原字符串不变
  //substring ：从start开始，end结束，包含头,不包含尾  ,返回一个新的字符串,原字符串不变
  // substr ： ：从start开始，截取length个字符。(推荐)
  ```

- 字符串切割

  ```javascript
  //split:将字符串分割成数组,原字符串不改变（很常用）
  var str = "张三,李四,王五";
  var arr = str.split(",");

  var str1 = "abcdef";
  var arr1 = str1.split("");//["a","b","c","d","e","f"] //这里可以理解为每一个字符之间有一个空的字符串
  ```

- 字符串替换

  ```javascript
  replace(searchValue, replaceValue)//参数：searchValue:需要替换的值    replaceValue:用来替换的值
  //注意,返回一个新的字符串,原来的字符串没有改变
  var str = "abcd"; 
  var newStr = str.replace("d","aaaa")
  console.log(str);//abcd
  console.log(newStr)//abcaaaa
  ```

- 练习

  ```javascript
  //1. 截取字符串"我爱中华人民共和国"，中的"中华"
  //2. "abcoefoxyozzopp"查找字符串中所有o出现的位置
  //3. 把字符串中所有的o替换成!
  //4. 把一个字符串中所有的空格全部去掉
  //5. 统计一个字符串中每个字符出现的次数 (作业)
  ```

## 面试题

```javascript
//1. 将字符串 "abcdefg"  翻转成   "gfedcba" (作业)
//2. 有一个链接： http://www.baidu.com?name=zs&id=100&desc=很帅 将链接的参数部分转换成一个对象,即{name:"zs", id=100,desc:"很帅}
//3. 有一个对象{name:"zs", id=100}和一个链接http://www.baidu.com,拼接成链接http://www.baidu.com?name=zs&id=100(作业)
```



## Date对象  

> Date对象基于1970年1月1日(世界标准时间)起的毫秒数
>
> 需要注意的是只能通过调用 Date 构造函数来实例化日期对象：以常规函数调用它（即不加 [new](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) 操作符）将会返回一个字符串，而不是一个日期对象。另外，不像其他JavaScript 类型，`Date 对象没有字面量格式。`
>

- 创建一个日期对象

  ```javascript
  var date = new Date();//使用构造函数创建一个当前时间的对象
  var date = new Date(1453094034000);//通过一个时间戳(从世界标准时间起始的毫秒数)
  var date = new Date("2017-04-22");//创建一个指定时间的日期对象
  var date = new Date("2017-03-22 00:52:34");//创建一个指定时间的日期对象
  var date = new Date(1995, 11, 17, 3, 24, 0);////创建一个指定时间的日期对象
   /*
   当Date作为构造函数调用并传入多个参数时，如果数值大于合理范围时（如月份为13或者分钟数为70），相邻的数值会被调整。比如 new Date(2013, 13, 1)等于new Date(2014, 1, 1)，它们都表示日期2014-02-01（注意月份是从0开始的）。其他数值也是类似，new Date(2013, 2, 1, 0, 70)等于new Date(2013, 2, 1, 1, 10)，都表示时间2013-03-01T01:10:00。
   */
  ```

- 时间戳

  ```javascript
  var date = +new Date();
  var date = Date.now();
  //1970年01月01日00时00分00秒起至现在的总毫秒数 
  //思考
  //如何统计一段代码的执行时间？
  ```

- 日期格式化(了解)

  ```javascript
  new Date().toString();//默认的日期格式
  new Date().toLocaleString();//本地风格的日期格式 2017/7/15 上午9:48:19
  new Date().toDateString();  //"Sat Jul 15 2017"
  new Date().toLocaleDateString(); //"2017/7/15"
  new Date().toTimeString(); //"09:54:19 GMT+0800 (中国标准时间)"
  new Date().toLocaleTimeString();//"上午9:54:44"
  ```

- 获取日期的指定部分

  ```javascript
  new Date().getSeconds();//获取秒
  new Date().getMinutes();//获取分钟
  new Date().getHours();//获取小时
  new Date().getDay();//获取星期，0-6    0：星期日
  new Date().getDate();//获取日，即当月的第几天
  new Date().getMonth();//返回月份，注意从0开始计算,0-11取值范围
  new Date().getFullYear();//返回年份   
  //思考：
  //封装一个函数，返回当前的时间，格式是：yyyy-MM-dd HH:mm:ss    2017-07-20 09:47:00
  ```




## arguments

> JavaScript中，arguments对象是比较特别的一个对象，实际上是当前函数的一个内置属性。也就是说所有函数都内置了一个arguments对象，arguments对象中存储了传递的所有的实参。arguments是一个伪数组，因此及可以进行遍历

```javascript
function a(){
  console.log(arguments)
}
a("a","b",1,true);  // ["a", "b", 1, true, callee: function, Symbol(Symbol.iterator): function]

//练习:
//1. 求任意个数的最大值
//2. 求任意个数的和
```



## window  

- name的特殊性

  > 当我们在全局申明了一个变量 或对象时,相当于给window对象添加了一个属性.
  >
  > window 对象本身拥有一个name的属性,用于iframe传递数据使用
  >
  > 如果我们在全局申明了name ,那么就会把window.name 的值覆盖掉.
  >
  > 建议全局时,不要使用name

  ​


## this

>this是Javascript语言的一个关键字。
>
>它代表函数运行时，自动生成的一个内部对象，只能在函数内部使用。
>
>随着函数使用场合的不同，this的值会发生变化。但是有一个总的原则，那就是this指的是，调用函数的那个对象。



**下面分四种情况，详细讨论this的用法。**

#### 1.纯粹的函数调用

这是函数的最通常用法，属于全局性调用，因此this就代表全局对象window。
请看下面这段代码，它的运行结果是1。

```javascript

　　function test(){
　　　　this.x = 1;
　　　　alert(this.x);
　　}
　　test(); // 1


为了证明this就是全局对象，我对代码做一些改变：
　　var x = 1;
　　function test(){
　　　　alert(this.x);
　　}
　　test(); // 1


  
　　var x = 1;
　　function test(){
　　　　this.x = 0;
　　}
　　test();
　　alert(x); //0
```



#### 2.作为对象方法的调用

> 函数还可以作为某个对象的方法调用，这时this就指这个上级对象。

```javascript
function test(){
　　　　alert(this.x);
　　}
var o = {};
o.x = 1;
o.m = test;
o.m(); // 1
```



#### 3.作为构造函数调用

> 就是通过这个函数生成一个新对象（object）。这时，this就指这个新对象。

```javascript
function test(){
　　　　this.x = 1;
}
var o = new test();
alert(o.x); // 1
//运行结果为1。为了表明这时this不是全局对象，我对代码做一些改变：
var x = 2;
function test(){
　　this.x = 1;
}
var o = new test();
alert(x); //2
//运行结果为2，表明全局变量x的值根本没变。
```



#### 4.apply调用



```javascript
//apply()是函数对象的一个方法，它的作用是改变函数的调用对象，它的第一个参数就表示改变后的调用这个函数的对象。因此，this指的就是这第一个参数。
　　var x = 0;
　　function test(){
　　　　alert(this.x);
　　}
　　var o={};
　　o.x = 1;
　　o.m = test;
　　o.m.apply(); //0
//apply()的参数为空时，默认调用全局对象。因此，这时的运行结果为0，证明this指的是全局对象。
//如果把最后一行代码修改为
　　o.m.apply(o); //1
//运行结果就变成了1，证明了这时this代表的是对象o。
```



#  14.delete

**delete **操作符会从某个对象上移除指定属性。成功删除的时候回返回 `true`，否则返回 `false`。但是，重要的是要考虑以下情况：

- 如果你删除的属性在对象上不存在，那么delete将不会起作用，但仍会返回true
- 如果 `delete` 操作符删除成功，则被删除的属性将从所属的对象上彻底消失。然后，如果该对象的原型链上有一个同名属性，则该对象会从原型链上继承该同名属性。（也就是说delete操作只会在自身的属性上起作用）
- 任何使用 [`var`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/var) 声明的属性不能从全局作用域或函数的作用域中删除。这样的话，delete操作不能删除任何在全局作用域中的函数（无论这个函数是来自于函数声明或函数表达式）除了在全局作用域中的函数不能被删除，在对象(object)中的函数是能够用delete操作删除的。
- 任何用[`let`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)或[`const`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const)声明的属性不能够从它被声明的作用域中删除。
- 不可设置的(Non-configurable)属性不能被移除。这意味着像[`Math`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math), [`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Array), [`Object`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object)内置对象的属性以及使用[`Object.defineProperty()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)方法设置为不可设置的属性不能被删除。




# 15.严格模式

除了正常运行模式，ECMAscript 5添加了第二种运行模式：严格模式（strict mode）

设立"严格模式"的目的，主要有以下几个：

> - 消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为;
>
> - 消除代码运行的一些不安全之处，保证代码运行的安全；
>
> - 提高编译器效率，增加运行速度；
>
> - 为未来新版本的Javascript做好铺垫。

"严格模式"体现了Javascript更合理、更安全、更严谨的发展方向，包括IE 10在内的主流浏览器，都支持.

另一方面，同样的代码，在"严格模式"中，可能会有不一样的运行结果；一些在"正常模式"下可以运行的语句，在"严格模式"下将不能运行。不过目前严格模式还处于发展阶段,有部分规则还没有被浏览器实现.

 

严格模式下不能使用十六进制,delete不能删除变量 否则会报错

### 1.如何进入严格模式?

> 　　"use strict";

老版本的浏览器会把它当作一行普通字符串，加以忽略。

#### 1.1 针对整个js代码

> 将"use strict"放在第一行，则整个js代码都将以"严格模式"运行。如果这行语句不在第一行，则无效

```html
<!--下面的代码表示，一个网页中依次有两段Javascript代码。前一个script标签是严格模式，后一个不是。-->　
<script>
　　　　"use strict";
　　　　console.log("这是严格模式。");
　</script>

　<script>
　　　　console.log("这是正常模式。");
　</script>
```

#### 1.2 针对单个函数

> 将"use strict"放在函数体的第一行，则整个函数以"严格模式"运行。

```javascript
function strict(){
　　　"use strict";
　　　return "这是严格模式。";
}

function notStrict() {
　　　return "这是正常模式。";
}
```



#### 1.3 建议写法

> 因为第一种调用方法不利于文件合并，下面这种用法更利于文件合并的情况下(jQuery源码也是自调用函数执行的)

```javascript
(function (){
　　"use strict";

　　// some code here
  
  function fn(){
    ...
	}
   window.fn = fn;
})(window);
```



### 2.严格模式对语法和行为的改变

#### 2.1 全局变量显式声明

> 严格模式禁止未申明赋值的这种用法，全局变量必须显式声明。

```javascript
"use strict";

a = 1; // 报错，a未声明
```

因此，严格模式下，变量都必须先用var命令声明，然后再使用。

#### 2.2 创建eval作用域(ajax阶段的内容)

> 正常模式下，Javascript语言有两种变量作用域（scope）：全局作用域和局部作用域。
>
> 严格模式创设了第三种作用域：eval作用域。
>
> 正常模式下，eval语句的作用域，取决于它处于全局作用域，还是处于局部作用域。
>
> 严格模式下，eval语句本身就是一个作用域，不再能够生成全局变量了，它所生成的变量只能用于eval内部。
>

```javascript
　"use strict";

　　var x = 2;

　　console.log(eval("var x = 5; x")); // 5

　　console.log(x); // 2
```



#### 2.3 增强的安全措施

##### 2.3.1 禁止this关键字指向全局对象

```javascript
　function f(){
　　　return this;
　} 
　// 返回window

　function f(){ 
　　　"use strict";
　　　return this;
　} 
　// 返回undefined
```

因此，使用构造函数时，如果忘了加new，this不再指向全局对象，而是报错。

```javascript
function f(){

　"use strict";

　this.a = 1;

};

f();// Uncaught TypeError: Cannot set property 'a' of undefined  
```



#### 2.4  重名错误

严格模式新增了一些语法错误。



- 函数不能有重名的参数

> 正常模式下，如果函数有多个重名的参数，可以用arguments[i]读取。严格模式下，这属于语法错误。

```javascript
"use strict";

　function f(a, a, b) { 
		
　　　return 1;

　}

 console.log(f());

//Uncaught SyntaxError: Duplicate parameter name not allowed in this context
```



#### 2.5 arguments对象的限制

> arguments是函数的参数对象，严格模式对它的使用做了限制。

- 不允许对arguments赋值

```javascript
"use strict";

　　function f() {

        console.log(arguments)

　　　　arguments = 1;
        
        console.log(arguments) 

　　}

    console.log(f())
    
    //Unexpected eval or arguments in strict mode
```



- arguments不再追踪参数的变化

```javascript
function f(a) {

　　　　a = 2;

　　　　return [a, arguments[0]];

　　}

　　console.log(f(1)); // 正常模式为[2,2]

　　function f(a) {

　　　　"use strict";

　　　　a = 2;

　　　　return [a, arguments[0]];

　　}

　　console.log(f(1)); // 严格模式为[2,1]
```



**注意:es6又对严格模式做出了一些修改,在某些情况下,不能直接使用显式的严格模式**

### 16== 比较规则

1 ==两边的类型必须一致,如果不一样进行类型转换,转换成一致的类型在进行比较

2 如果两个是引用类型,比较地址,如果是值类型,直接比较值

3 如果==两边一个是值类型,一个是引用类型,会把引用类型转成值类型再进行比较,

​	引用类型转值类型的规则:

​	(1)会先调用对象的valueOf()方法,会得到一个值,如果是值类型的就直接参与比较

​	(2) 如果valueOf()的结果不是值类型,会调用对象的toString(),会得到一个字符串类型的数据,进行比较

4 ==两边都是值类型比较规则:

​	(1) 默认null==undefind 结果为true

​	(2) 如果==两边有布尔类型的值  先将true 转为1   false转为0  再进行比较

​	(3) 如果一边是数字,一边是字符串会将字符串转为数字再进行比较

#### 面试题:

console.log({}==!{}) ===>false;

console.log([]==![])  ===>true;

### 17 try-catch-finally

```javascript
try{
	可能会出现错误的代码
}cacth(e){
	处理错误的代码
}finally{
	写最终执行的代码
	finally中的代码无论程序是否出错都会执行(都用于在程序执行完成 清理内存 来及回收等操作)
}
```

#### 手动抛出异常

throw  +  任何类型的数据( 最好是字符串和对象);

伪元素 不是标签而是css样式