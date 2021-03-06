# JavaScript高级程序设计

## 第一章 JavaScript简介

### 1.1 JavaScript简史
> 为减少用户直接与服务器进行频繁的数据交换，这样会加重用户的负担，所以人们对客户端语言的需求越来越强烈。Netscape公司与Sum公司共同建立开发联盟，在发布时为了搭上媒体热炒Java的顺风车，所以名字由LiveScript改为JavaScript。JavaScript一直没有标准规范，所以欧洲计算机制造商协会（ECMA）定义了一种名为ECMAScript的新脚本语言的标准

### 1.2 JavaScript实现
> 一个完整的JavaScript由ECMAScript(核心)、DOM(文档对象模型)、BOM(浏览器对象模型);

1. 文档对象模型(DOM):是针对XML但经过扩展用于HTML的应用程序编程接口(API，Application Programming Interface)。DOM把整个页面映射为一个多层节点结构。此时，负责制定Web通信标准的W3C(World Wide Web Consortium,万维网联盟)开始着手规划DOM。
2. 浏览器对象模型(BOM，Browser Object Model):支持可以访问和操作浏览器窗口的。开发人员使用 BOM可以控制浏览器显示的页面以外的部分。

## 第二章 在HTML中使用JavaScript
### 2.1 <script>元素
#### 2.1.1 标签位置
#### 2.1.2 延迟脚本
#### 2.1.3 异步脚本
#### 2.1.4 在XHTML中的用法
#### 2.1.5 不推荐使用的语法
### 2.2 嵌入代码与外部文件
### 2.3 文档模式
### 2.4 <noscript>元素
### 2.5 小结
1. 在包含外部JavaScript文件时，必须将src属性设置为指向相应文件的URL。而这个文件既可以是与包含它的页面位于同一个服务器上的文件，也可以是其他任何域中的文件。 
2. 所有<script>元素都会按照它们在页面中出现的先后顺序依次被解析。在不使用 defer 和 async 属性的情况下，只有在解析完前面<script>元素中的代码之后，才会开始解析后面<script>元素中的代码。
3. 由于浏览器会先解析完不使用defer属性的<script>元素中的代码，然后再解析后面的内容， 所以一般应该把<script>元素放在页面最后，即主要内容后面，</body>标签前面。
4. 使用defer属性可以让脚本在文档完全呈现之后再执行。延迟脚本总是按照指定它们的顺序执行。
5. 使用async属性可以表示当前脚本不必等待其他脚本，也不必阻塞文档呈现。不能保证异步脚 本按照它们在页面中出现的顺序执行。
6. 使用<noscript>元素可以指定在不支持脚本的浏览器中显示的替代内容。但在启用了脚本 的情况下，浏览器不会显示<noscript>元素中的任何内容。

## 第三章 基本概念
### 3.1 语法
#### 3.1.1 区分大小写
#### 3.1.2 标识符
>  标识符指变量、函数、属性的名字或者函数的参数
#### 3.1.3 注释
#### 3.1.4 严格模式
#### 3.1.5 语句
> 虽然语句结尾的分号不是必需的，但是建议不要省略，加上分号可以避免错误，开发人员也可以通过删除多余的空格来压缩代码，另外，加上分号也会在某些情况下增进代码的性能，因为这样解析器就不必花时间推测在哪里插入分号；
### 3.2 关键字和保留字
> 关键字是语言保留的，不能用做标识符;

> 保留字也不能用作标识符，尽管保留子现在没有特殊的用途，但他们有可能被用作关键字；

### 3.3 变量
> 变量是松散类型的，所谓松散类型就是可以用来保存任何类型的数据

### 3.4 数据类型
#### 3.4.1 typeof操作符
> typeof是一个操作符而不是一个函数

> typeof null会返回object，因为特殊值null被认为是一个空的对象调用

> typeof 后返回的类型都为字符串,typeof typeof 连续两次或多次typeof后结果为"string"

#### 3.4.2 Undefined类型

> undefined类型只有一个值，即特殊的undefined，在变量声明后未进行初始化时，这个变量值就是undefined ,undefined值与本身相等；

> undefined值的变量与未定义的变量还是不一样的，但是使用typeof操作符对未初始化的变量为undefined，对未声明的变量也返回undefined

#### 3.4.3 Null类型
> Null类型只有一个值，即特殊的null，null值表示一个空对象指针 typeof null为object；

> 如果定义的变量准备在将来用于保存对象，那么最好将该变量初始化为null；

> 实际上，undefined值是派生null值的，null == undefined为true，null === undfined为false

> null与自身是全等关系

#### 3.4.4 Boolean类型
> Boolean类型有两个值：true，false

> 任何对象转为Boolean类型都为true，null转为Boolean类型为false

#### 3.4.5 Number类型
> isFinite(),函数功能:判断一个数是不是有穷的，传入的参数在最大值与最小值之间则返回true；

> 任何涉及NaN的操作都会返回NaN,NaN与任何值都不相等，包括NaN本身；

> isNaN()判断参数是不是数值,对参数会有类型转换，之后判断是不是数值，不是数值返回true，否则返回false

> 数值转换:Number()可以用于任何数据类型；parseInt()，parseFloat()主要处理字符串类型

#### 3.4.6 String类型
> 字符字面量:String数据类型包含一些特殊的字符字面量，也叫转移字符，用于表示非打印字符，或者具有其他用途的字符；

> 字符串是不可变的，也就是说字符一点创建，它的值就不可能改变，要改变某个变量保存的字符串，首先要销毁原来的字符串，然后再用另一个包含新值的字符串填充该变量；

> null与undefined没有toString()方法，要想转换成字符串可以使用String()

#### 3.4.7 Object类型
==面试题==
> 值类型存在栈中，引用类型存在堆中，引用类型的值是指针指向的值，存在不同的位置是性能的优化，值类型存储空间小，引用类型的值可能需要存储空间比较大，闭包中的变量会保存在堆中，详情看闭包一节

> 为什么基本数据类型保存在栈中，而引用数据类型保存在堆中？
1）堆比栈大，栈比堆速度快；
2）基本数据类型比较稳定，而且相对来说占用的内存小；
3）引用数据类型大小是动态的，而且是无限的，引用值的大小会改变，不能把它放在栈中，否则会降低变量查找的速度，因此放在变量栈空间的值是该对象存储在堆中的地址，地址的大小是固定的，所以把它存储在栈中对变量性能无任何负面影响；
4）堆内存是无序存储，可以根据引用直接获取；

### 3.5  操作符
### 3.6  语句
> for-in语句是一种精准的 迭代语句，可以用来枚举对象的所有属性；

> label：使用label可以在代码中添加标签，可以与break活continue语句连用
```
    outermost: for (var i=0; i < 10; i++) { 
        for (var j=0; j < 10; j++) { 
            if (i == 5 && j == 5) { 
                break outermost; 
            } 
            num++; 
        } 
    }
```

> with语句的作用是将代码的作用域设置到一个特定的作用域中；大量使用with语句会导致性能下降，也不方便调试，因此不建议使用with语句
```
    with(location){ 
        var qs = search.substring(1); 
        var hostName = hostname; 
        var url = href; 
    }
```

### 3.7  函数
#### 3.7.1 理解参数
> 函数参数实际上使用数组表示的，在函数体内使用arguments访问该数组，从而获取传递给函数的每一个参数；

> 函数命名的参数只是提供便利，并不是必须的；

> arguments对象可以与命名参数一起使用，arguments中的值与对应参数的值保持一致
#### 3.7.2 没有重载
>定义两个相同的名字的函数，该名字只属于后一个函数；

### 3.8 小结
1. ECMAScript 中的基本数据类型包括 Undefined、Null、Boolean、Number 和 String。 
2. 与其他语言不同，ECMScript 没有为整数和浮点数值分别定义不同的数据类型，Number 类型可 用于表示所有数值。
3. ECMAScript 中也有一种复杂的数据类型，即 Object 类型，该类型是这门语言中所有对象的基 础类型。
4. 严格模式为这门语言中容易出错的地方施加了限制。
5. ECMAScript 提供了很多与 C 及其他类 C 语言中相同的基本操作符，包括算术操作符、布尔操作 符、关系操作符、相等操作符及赋值操作符等。
6. ECMAScript 从其他语言中借鉴了很多流控制语句，例如 if 语句、for 语句和 switch 语句等。 ECMAScript 中的函数与其他语言中的函数有诸多不同之处。
7. 无须指定函数的返回值，因为任何 ECMAScript 函数都可以在任何时候返回任何值。
8. 实际上，未指定返回值的函数返回的是一个特殊的 undefined 值。
9. ECMAScript 中也没有函数签名的概念，因为其函数参数是以一个包含零或多个值的数组的形式 传递的。
10. 可以向 ECMAScript 函数传递任意数量的参数，并且可以通过 arguments 对象来访问这些参数。
11. 由于不存在函数签名的特性，ECMAScript 函数不能重载。

==面试题目:==
1. ==typeof可以识别所有值类型(Number,String等)，函数，引用类型(但是不能细分引用类型Object,Arr)==
2. ==类型转换：字符串拼接、两等运算符、if语句和逻辑运算；强制类型转换：parseInt parseFloat toString=
```
const a = 100 + 10    //110
const a = 100 + '10'  //10010
const a = true + '10' //true10
100 == '100' //true
0 == ''      //true
0 == false   //true
false == ''  //true
null ==  undefined //true
//除了 == null之外，全部用三等===
const obj = { x:100 }
if(obj.a == null){}
//相当于
if(obj.a === null || obj.a === undefined){}

//truly变量：两步非运算为真的变量
//falsely变量：两步非运算为假的变量 !!0 !!NAN !!'' !!null !!undefined !!false
```

## 第四章 变量、作用域和内存问题
### 4.1 基本类型和引用类型的值
#### 4.1.1 动态的属性
> 对于引用类型的值，我们可以为其添加属性和方法，也可以改变和删除其属性和方法;
#### 4.1.2 复制变量值
> 当复制基本类型后，两个变量互不影响，存在栈中不同内存位置；

> 当复制引用类型后，两个变量互相影响，指向堆中同一个位置；

#### 4.1.3 传递参数(需要再次理解)
> 所有函数的参数都是按值传递的，也就是说把函数外部的值复制给函数内部的参数，就是把值从一个变量复制到另一个变量一样，对于不同的数据类型同上一节内容；

#### 4.1.4 检测类型
> 使用typeof可以检测基本类型，检测引用类型时会一直显示object；使用instanceof可以检测出是具体哪种类型的对象，使用方法 result = variable instanceof constructor

### 4.2 执行环境及作用域
> **执行环境**定义了变量或函数有权访问的其他数据，决定了它们各自的行为。每个执行环境都有 一个与之关联的**变量对象**，环境中定义的所有变量和函数都将保存在这个对象中；

> 某个执行环境中所有代码执行完毕后，该环境被销毁，环境中的所有变量和函数定义也随之销毁；

> 当代码在一个环境中执行时，会创建变量对象的一个**作用域链**，作用域链的用途是保证对执行环境有权访问的所有变量和函数的有序访问；

> 内部环境可以通过作用域链访问所有的外部环境，但外部环境不能访问内部环境中的任意变量和函数；
#### 4.2.1 延长作用域链
> 有些语句可以在作用域链的前端临时增加一个变量对象，该变量对象会在代码执行后被移除；

> try-catch语句中的catch块，with语句都会在作用域的前端添加一个变量对象；对于with语句来说，会将指定的对象添加到作用域链中，对于catch中，会创建一个新的变量对象；
#### 4.2.2 没有块级作用域

### 4.3 垃圾收集
#### 标记清除

> 先标记变量，之后清楚进行给无标记的变量进行清除

#### 引用计数

> 无法消除循环引用的变量

#### 、性能问题、管理内存

### 4.4 小结
1. 基本类型值在内存中占据固定大小的空间，因此被保存在栈内存中；
2. 从一个变量向另一个变量复制基本类型的值，会创建这个值的一个副本；
3. 引用类型的值是对象，保存在堆内存中；
4. 包含引用类型值的变量实际上包含的并不是对象本身，而是一个指向该对象的指针；
5. 从一个变量向另一个变量复制引用类型的值，复制的其实是指针，因此两个变量最终都指向同 一个对象；
6. 确定一个值是哪种基本类型可以使用 typeof 操作符，而确定一个值是哪种引用类型可以使用 instanceof 操作符。 
<p>所有变量（包括基本类型和引用类型）都存在于一个执行环境（也称为作用域）当中，这个执 行环境决定了变量的生命周期，以及哪一部分代码可以访问其中的变量。以下是关于执行环境的几 点总结：</p>

1. 执行环境有全局执行环境（也称为全局环境）和函数执行环境之分;
2. 每次进入一个新执行环境，都会创建一个用于搜索变量和函数的作用域链;
3. 函数的局部环境不仅有权访问函数作用域中的变量，而且有权访问其包含（父）环境，乃至全 局环境;
4. 全局环境只能访问在全局环境中定义的变量和函数，而不能直接访问局部环境中的任何数据;
5. 变量的执行环境有助于确定应该何时释放内存。
<p>JavaScript是一门具有自动垃圾收集机制的编程语言，开发人员不必关心内存分配和回收问题。可以对JavaScript的垃圾收集例程作如下总结.</p>

1. 离开作用域的值将被自动标记为可以回收，因此将在垃圾收集期间被删除。
2. “标记清除”是目前主流的垃圾收集算法，这种算法的思想是给当前不使用的值加上标记，然后再回收其内存。
3. 另一种垃圾收集算法是“引用计数”，这种算法的思想是跟踪记录所有值被引用的次数。JavaScript 引擎目前都不再使用这种算法；但在 IE 中访问非原生 JavaScript 对象（如 DOM元素）时，这种 算法仍然可能会导致问题。
4. 当代码中存在循环引用现象时，“引用计数”算法就会导致问题;
5. 解除变量的引用不仅有助于消除循环引用现象，而且对垃圾收集也有好处。为了确保有效地回 收内存，应该及时解除不再使用的全局对象、全局对象属性以及循环引用变量的引用。

## 第五章 引用类型
> 引用类型是一种数据结构，用于将数据和功能组织在一起，引用类型有时候也被称为**对象定义**，因为它描述的是一类对象所具有的属性和方法；
### 5.1 Object类型
> 创建object实例方式:

```
//使用new操作符后跟Object构造函数
var person = new Object();
    person.name = "mxm@";
    person.age = 18;
//使用对象字面量表示法 
var persson = {
    name:"mxm@",
    age:18
}
//使用构造函数
var M = function(name){this.name = name}
var n = new M('mxm')
//使用Object.create()
var p = {name:'mxm'}
var obj = Object.create(p)
//设置属性-计算属性名,使用中括号包裹起来，里面是变量的名称
var persson = {
    [name]:"mxm@",
}
```
> 访问对象属性

```
//[]的优点是可以通过变量来访问属性；如果属性名中包含会导致语法错误的字符，或者属性名使用的是关键字或保留字，也可以使用方括号表示法
alert(person["name"]);
var propertyName = "name"; 
alert(person[propertyName]);
person["first name"] = "Nicholas";
//直接使用点访问属性
alert(person.name);
//通常，除非必须使用变量来访问属性，否则我们建议使用点表示法
```

### 5.2 Array类型
> 数组中每一项可以存放任何类型的的数据，数组的大小可以动态调整

> 数组方法的功能是什么，返回值是什么，是否会对原数组造成影响

> 创建数组的基本方式有两种

```
//使用Array构造函数,new操作符可以省略
var color = new Array()
//使用数组字面量表示法
var color = ["red","blue"]
```
> 数组的length不是只读的，因此，通过设置这个属性，可以从数组的末尾移除项或像数组中添加新项；

```
var colors = ["red", "blue", "green"];
colors[colors.length] = "black";
```

#### 5.2.1 检测数组
> instanceof只能在同一个执行环境中进行检测，不能检测多个执行环境同时存在的情况，因此可以使用isArray(),使用方法Array.isArray(value),返回Boolean值

#### 5.2.2 转换方法
> 所有对象都具有toLocaleString(),toString(),valueof()方法

> toLocaleString(),toString()返回的是由数组中每个值的字符串形式拼接而成的一个以逗号分隔的字符串，valueof()返回数组

```
[1,2,3,4].toString()//"1,2,3,4"
[1,2,3,4].toLocaleString()//"1,2,3,4"
[1,2,3,4].valueOf()//[1, 2, 3, 4]
```
> 使用join()可以得倒任意字符分割的字符串；
#### 5.2.3 栈方法
> 对栈的操作只能在栈顶进行操作，栈的顶部相当于数组的最后一项

> push()可以接受任意数量的参数，把他们逐个添加到数组末尾，并返回修改后数组的长度，改变原数组，不是纯函数

```
var color = ["red"];color.push("blue","green");//3
```
> pop()则从数组末尾移除最后一项，返回被移除的项，，改变原数组，不是纯函数

```
var color = ["red"];color.push("blue","green");color.pop()//"green"
```
#### 5.2.4 队列方法
> 队列在列表的末端添加项，从列表的前端移除项。由于push()是向数组末端添加项的方法，因此要模拟队列只需要从一数组前端取得项的方法，实现这一操作可以使用shift()方法，它能够移除数组中的第一项并返回该项，同时数组的长度减一，结合使用push()与shiift(),则可以像使用队列一样使用数组；改变原数组，不是纯函数

```
var color = [];color.push("blue","green");color.shift();//"blue"
```
> unshift()可以在数组的前面添加任意个项并返回新数组的长度，因此使用unshift()与pop()方法，可以从相反的方向模拟队列，即在数组的前端添加项，从数组末端移除项，改变原数组，不是纯函数

```
var color = [];color.unshift("blue","green");color.pop();//"green"
```
#### 5.2.5 重排序方法

- reverse()

  - reverse()反转数组项的顺

  - ```javascript
    var color = ["red","blue","green"];color.reverse();//["green", "blue", "red"]
    ```

- sort()

  - sort()默认情况下按照升序排列数组项，为了实现排序，sort()方法会调用每个数组项的toString(),然后得到比较的字符串；改变原数组，不是纯函数

  - sort()在进行比较字符串时，数字无法正常排序，因此sort()方法可以接受一个比较函数作为参数，以便我们指定哪个值在哪个值的前面；比较函数接收两个参数(默认升序)，如果第一个参数应该位于第二个之前则返回一个负数，如果两个参数相等则返回0，如果第一个参数应该位于第二个之后则返回一个正数。

  - ```javascript
    function compore(value1,value2){
        if(value1 < value2){
            return -1
        }else if(value1 > value2){
            return 1 
        }else{
            return 0
        }
    }
    [1,3,2,6,4,9,2].sort(compore);//[1, 2, 2, 3, 4, 6, 9]
    ["1","3","2","6","4","9","2"].sort(compore);//["1", "2", "2", "3", "4", "6", "9"]
    ```

  - 对于上面的compore函数用于数组中每一项的类型为Number、String；

  - sort源码解析

    查看两个版本的v8源码
    
    ```javascript
    //https://github.com/v8/v8/blob/5.9.221/src/js/array.js#L709
    //此方法的入口
    utils.InstallFunctions(GlobalArray.prototype, DONT_ENUM, [
      ...
      "sort", getFunction("sort", ArraySort),
      ...
    ])
    //进入InnerArraySort,对类数组对象以及空洞数组进行特殊处理，然后进行排序
    //之后看快速排序，仔细看里面的备注，都是性能优化的点
      function QuickSort (a, from, to) {
      // 基准选择第一个元素
      var third_index = 0;
      while (true) {
        // 待排序数组长度 <= 10 采用插入排序
        if (to - from <= 10) {
          InsertionSort(a, from, to);
          return;
        }
        if (to - from > 1000) {
          // 每隔 200 ~ 215 （根据 length & 15的结果）个元素取一个值，
          // 然后将这些值进行排序，取中间值的下标
          // 这里的排序其实又是一个递归调用
          third_index = GetThirdIndex(a, from, to);
        } else {
          // 将中间元素设为基准值
          third_index = from + ((to - from) >> 1);
        }
        // 将第一个,中间元素（上面获取的基准值），最后一个元素三者中的中位数作为基准值
        var v0 = a[from];
        var v1 = a[to - 1];
        var v2 = a[third_index];
    		...
        ...
        ...
    };
    此版代码的bug：在执行ArraySort([1,2,13,14,5,6,17,18,9,10,11,12,31,41],()=>0)，不会原样输出，具体原因看代码，所以后来有了优化的代码
    ```
    
    - es2019以后开始使用TimSort方法
    
    ```javascript
    //https://github.com/v8/v8/blob/7.6.303/third_party/v8/builtins/array-sort.tq
    此版的sort方法进行优化，使用TimSort算法进行排序；
    参考链接:https://juejin.cn/post/6844904131518267400
    主要思想融合了归并算法和二分插入排序算法的精髓；
    ```
    
    

- valueof()

  - 对于数组中每一项的类型为数值类型或者valueof()方法返回数值类型，可以使用简单的比较函数

  - ```javascript
    function compare(value1, value2){ 
        return value1 - value2; 
    };
    [1,3,5,2,9,5].sort(compare);//[1, 2, 3, 5, 5, 9]
    ```

    

#### 5.2.6 操作方法
> concat()可以基于当前数组中的所有项创建一个新数组，不改变原数组是纯函数

```
[1].concat(2,"3",["red"])//[1, 2, "3", "red"]
```
> <font color="red">已多次使用</font>
>
> slice()基于当前数组中的一个或多个创建一个新数组，接受一或两个参数；

> slice(起始位置，结束位置(可省略))，不包含结束位置的项；

> 如果 slice()方法的参数中有一个负数，则用数组长度加上该数来确定相应的位 置。例如，在一个包含 5 项的数组上调用 slice(-2,-1)与调用 slice(3,4)得到的 结果相同。如果结束位置小于起始位置，则返回空数组，不改变原数组是纯函数。

```
[1,2,3,4,5,6].slice(3)//[4, 5, 6]
[1,2,3,4,5,6].slice(3,5)//[4, 5]
[1,2,3,4,5,6].slice(-3,-5)//[]
[1,2,3,4,5,6].slice(-5,5)//[2, 3, 4, 5]
```
> splice():删除：可以删除任意数量的项，只需指定个参数：要删除的**第一项的位置和要删除的项数**。例如，splice(0,2)会删除数组中的前两项，改变原数组不是纯函数。

> <font color="red">已多次使用，但是未正确使用，参数的理解有误</font>
>
> splice():插入：可以向指定位置插入任意数量的项，只需提供3个参数：**起始位置(从起始位置的前一位开始插入)、0（要删除的项数)和要插入的项**。如果要插入多个项，可以再传入第四、第五，以至任意多个项。例如， splice(2,0,"red","green")会从当前数组的位置开始插入字符串"red"和"green"。

> splice():替换：可以向指定位置插入任意数量的项，且同时删除任意数量的项，只需指定 3 个参数：起 始位置、要删除的项数和要插入的任意数量的项。插入的项数不必与删除的项数相等。例如， splice(2,1,"red","green")会删除当前数组位置2的项，然后再从位置2开始插入字符串 "red"和"green"。

```javascript
[1,2,3,4,5].splice(2,2)//[3, 4]
var arr = [1,2,3,4,5];arr.splice(2,0,1,2);arr//[1, 2, 1, 2, 3, 4, 5]
var arr = [1,2,3,4,5];arr.splice(2,1,1,2);arr//[1, 2, 1, 2, 4, 5]
```
#### 5.2.7 位置方法
> 为数组实例添加了两个位置方法：indexOf()和 lastIndexOf()。这两个方法都接收 两个参数：要查找的项和（可选的）表示查找起点位置的索引。其中，indexOf()方法从数组的开头（位 置 0）开始向后查找，lastIndexOf()方法则从数组的末尾开始向前查找。

```
[1,2,3,4,5,6].indexOf(3,0)//2
[1,2,3,4,5,6].indexOf(3,3)//-1
```
#### 5.2.8 迭代方法
> every()：对数组中的每一项运行给定函数，如果该函数对每一项都返回 true，则返回 true，如果有返回结果不是true则直接结束循环，默认不写return，则代表返回undefined，认定成false，不支持break、continue，可以使用return，every是受控制的循环，every() 不会对空数组进行检测，纯函数。

> filter()：对数组中的每一项运行给定函数，返回该函数会返回 true 的项组成的数组，不改变原数组是纯函数。

> forEach()：对数组中的每一项运行给定函数。这个方法没有返回值，非受控循环，不是纯函数，不能使用break、continue,return减少循环或停止循环，不改变原数组

> map()：对数组中的每一项运行给定函数，返回每次函数调用的结果组成的数组，不改变原数组是纯函数。

> some()：对数组中的每一项运行给定函数，如果该函数对任一项返回 true，则返回 true。

> for in:主要为循环object，但可以遍历数组，但是有一定弊端，当索引不是数字时，也可以正常访问到，参数index的类型为字符串，因为此时数组被认成对象，对象的索引是字符串，支持break、continue减少循环，纯函数

```
[1,2,3,4,5].every((item,index,arrray)=>(item > 0))//true
[1,2,3,4,5].every((item,index,arrray)=>(item > 2))//false
[1,2,3,4,5].filter((item,index,arrray)=>( item > 2))//[3, 4, 5]
[1,2,3,4,5].forEach((item,index,arrray)=>{})
[1,2,3,4,5].map((item,index,arrray)=>(item*2))//[2, 4, 6, 8, 10]
[1,2,3,4,5].some((item,index,arrray)=>(item > 2))//true
[1,2,3,4,5].some((item,index,arrray)=>(item > 5))//false
const a=[1,2,3,4,5];for(let index in a){console.log("a",a[index])};
//1,2,3,4,5，index的类型为字符串
const a=[1,2,3,4,5];a.c=8;for(let index in a){console.log("a",a[index])};console.log("a",a)
//1,2,3,4,5,8
==面试题==
[10,20,30].map(parseInt)//[10,NaN,NaN]
[10,20,30].map((num,index)=>parseInt(num,index))
parseInt() 函数可解析一个字符串，并返回一个整数。
parseInt(string, radix):string必需,要被解析的字符串;radix:可选。表示要解析的数字的基数。该值介于 2 ~ 36 之间。如果省略该参数或其值为0，则数字将以10进制数来解析。如果它以 “0x” 或 “0X” 开头，将以16进制数解析。如果该参数小于 2 或者大于 36，则 parseInt()将返回 NaN。字符串string中的数字不能大于radix才能正确返回数字结果值
const arr = [10,0,10,20,30,40,50,60,70].map((num,index)=>parseInt(num,index))//[10, NaN, 2, 6, 12, 20, 30, 42, 56]
```
#### 5.2.9 归并方法
> reduce()和 reduceRight()。这两个方法都会迭代数组的所有项，然后构建一个最终返回的值。其中，reduce()方法从数组的第一项开始，逐个遍历到最后。而reduceRight()则从数组的最后一项开始，向前遍历到第一项。两个参数；第一个为函数：四个参数：前一个值、当前值、项的索引和数组对象，第二个参数：初始值(也就是第一次prev的值),不是纯函数。

```javascript
[1,2,3,4,5].reduce((prev,cur,index,array)=> (prev + cur) )
```
#### 5.2.10题目

1. ==数组中最大值==
    1. forEach循环；(变成数组:Array.prototype.slice.call(argunments))
    2. Math.max();
2. ==数组拍平flatern==
```
    function flat(arr){
      const isDeep = arr.some(item => item instanceof Array);
      if(!isDeep){
        return arr
      }
      const res = Array.prototype.concat.apply([],arr)
      return flat(res)
    }
    const result = flat([1,2,[1,[1,3]],4,5])
    console.log("result",result)
```
3. ==数组去重==
```
    function unique(arr){
      const res = [];
      arr.forEach(item =>{
        if(res.indexOf(item) < 0){
            res.push(item)
        }
      })
      return res
    }
    const res = unique([10,20,30,10])
    console.log(res)
    //set是一种无序结构，不能重复
    function unique(arr){
      const set = new Set(arr);
      return [...set]
    }
    const res = unique([10,20,30,10])
    console.log(res)
    //两种方式区别:第一种效率比较低，推荐使用第二种
```

### 5.3 Date类型
### 5.4 RegExp类型
> 字符字面量定义正则表达式
> 使用RegExp构造函f数创建正则表达式
#### 5.4.1 RegExp实例属性
>  RegExp的每个实例都具有下列属性，通过以下信息可以获取有关模式的各种信息 

1. global：布尔值，表示是否设置了 g 标志;
2. ignoreCase：布尔值，表示是否设置了 i 标志。
3. lastIndex：整数，表示开始搜索下一个匹配项的字符位置，从 0 算起。
4. multiline：布尔值，表示是否设置了 m 标志。
5. source：正则表达式的字符串表示，按照字面量形式而非传入构造函数中的字符串模式返回

```
var pattern = / \.at /gi;
pattern.global; //true
pattern.ignoreCase;//true
pattern.lastIndex;//0
pattern.multiline;//false
pattern.source;//" \.at "
```
#### 5.4.2 RegExp实例方法

```
var text = "mom and dad and baby"; 
var pattern = /mom( and dad( and baby)?)?/gi; 
var matches = pattern.exec(text); 
matches.index;//0
matches.input;//"mom and dad and baby"
matches[0];//"mom and dad and baby"
matches[1];//"and dad and baby"
matches[2];//"and baby"
```
```
var text = "000-00-0000"; 
var pattern = /\d{3}-\d{2}-\d{4}/;
pattern.test(text)//true
```
> RegExp 实例继承的 toLocaleString()和toString()方法都会返回正则表达式的字面量，与创建正则表达式的方式无关。

> 参考链接[!https://deerchao.cn/tutorials/regex/regex.htm]

#### 5.4.3 RegExp构造函数属性
#### 5.4.4 模式局限性

==面试题==

```
// 下划线转换驼峰
function toHump(name) {
    return name.replace(/\_(\w)/g, function(all, letter){
        return letter.toUpperCase();
    });
}
// 驼峰转换下划线
function toLine(name) {
  return name.replace(/([A-Z])/g,"_$1").toLowerCase();
}


// 测试
let a = 'a_b2_345_c2345';
console.log(toHump(a));

let b = 'aBdaNf';
console.log(toLine(b));
//用正则表达式来将字符串"I? love ?? the ?great ? ?wall in ?beijing"更改为："I love the Great Wall in Beijing"，主要是 为了解决编码的问题导致的问题，规律：
//1，乱码只有两种特殊字符分别是'?'和' ';
//2，如果乱码的末尾是'?'则它的下一位字母肯定是大写；
function strTran(str){
	const strUp = str.replace(/[\?,](\w)/g, function(all, letter){
        return letter.toUpperCase();
    });
	return strUp.replace(/\?+/g, "")
}
console.log(strTran("I? love ?? the ?great ? ?wall in ?beijing"));
```



### 5.5 Function类型
> 由于函数是对象，因此函数名实际上也是一个指向函数的指针，不会与某个函数绑定

> 定义函数方式:函数声明语法定义、函数表达式定义函数、使用Function构造函数定义函数

```javascript
function sum (num1, num2) { return num1 + num2; }
var sum = function(num1, num2){ return num1 + num2; };
var sum = new Function("num1", "num2", "return num1 + num2");
//函数默认返回值为undefined
function nums(num1, num2){ 
  console.log(num1 + num2)
}
console.log(nums(1,2))//undefined
```
>  由于函数名仅仅是指向函数的指针，因此函数名与包含对象指针的其他变量没有什么不同，换句话说，函数可能有多个名字
#### 5.5.1 没有重载
#### 5.5.2 函数声明与函数表达式
> 在解析器中对函数声明与函数表达式的处理方式不同,使用函数声明时解析器存在函数声明提升的过程，读取并将函数声明添加到执行环境中，函数表达式不会存在函数提升状态，因此调用函数的代码不能写在函数定义的前面；

> 使用var const let定义函数表达式时，注意到变量提升的问题，不同定义方式变量提升不一致

#### 5.5.3 作为值的函数
> 函数名本身就是变量，所以函数也可以作为值来使用，可以把函数像传递参数一样传递给另外一个函数，而且可以将函数作为一个函数的返回结果；

```
function callSomeFunction(someFunction, someArgument){ 
    return someFunction(someArgument);
}
function add10(num){ 
    return num + 10; 
}
callSomeFunction(add10, 10);//20

function getGreeting(name){ 
    return "Hello, " + name;
}
callSomeFunction(getGreeting, "Nicholas");//"Hello, Nicholas"
```
```
function createComparisonFunction(propertyName) { 
    return function(object1, object2){ 
        var value1 = object1[propertyName]; 
        var value2 = object2[propertyName]; 
        if (value1 < value2){ 
            return -1; 
        } else if (value1 > value2){ 
            return 1;
        } else { 
            return 0;
        } 
    }; 
}
var data = [{name: "Zachary", age: 28}, {name: "Nicholas", age: 29}]; 
data.sort(createComparisonFunction("age"));//[{name: "Zachary", age: 28},{name: "Nicholas", age: 29}]
```
#### 5.5.4 函数内部属性
> arguments中callee属性是一个指针，指向拥有这个arguments对象的函数，当函数在严格模式下运行时，访问 arguments.callee 会导致错误。在阶乘函数中为了解耦，可以使用；

```
function factorial(num){ 
    if (num <=1) { 
        return 1; 
    } else { 
        return num * arguments.callee(num-1) 
    } 
}
```
> 函数内部另一个特殊对象是this，在函数执行的时候才能知道this具体指什么，
#### 5.5.5 函数属性和方法
> 函数也是对象，也具有属性和方法；

1. length属性代表函数接受参数的个数;
2. prototype是保存它们所有实例方法的真正所在
3. 每个函数都包含两个非继承而来的方法:apply()和call(),这两个方法的用途都是在特定的作用域中调用函数，实际上等于设置函数体内this对象的值，apply()方法接收来两个参数：一个是在其中运行函数的作用域，另一个是参数数组(可以是Array的实例，也可以是arguments对象)，call()方法参数：一个是在其中运行函数的作用域，其余参数是直接传递给函数(传递给函数的参数必须逐个列举出来)；

```
function sum(num1, num2){ 
    return num1 + num2; 
} 
function callSum1(num1, num2){ 
    return sum.apply(this, arguments); 
} 
function callSum2(num1, num2){ 
    return sum.apply(this, [num1, num2]); 
} 
callSum1(10,10);//20
callSum2(10,10);//20

function callSum(num1, num2){ 
    return sum.call(this, num1, num2); 
}
callSum(10,10);//20
```
> apply()与call()可以扩充函数的作用域；

```javascript
window.color = "red"; 
var o = { color: "blue" }; 
function sayColor(){ 
    alert(this.color); 
} 
sayColor(); //"red"
sayColor.call(this); //"red"
sayColor.call(window); //"red"
sayColor.call(o);//"blue"
```
> 以上代码方式不需要给o对象添加sayColor方法，直接运用更改作用域

> ECMAScript 5 还定义了一个方法：bind()。这个方法会创建一个函数的实例，其 this 值会被绑 定到传给 bind()函数的值;

#### 5.5.6 构造函数

> **<font color="red">使用new时，函数中使用return会发生什么？</font>**

- 使用new时发生了什么？

  - 创建一个空的新对象；

  - 将构造函数的作用域赋给这个对象(**因此this指向了这个对象，也就是将新对象的原型指向了构造函数的prototype属性**)；

  - 执行构造函数中的代码(**为这个对象添加属性和方法以及执行构造函数中其他代码，假如构造函数中没有为该对象添加属性和方法(也就是没有this赋值)，则是一个空对象(下面有例子)**)；

  - 返回这个新对象(**如果被调用的函数没有显式的 return 表达式（仅限于返回对象），则隐式的会返回 this 对象 - 也就是新创建的对象**)；

    **注意：原本的构造函数是window对象的方法，如果不用new操作符而直接调用，那么构造函数的执行对象就 是window，即this指向了window。现在用new操作符后，this就指向了新生成的对象。理解这一步至关重要。**

    ```javascript
    function Person() {
      // this.age = 22;
      window.age=23;
      this.name='tom'
      let name = 'tony';
      console.log(name);//tony,直接返回let定义的变量
    }
    let p = new Person();  //自动执行构造函数中的代码，输出 tony
    console.log(p.age) // undefined,由于构造函数没有定义age，所以undefined;只有通过this.定义的变量才能通过实例获取到
    console.log(window.age) // 23
    console.log(p.name) // tom，之所以没有打印出tony，是因为let name = 'tony'这个this.中没有赋这个值
    整体输出结果："tony" undefined 23 "tom"//先打印出tony请看上面的new之后的执行顺序
    
    //假如函数调用时未按照构造函数调用
    function Keith() {
    	this.height = 180;//正常函数调用this指向window
    }
    var person = Keith();
    console.log(person.height); //TypeError: person is undefined
    console.log(window.height); //180
    
    //构造函数中没有为对象实力添加属性和方法
    function Keith() {
    	return 'this is a message';//return中只要是基本类型就不会影响实例的内容
    }
    var boy = new Keith();
    console.log(boy); // {}
    ```

    

- 构造函数中return后发生了什么

  - 构造函数中无return时，默认返回new时第一步创建的新对象

    ```javascript
    function Foo(age) {
      this.age = age;
    }
    var o = new Foo(111);
    console.log(o);//{age:111}
    ```

  - 构造函数return基本类型时，返回new时第一步创建的新对象

    ```javascript
    function Foo(age) {
      this.age = age;
      return undefined //或return null、return 111、return 'aaaa'、return true
    }
    var o = new Foo(111);
    console.log(o);//{age:111}
    ```

  - 构造函数return引用类型时，返回return语句后的引用类型值

    ```javascript
    function Foo(age) {
      this.age = age;
      return { type: "我是显式返回的" };//或return ['显式返回']、return function(){console.log("我是显式返回的")}
    }
    
    var o = new Foo(222);
    console.log(o);//{ type: "我是显式返回的" }
    ```

    

#### 5.5.7 题目

> **<font color="red">浅拷贝与深拷贝:</font>**

> 浅拷贝只复制一层对象的属性，并不包括对象里面的为引用类型的数据。深拷贝是对对象以及对象的所有子对象进行拷贝。

> objec.assgin不是深拷贝，它是第一层级的深层拷贝，深层级无法深拷贝；扩展运算符也是浅拷贝，它是第一层级的深层拷贝，深层级无法深拷贝

```
const arr1 = {
    name:'mxm',
    age:18,
    address:{
        city:'南城子'
    },
    fruit:['香蕉','火龙果','葡萄']
}
const arr2 = deepClone(arr1)
arr2.fruit[3] = '香蕉'
console.log("arr2",arr2);
console.log("arr1",arr1)
function deepClone(obj = {}){
    if(typeof obj != 'bject' || typeof obj == null){
        return obj
    }
    let result
    if(obj instanceof Array){
        result = []
    }else{
        result = {}
    }
    for(let key in obj){
        if(obj.hasOwnProperty(key)){
            /**深浅拷贝的区别**/
            result[key] = deepClone(obj[key])//深拷贝
            result[key] = obj[key]//浅拷贝
        }
    }
    return result
}
```
==判断对象是否相等==
```
    isObjectEqual(obj1, obj2){
        let o1 = obj1 instanceof Object
        let o2 = obj2 instanceof Object
        if(!o1 || !o2) {    // 如果不是对象 直接判断数据是否相等
            return obj1 === obj2
        }
        // 判断对象的可枚举属性组成的数组长度
        if(Object.keys(obj1).length !== Object.keys(obj2).length) {
            return false
        }
        for(let attr in obj1) {
            let a1 = Object.prototype.toString.call(obj1[attr]) == '[object Object]'
            let a2 = Object.prototype.toString.call(obj2[attr]) == '[object Object]'
            let arr1 = Object.prototype.toString.call(obj1[attr]) == '[object Array]'
            if(a1 && a2) {
            // 如果是对象继续判断(对象中有不相同直接返回false，否则进入下一次循环)
                if(this.isObjectEqual(obj1[attr], obj2[attr])){
                    if(Object.keys(obj1)[Object.keys(obj1).length-1] === attr){
                        return true
                    }
                }else{
                    return false
                }
                
            } else if(arr1){
            // 如果是数组 判断
                if(obj1[attr].toString() != obj2[attr].toString()){
                    return false
            }
            } else if(obj1[attr] !== obj2[attr]) {
            // 不是对象的就判断数值是否相等
                return false
            }
        }
        return true
    }
```
==new Object()与Object.create()区别==

1. {}等同于new Object()，有原型；
2. Object.create()可以定义原型，Object.create(null)表示没有原型

==判断对象为空对象==

```
//第一种
var data = {};
var b = (JSON.stringify(data) == "{}");
alert(b);//true
//第二种for in 循环判断
var obj = {};
var b = function() {
for(var key in obj) {
	return false;
}
	return true;
}
alert(b());//true
//使用ES6的Object.keys()方法
var data = {};
var arr = Object.keys(data);
alert(arr.length == 0);//true
```



### 5.6 基本包装类型

> 为了便于操作基本类型值，提供了三个特殊的引用类型：Boolean、Number、String,这些类型与本章介绍的其他引用类型相似，但同时也具有与各自的基本类型相应的特殊行为；

> 引用类型与基本包装类型的主要区别是对象的生命周期;

> 对基本包装类型的实例调用typeof会返回"object"，而且所有基本包装类型的对象都会被转换 为布尔值 true。
#### 5.6.1 Boolean类型
> 基本类型与引用类型的布尔值还有两个区别。首先，typeof 操作符对基本类型返回"boolean"， 而对引用类型返回"object"。其次，由于 Boolean 对象是 Boolean 类型的实例，所以使用 instanceof 操作符测试 Boolean 对象会返回 true，而测试基本类型的布尔值则返回 false。
#### 5.6.2 Number类型

1. toFixed()方法会按照指定的小数位返回数值的字符串表示,能够自动舍入
2. toExponential()，该方法返回以指数表示法(也称e表示法),接收一个参数，指定输出结果中小数位数；
3. toPrecision()方法可能会返回固定大小（fixed）格式，也可能返回指数（exponential）格式；具体规则是看哪种格式最合适。这个方法接收一个参数，即表示数值的所有数字的位数（不包括指数部分)
#### 5.6.3 String类型
1. charAt():接受一个参数：基于零的字符位置，返回指定位置的字符；
2. charCodeAt():接受一个参数：基于零的字符位置，返回指定位置的字符的编码
3. concat():用于将一个或多个字符串拼接起来，返回拼接得到的新字符串；
4. slice()，substring():第一个参数子字符串的开始位置，第二个参数是子字符串做后一个字符后面的位置
5. substr():第一个参数子字符串的开始位置，第二个参数是子字符串的长度
6. indexOf():从字符串的开头向后查找子字符串的位置，若存在返回所在位置，若不存在返回-1，第一个参数是要查找的字符串，第二个字符串可以指定查找位置
7. lastIndexOf():从字符串的末尾向前查找子字符串的位置，若存在返回所在位置，若不存在返回-1，第一个参数是要查找的字符串，第二个字符串可以指定查找位置
8. trim():去除空格//this.replace(/^\s+/,'').replace(/\s+$/,'')
9. toLowerCase()、toLocaleLowerCase()、toUpperCase()、toLocaleUpperCase()
10. split():这个方法可以基于指定的分隔符将一个字符串分割成多个子字符串，并将结果放在一个数组中。分隔符可以是字符串，也可以是一个RegExp对象（这个方法不会将字符串看成正则表达式）。split()方法可以接受可选的第二个参数，用于指定数组的大小，以便确保返回的数组不会超过既定大小。
11. localeCompare()，这个方法比较两个字符串，并返回下列值中的一个：如果字符串在字母表中应该排在字符串参数之前，则返回一个负数（大多数情况下是-1，具体的值要视实现而定）；如果字符串等于字符串参数，则返回0；如果字符串在字母表中应该排在字符串参数之后，则返回一个正数（大多数情况下是 1，具体的值同样要视实现而定）。
12. formCharCode():这个方法的任务是接收一或多个字符编码，然后将它们转换成一个字符串;

```
var stringValue = "yellow"; 
stringValue.localeCompare("brick");//1
```
### 5.7 单体内置对象
#### 5.7.1 Global对象
1. encodeURI()不会对本身属于URI的特殊字符进行编码，例如冒号、正斜杠、问号和井字号,只把空格替换成%20；而encodeURIComponent()则会对它发现的任何非标准字符进行编码(替换所有非字母数字字符)；
2. decodeURIComponent()。其中，decodeURI()只能对使用encodeURI()替换的字符进行解码；decodeURIComponent()能够解码使用encodeURIComponent()编码的所有字符，即它可以解码任何特殊字符的编码。
3. eval():像是一个解析器，只接受一个参数

#### 5.7.2 Math对象
1. min()和 max()方法用于确定一组数值中的最小值和最大值。这两个方法都可以接收任意多个数值参数
```
Math.max(3, 54, 32, 16); //54
Math.min(3, 54, 32, 16); //3
var values = [1, 2, 3, 4, 5, 6, 7, 8];
Math.max.apply(Math, values);//8
```
2. Math.ceil()执行向上舍入，即它总是将数值向上舍入为最接近的整数、Math.floor()执行向下舍入，即它总是将数值向下舍入为最接近的整数、Math.round()执行标准舍入，即它总是将数值四舍五入为最接近的整数、Math.random()方法返回大于等于 0 小于 1 的一个随机数。

### 5.8 小结
1. 引用类型与传统面向对象程序设计中的类相似，但实现不同；
2. Object 是一个基础类型，其他所有类型都从 Object 继承了基本的行为；
3. Array 类型是一组值的有序列表，同时还提供了操作和转换这些值的功能；
4. Date 类型提供了有关日期和时间的信息，包括当前日期和时间以及相关的计算功能；
5. RegExp 类型是 ECMAScript支持正则表达式的一个接口，提供了最基本的和一些高级的正则表达式功能。

> 函数实际上是 Function 类型的实例，因此函数也是对象；而这一点正是 JavaScript 最有特色的地方。由于函数是对象，所以函数也拥有方法，可以用来增强其行为。 因为有了基本包装类型，所以JavaScript中的基本类型值可以被当作对象来访问。三种基本包装类 型分别是：Boolean、Number 和 String。以下是它们共同的特征:

1. 每个包装类型都映射到同名的基本类型;
2. 在读取模式下访问基本类型值时，就会创建对应的基本包装类型的一个对象，从而方便了数据操作；
3. 操作基本类型值的语句一经执行完毕，就会立即销毁新创建的包装对象。

> 在所有代码执行之前，作用域中就已经存在两个内置对象：Global 和 Math。在大多数 ECMAScript 实现中都不能直接访问 Global 对象；不过，Web 浏览器实现了承担该角色的 window 对象。全局变量和函数都是Global对象的属性。Math对象提供了很多属性和方法，用于辅助完成复杂的数学计算任务。

## 第六章 面向对象的程序设计
> 可以把对象想象成散列表，就是一组名值对，其中值可以是数据或函数
### 6.1 理解对象
#### 6.1.1 属性类型
> 特性是内部特征，需要放在两对方括号中，[[]]

1. **数据属性**:数据属性包含一个数据值的位置，在这个位置可以读取和写入值，数据属性有4个描述其行为的特性:
    1. **[[Configurable]]**:能否通过delete删除属性从而重新定义属性、能否修改属性的特性、能否将属性修改为访问器属性，默认为true；
    2. **[[Enumerble]]**:能否通过for-in循环返回属性，默认值为true；
    3. **[[Writable]]**：能否修改属性的值，默认值为 true；
    4. **[[Value]]**:包含属性的数据值，读与写都在这个位置，默认值为undefined

> 要**修改属性默认的特性**,必须使用Object.defineProperty()方法，三个参数:属性所在对象，属性名字，描述符对象，在描述符对象中一旦把属性设置为不可配置，就不能再把它变回可配置了，除了writable

```
var person = {}; 
Object.defineProperty(person, "name", { writable: false, value: "Nicholas" });
alert(person.name);
```
2. **访问器属性**：不包含数据值，包含一对儿getter和setter函数，访问器属性有如下4个特性：   
    1. **[[Configurable]]**:能否通过delete删除属性从而重新定义属性、能否修改属性的特性、能否将属性修改为访问器属性，默认为true；
    2. **[[Enumerble]]**:能否通过for-in循环返回属性，默认值为true；
    3. **[[Get]]**:在读取属性时调用的函数，默认值为undefined；
    4. **[[Set]]**:在写入属性时调用的函数，默认值为undefined；
> 访问器属性不能直接定义，必须使用Object.defineProperty(),getter与setter不一定同时指定
```
var book = { _year: 2004, edition: 1 }; 
Object.defineProperty(book, "year", { 
    get: function(){ 
        return this._year; 
    }, 
    set: function(newValue){
        if (newValue > 2004) { 
            this._year = newValue; 
            this.edition += newValue - 2004; 
        }
    } 
});
book.year = 2005;
alert(book.edition); //2
```
#### 6.1.2 定义多个属性
> 定义多个属性，Object.defineProperties(),接收两个对象参数：第一个对象是要添加和修改其属性的对象，第二个对象的属性与第一个对象中要添加或修改的属性一一对应。

```
var book = {};
Object.defineProperties(book,{num:{value:2000},edition:{value:1}});
book; //{num: 2000, edition: 1}
```
#### 6.1.3 读取属性的特性
> 使用Object.getOwnPropertyDescriptor()方法，接收两个参数：属性所在的对象和要读取其描述符的属性名称，返回值是一个对象；

```
var book = {};
Object.defineProperties(book,{num:{value:2000},edition:{value:1}});
Object.getOwnPropertyDescriptor(book,'num').value //2000
```
### 6.2 创建对象
> 使用Object构造函数或对象字面量都可以创建单个对象，但是这些方式有明显的缺点：使用同一个接口创建很多对象，会产生大量的重复代码，为解决这个问题，开始使用工厂模式的一种变体
#### 6.2.1 工厂模式

```
function createPerson(name, age, job){ 
    var o = new Object(); 
    o.name = name; 
    o.age = age; 
    o.job = job; 
    o.sayName = function(){ 
        alert(this.name); 
    }; 
    return o; 
} 
var person1 = createPerson("Nicholas", 29, "Software Engineer"); 
var person2 = createPerson("Greg", 27, "Doctor");
```
> 工厂模式虽然解决了创建多个相似对象的问题，但是没有解决对象识别的问题
#### 6.2.2 构建函数模式

```
function Person(name, age, job){ 
    this.name = name; 
    this.age = age; 
    this.job = job; 
    this.sayName = function(){ 
        alert(this.name); 
    }; 
} 
var person1 = new Person("Nicholas", 29, "Software Engineer"); 
var person2 = new Person("Greg", 27, "Doctor");
```
> 实例中有constructor(构造函数)属性，该属性指向Person

1. 将构造函数当作函数

> 构造函数与其他函数的唯一区别，就在于调用它们的方式不同。不过，构造函数毕竟也是函数，不存在定义构造函数的特殊语法。任何函数，只要通过new操作符来调用，那它就可以作为构造函数；而任何函数，如果不通过new操作符来调用，那它跟普通函数也不会有什么两样。

2. 构造函数的问题

> 构造函数中每个方法都是在每一个实例上重新创建一遍，以这种方式创建函数，会导致不同的作用域和标识符解析，解决方法如下：

```javascript
function Person(name, age, job){ 
    this.name = name; 
    this.age = age; 
    this.job = job;
    this.sayName = sayName; 
} 
function sayName(){ 
    alert(this.name); 
} 
var person1 = new Person("Nicholas", 29, "Software Engineer"); 
var person2 = new Person("Greg", 27, "Doctor"); 
```
> 这样修改后也有问题：在全局作用域中定义的函数实际上只能被某个对象调用，这让全局作用域有点名不副实。而更让人无法接受的是：如果对象需要定义很多方法，那么就要定义很多个全局函数，于是我们这个自定义的引用类型就丝毫没有封装性可言了。

#### 6.2.3 原型模式
> prototype 就是通过调用构造函数而创建的那个对象实例的原型对象。使用原型对象的好处是可以 让所有对象实例共享它所包含的属性和方法。换句话说，不必在构造函数中定义对象实例的信息;

```
function Person(){
    
} 
Person.prototype.name = "Nicholas"; 
Person.prototype.age = 29;
Person.prototype.job = "Software Engineer"; 
Person.prototype.sayName = function(){ 
    alert(this.name); 
}; 
var person1 = new Person(); 
person1.sayName(); //"Nicholas"
var person2 = new Person();
person2.sayName(); //"Nicholas" 
alert(person1.sayName == person2.sayName); //true
```
1. 理解原型对象

> 无论什么时候，只要创建了一个新函数，就会根据一组特定的规则为该函数创建一个prototype属性，这个属性指向函数的原型对象。在默认情况下，所有原型对象都会自动获得一个constructor （构造函数）属性，这个属性包含一个指向prototype属性所在函数的指针。
> ![构造函数、原型对象、实例之间的关系](/Users/naebunsakai/study/有道云笔记图片/prototype.png)
>
> 

> 虽然在所有实现中都无法访问到[[Prototype]]，但可以通过isPrototypeOf()方法来确定对象之间是否存在这种关系;ECMAScript5增加了一个新方法，叫Object.getPrototypeOf()，在所有支持的实现中，这个方法返回[[Prototype]]的值。

```
alert(Person.prototype.isPrototypeOf(person1));//true
alert(Object.getPrototypeOf(person1).name);
```
> 当为对象实例添加一个属性时，这个属性就会屏蔽原型对象中保存的同名属性；换句话说，添加这个属性只会阻止我们访问原型中的那个属性，但不会修改那个属性。即使将这个属性设置为 null，也只会在实例中设置这个属性，而不会恢复其指向原型的连接。不过，使用delete操作符则可以完全删除实例属性，从而让我们能够重新访问原型中的属性;

> 使用hasOwnProperty()方法可以检测一个属性是存在于实例中，还是存在于原型中。这个方法（不要忘了它是从 Object继承来的）只在给定属性存在于对象实例中时，才会返回true。

```
alert(person1.hasOwnProperty("name"));
```
2. 原型与in操作符

> in操作符会在通过对象能够访问给定属性时返回true，无论该属性存在于实例中还是原型中,同时使用 hasOwnProperty()方法和in操作符，就可以确定该属性到底是存在于对象中，还是存在于原型中，如下所示。 

```
alert("name" in person1);
function hasPrototypeProperty(object, name){ 
    return !object.hasOwnProperty(name) && (name in object); 
}
```
> 在使用for-in循环时，返回的是所有能够通过对象访问的、可枚举的（enumerated）属性，其中既包括存在于实例中的属性，也包括存在于原型中的属性。屏蔽了原型中不可枚举属性

> 要取得对象上所有可枚举的实例属性，可以使用ECMAScript5的Object.keys()方法。这个方法 接收一个对象作为参数，返回一个包含所有可枚举属性的字符串数组。

```
function Person(){ } 
Person.prototype.name = "Nicholas"; 
Person.prototype.age = 29;
Person.prototype.job = "Software Engineer"; 
Person.prototype.sayName = function(){ alert(this.name); }; 
var keys = Object.keys(Person.prototype); 
alert(keys); //"name,age,job,sayName"
```
> 如果你想要得到所有实例属性，无论它是否可枚举，都可以使用Object.getOwnPropertyNames() 方法;

```
var keys = Object.getOwnPropertyNames(Person.prototype); 
alert(keys); //"constructor,name,age,job,sayName"
```
3. 更简单的原型语法

```
function Person(){ } 
Person.prototype = { 
    name : "Nicholas", 
    age : 29, 
    job : "Software Engineer", 
    sayName : function () { alert(this.name); 
    } 
};
Object.defineProperty(Person.prototype, "constructor", { 
    enumerable: false, 
    value: Person 
});
```
4. 原型的动态性

> 由于在原型中查找值的过程是一次搜索，因此我们对原型对象所做的任何修改都能够立即从实例上反映出来——即使是先创建了实例后修改原型也照样如此。

```
function Person(){ } 
var friend = new Person();
Person.prototype = { 
    constructor: Person, 
    name : "Nicholas", 
    age : 29, job : "Software Engineer", 
    sayName : function () { alert(this.name); 
    }
}; 
friend.sayName(); //error
```
> 上述代码先创建了实例，后改写原型对象，切断了实例对象与原型对象之间的联系

5. 原生对象的原型 
6. 原型对象的问题

> 缺点：省略给构造函数传递参数的环节，结果所有实例在默认情况下都将取得相同的属性值；原型中所有属性是被很多实例共享的，这种共享对于引用类型来说，问题是非常突出的

#### 6.2.4 组合使用构造函数模式和原型模式

> 构造函数模式用于定义实例属性，而原型模式用于定义方法和共享的属性。结果，每个实例都会有自己的一份实例属性的副本，但同时又共享着对方法的引用，最大限度地节省了内存。另外，这种混成模式还支持向构造函数传递参

```
function Person(name, age, job){ 
    this.name = name; 
    this.age = age; 
    this.job = job; 
    this.friends = ["Shelby", "Court"];
} 
Person.prototype = { 
    constructor : Person, 
    sayName : function(){ alert(this.name); } 
} 
var person1 = new Person("Nicholas", 29, "Software Engineer"); 
var person2 = new Person("Greg", 27, "Doctor"); 
person1.friends.push("Van"); 
alert(person1.friends); //"Shelby,Count,Van" 
alert(person2.friends); //"Shelby,Count" 
alert(person1.friends === person2.friends); //false 
alert(person1.sayName === person2.sayName);//true
```
#### 6.2.5 动态原型模式
#### 6.2.6 寄生构造函数模式
#### 6.2.7 稳妥构造函数模式
### 6.3 继承(面试中常问，可与es6中class一起学习)
#### 6.3.1 原型链继承
- 基本思想

  - 利用原型让一个引用类型继承另一个引用类型的属性和方法；实际上是构造函数的实例指向的原型对象是另一个构造函数的实例

  ```javascript
  function SuperType(){ 
      this.property = true;
  }
  SuperType.prototype.getSuperValue = function(){ 
      return this.property;
  }; 
  function SubType(){ 
      this.subproperty = false;
  } 
  //继承了 SuperType 
  SubType.prototype = new SuperType(); 
  SubType.prototype.getSubValue = function (){ 
      return this.subproperty; 
  }; 
  var instance = new SubType(); 
  alert(instance.getSuperValue());//true
  
  alert(instance instanceof Object);//true
  alert(SubType.prototype.isPrototypeOf(instance));//true
  ```

  默认的原型

> ![原型继承图](/Users/naebunsakai/study/有道云笔记图片/prototypeExtend.png)
- 原型链-优点
  
- 继承了父类的模板，又继承了父类的原型对象
  
- 原型链-缺点
  - 父类构造函数中包含引用类型，所有实例都有更改的权利，其中一个实例对引用类型的操作在另外一个实例中也可以体现出来；

    ```javascript
    function SuperType(){ 
      this.colors = ["red", "blue", "green"];
    }
    function SubType(){ 
    } 
    //原型继承
    SubType.prototype = new SuperType(); 
    var instance1 = new SubType(); 
    instance1.colors.push("black"); 
    alert(instance1.colors); //"red,blue,green,black" 
    var instance2 = new SubType(); 
    alert(instance2.colors); //"red,blue,green,black"
    ```

  - 在创建子类的实例时，不能向超类型的构造函数中传递参数，或者说是，没办法在不影响所有对象实例的情况下，向父类的构造函数传递参数

    > 由于会存在以上问题，所以实践中很少单独使用原型链继承，以上两个问题可以用下面的继承方式解决

  - 给原型添加方法的代码一定要放在替换原型的语句之后，否则添加的方法会被覆盖掉;在通过原型链实现继承时，不能使用对象字面量创建原型方法,因为这样做就会重写原型链;

    ```javascript
    function SuperType(){ 
        this.property = true; 
    } 
    SuperType.prototype.getSuperValue = function(){ 
        return this.property; 
    };
    function SubType(){ 
        this.subproperty = false;
    } 
    //继承了 SuperType 
    SubType.prototype = new SuperType(); 
    //添加新方法 
    SubType.prototype.getSubValue = function (){ 
        return this.subproperty; 
    };
    //重写超类型中的方法 
    SubType.prototype.getSuperValue = function (){ 
        return false;
    }; 
    var instance = new SubType(); 
    alert(instance.getSuperValue()); //false
    
    
    //使用了对象字面量,完全形成了一个新的对象
    SubType.prototype = {
      get:(new SuperType()).getSuperValue
    }; 
    ```

  - 无法实现多继承

#### 6.3.2 借用构造函数(伪造对象或经典继承)

- 基本思想

  - 在子类型构造函数的内部调用超类型构造函数。别忘了，函数只不过是在特定环境中执行代码的对象， 因此通过使用apply()和call()，bind()方法也可以在（将来）新创建的对象上执行构造函数

    ```javascript
    function SuperType(){ 
          this.colors = ["red", "blue", "green"]; 
      } 
      function SubType(){ 
          //继承了 SuperType 
          SuperType.call(this); 
      } 
      var instance1 = new SubType(); 
      instance1.colors.push("black"); 
      alert(instance1.colors); //"red,blue,green,black" 
      var instance2 = new SubType(); 
      alert(instance2.colors); //"red,blue,green"
    ```

    ```javascript
    //传递参数
    function SuperType(name){ 
        this.name = name; 
    } 
    function SubType(){ 
        //继承了 SuperType，同时还传递了参数 
        SuperType.call(this, "Nicholas"); 
        //实例属性 
        this.age = 29; 
    } 
    var instance = new SubType(); 
    alert(instance.name); //"Nicholas";
    alert(instance.age); //29
    ```

- 借用构造函数-优点

  - 解决了原型链继承中子类实例共享父类引用对象的问题，实现多继承，创建子类实例时，可以向父类传递参数

- 借用构造函数-缺点

  - 实例(instance)并不是父类的实例，只是子类的实例
  - **只能**继承父类的实例属性和方法，**不能**继承原型属性/方法
  - **无法实现函数复用**，每个子类都有父类实例函数的副本，影响性能

> 由于存在以上问题，所以借用构造函数的技术很少单独使用

#### 6.3.3 组合继承(伪经典继承)

- 基本思想

  - 使用原型链实现对原型属性和方法的继承，而通过借用构造函数来实现对实例属性的继承。这样，既通过在原型上定义方法实现了函数复用，又能够保证每个实例都有它自己的属性。
  - 组合继承避免了原型链继承和借用构造函数继承的缺陷，融合了他们的优点，成为了最长使用的继承模式

  ```javascript
  function SuperType(name){ 
      this.name = name; 
      this.colors = ["red", "blue", "green"]; 
  } 
  SuperType.prototype.sayName = function(){ 
      alert(this.name);
  }; 
  function SubType(name, age){ 
      //继承属性 
    	SuperType.call(this, name); 
      this.age = age; 
  } 
  //继承方法 
  SubType.prototype = new SuperType(); 
  SubType.prototype.constructor = SubType; 
  SubType.prototype.sayAge = function(){
      alert(this.age); 
  }; 
  var instance1 = new SubType("Nicholas", 29); 
  instance1.colors.push("black"); 
  alert(instance1.colors); //"red,blue,green,black" 
  instance1.sayName(); //"Nicholas"; 
  instance1.sayAge(); //29 
  var instance2 = new SubType("Greg", 27); 
  alert(instance2.colors); //"red,blue,green" 
  instance2.sayName(); //"Greg"; 
  instance2.sayAge(); //27
  ```

- 组合继承-缺点

  - 调用了两次父类构造函数，生成了**两份实例**（子类实例将子类原型上的那份屏蔽了）

#### 6.3.4 原型式继承

- 基本思想
  - 将子类的原型设置为父类的原型

- 创建一个纯洁的对象，连原型都没有的对象
- 创建方式Object.create()

```javascript
// 父类
function SuperType (name) {
  this.colors = ["red", "blue", "green"];
  this.name = name; // 父类属性
}
SuperType.prototype.sayName = function () { // 父类原型方法
  return this.name;
};

/** 第一步 */
// 子类，通过 call 继承父类的实例属性和方法，不能继承原型属性/方法
function SubType (name, subName) {
  SuperType.call(this, name); // 调用 SuperType 的构造函数，并向其传参 
  this.subName = subName;
}

/** 第二步 */
// 解决 call 无法继承父类原型属性/方法的问题
// Object.create 方法接受传入一个作为新创建对象的原型的对象，创建一个拥有指定原型和若干个指定属性的对象
// 通过这种方法指定的任何属性都会覆盖原型对象上的同名属性
SubType.prototype = Object.create(SuperType.prototype, { 
  constructor: { // 注意指定 SubType.prototype.constructor = SubType
    value: SubType,
    enumerable: false,
    writable: true,
    configurable: true
  },
  run : { 
    value: function(){ // override
      SuperType.prototype.run.apply(this, arguments); 
       // call super
       // ...
    },
    enumerable: true,
    configurable: true, 
    writable: true
  }
}) 

/** 第三步 */
// 最后：解决 SubType.prototype.constructor === SuperType 的问题
// 这里，在上一步已经指定，这里不需要再操作
// SubType.prototype.constructor = SubType;

var instance = new SubType('An', 'sistenAn')
```

#### 6.3.5 寄生式继承
#### 6.3.6 寄生组合式继承

- 基本思想

  - 在组合继承中，调用了两次父类构造函数，这里  **通过通过寄生方式，砍掉父类的实例属性，这样，在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，避免的组合继承的缺点**
  - 借用 **构造函数** 继承 **属性** ，通过 **原型链的混成形式** 来继承 **方法**

  ```javascript
  / 父类
  function SuperType (name) {
    this.colors = ["red", "blue", "green"];
    this.name = name; // 父类属性
  }
  SuperType.prototype.sayName = function () { // 父类原型方法
    return this.name;
  };
  
  // 子类
  function SubType (name, subName) {
    // 调用 SuperType 构造函数
    SuperType.call(this, name); // ----第二次调用 SuperType，继承实例属性----
    this.subName = subName;
  };
  
  // ----第一次调用 SuperType，继承原型属性----
  SubType.prototype = Object.create(SuperType.prototype)
  
  SubType.prototype.constructor = SubType; // 注意：增强对象
  
  let instance = new SubType('An', 'sisterAn')
  ```

- 寄生组合式继承-优点
  - 只调用一次 `SuperType` 构造函数，只创建一份父类属性
  - 原型链保持不变
  - 能够正常使用 `instanceof` 与 `isPrototypeOf`

### 设计模式

### 6.4 小结

### 6.5 题目

1. ==判断变量是不是数组:arr instanceOf Array;<br />
衍生题目instanceOf原理参考《6.3.1 原型链》的实例与构造方法的图，实际上是比较实例的隐式原型与构造方法的显示原型进行比较==
2. ==class的原型本质:原型与原型链的图《6.3.1 原型链》、属性和方法的执行规则==
3. ==手写JQuery展示插件和扩展性==

```javascript
class Jquery {
    constructor(dom){
        const result = document.querySelectorAll(dom)
        let length = result.length
        for(let i = 0;i<length;i++){
            this[i] = result[i]
        }
        this.length = length
    }
    get(index){
        return this[index]
    }
    each(fn){
        for(let i = 0;i<this.length;i++){
            const elem = this[i]
            fn(elem)
        }
    }
    on(type,fn){
        return this.each((elem)=>{
            elem.addEventListener(type,fn,false)
        })
    }
    //扩展其他api
}
//插件
Jquery.prototype.add = function(){}

//复习，造轮子
class MyJquery extends Jquery{
    constructor(dom){
        super(dom)
    }
    //扩展自己的方法
}
```

![image-20200423110941111](/Users/naebunsakai/Library/Application Support/typora-user-images/image-20200423110941111.png)

## 第七章 函数表达式

> 函数声明、函数声明提升(函数声明可以放在函数调用的后面)、函数表达式(函数表达式在使用前必须赋值)
### 7.1 递归

```
function factorial(num){ 
    if (num <= 1){ 
        return 1; 
    } else { 
        return num * factorial(num-1); 
    }
}
```
> 设置后var anotherFactorial = factorial;factorial = null;递归会报错，改进方法

```
function factorial(num){ 
    if (num <= 1){ 
        return 1; 
    } else { 
        return num * arguments.callee(num-1); 
    }
}
```
> arguments.callee是一个指向正在执行的函数的指针，因此可以用它来实现对函数,严格模式arguments.callee会报错，改进方法

```
var factorial = (function f(num){
    if (num <= 1){ 
        return 1; 
    } else { 
        return num * f(num-1); 
    } 
});
```
> 使用命名函数表达式后，即便把函数值赋值给另一个变量，函数的名字f仍然有效，递归调用照样完成，这种方式在严格模式和非严格模式都可以行的通

#### 7.1.1 题目

> 递归与循环有一定相似程度，假如不使用类似for，while循环控制语句和js本身自带方法（如：forEach）的情况下，实现将一个空数组[]赋值成[0,2,4,6,8,10,...,100]，范围0-100便可。

```
 function arrValue(min, max, arr) {
      if (typeof min !== "number" || min < 0) {
      	return false
      }
      if (typeof max !== "number" || max > 100) {
      	return false
      }
      if (arr.constructor !== Array) {
      	return false
      }
      if (min % 2 === 0) {
      	arr.push(min)
      }
      if (min == max) {
      	return arr
      }
      return arrValue(++min, max, arr)
 }
 
console.log(arrValue(0,100,[]));
```



### 7.2 闭包

> 在一个函数执行完毕后，函数作用域中的变量会进行销毁，使用闭包后,作用域创建的活动对象不会在内存中销毁,会一直存在，但是执行的函数回从内存中清掉，所在闭包可能存在内存泄漏；

> 函数作用域链：每个函数在被调用的时候都会创建一个活动对象，作用域链指向活动对象，函数调用结束后作用域链对活动对象的指向移除，在闭包中，父函数执行完毕后，作用域链对活动对象的指向移除，但是闭包的作用域链中也有对活动对象的指向，因此该活动对象不会被销毁，因为该活动对象还有被引用

> 闭包是有权访问**<font color='red'>另一个函数作用域</font>**中的变量的函数，创建闭包的常用方式就是在一个函数内部创建另一个函数；作用域链本质上是一个指向变量对象的指针列表，它只引用但不实际包含变量对象
#### 7.2.1 闭包与变量
> 闭包只能获取函数中任意变量的最后一个值，闭包所保存的是整个变量对象，而不是某个特殊的变量；

```
function createFunctions(){ 
    var result = new Array(); 
    for (var i=0; i < 10; i++){ 
        result[i] = function(){ 
            return i; 
        }; 
    } 
    return result; 
}
```
> 从作用域链的角度去看结果，在createFunctions执行返回结果后，result每一项都是一个函数，在这个函数中寻求变量i的值，在包含函数的活动对象中找到变量i的值，此时变量i的值是10，result中每一项的变量i都是10；

```
function createFunctions(){ 
    var result = new Array(); 
    for (var i=0; i < 10; i++){ 
        result[i] = function(num){ 
            return function(){ 
                return num; 
            }; 
        }(i); 
    } 
    return result; 
}
```
> 依旧从作用域链的角度看结果，在createFunctions执行返回结果后，result每一项都是一个函数，在执行函数得出结果时，在作用域链新增了一层匿名函数的作用域的活动对象，在这个活动对象中找到函数要返回的结果，所以现在不需要在createFunctions活动对象中寻找结果，因此这个数组中函数返回的每一项都是索引值项；

> 闭包中的变量存储在堆空间中，闭包会创建一个closure([ˈkloʊʒər] )对象存放变量

> 闭包作用：1、读取函数内部的变量
> 2、让这些变量的值始终保持在内存中。不会再f1调用后被自动清除。
> 3、方便调用上下文的局部变量。利于代码封装。
> 原因：f1是f2的父函数，f2被赋给了一个全局变量，f2始终存在内存中，f2的存在依赖f1，因此f1也始终存在内存中，不会在调用结束后，被垃圾回收机制回收。
>
> https://blog.csdn.net/qq_21132509/article/details/80694517

#### 7.2.2 关于this对象

> this对象是在运行时基于函数的执行环境绑定的；

> 每个函数在被调用时都会自动取得两个特殊变量：this、argunment，内部函数在搜索这两个变量时，只会搜索到其活动对象为止

> 如果想访问作用域中的this、arguments对象，必须将对该对象的引用保存到另一个闭包能够访问的变量中。
#### 7.2.3 内存泄漏

- 使用闭包后，记得将闭包函数置为null，这样可以释放闭包作用域链中的内存

#### 7.2.4 闭包使用场景

- <font color="red">闭包的用途</font>
  - 读取函数内部的变量
  - 让这些变量的值始终保持在内存中。不会在f1调用后被自动清除。
  - 方便调用上下文的局部变量。利于代码封装。
    原因：f1是f2的父函数，f2被赋给了一个全局变量，f2始终存在内存中，f2的存在依赖f1，因此f1也始终存在内存中，不会在调用结束后，被垃圾回收机制回收。

- <font color="red">闭包的使用场景</font>

  - setTimeout中为第一个函数传参

    ```javascript
    setTimeout(function(){
      console.log('原生')
    },0);
    function func(value){
      return function(){
        console.log(value)
      }
    }
    setTimeout(func("闭包"),0)
    ```

  - 回调

    ```javascript
    function changeSize(size){
      return function(){
        document.body.style.fontSize = size + 'px';
      };
    }
    const size12 =  changeSize(12)
    const size14 =  changeSize(14)
    const size16 =  changeSize(16)
    
    document.getElementById('size-12').onclick = size12;
    document.getElementById('size-14').onclick = size14;
    document.getElementById('size-16').onclick = size16;
    ```

    

  - 封装变量

    ```javascript
    //用闭包定义能访问私有函数和私有变量的公有函数。
    var counter = (function(){
      var privateCounter = 0;	//私有变量
      function change(val){
        privateCounter += val;
      }
      return {
        increment:function(){	//三个闭包共享一个词法环境
          change(1);
        },
        decrement:function(){
          change(-1);
        },
        value:function(){
          return privateCounter;
        }
      };
    })();
    
    console.log(counter.value());//0
    counter.increment();
    counter.increment();//2
    ```

    

  - 为节点循环绑定click事件(块级作用域概念)

    ```javascript
    /**
    	 * 解决方法1     通过函数工厂，则函数为每一个回调都创建一个新的词法环境
    	 */
    	function showContent(content){
    		document.getElementById('info').innerHTML = content;
    	};
    
    	function callBack(content){
    		return function(){
    			showContent(content)
    		}
    	};
    
    	function setContent(){
    		var infoArr = [
    			{'id':'email','content':'your email address'},
    			{'id':'name','content':'your name'},
    			{'id':'age','content':'your age'}
    		];
    		for (var i = 0; i < infoArr.length; i++) {
    			var item = infoArr[i];
    			document.getElementById(item.id).onfocus = callBack(item.content)
    		}
    	}
    	setContent()
    
    	/**
    	 * 解决方法2 		绑定事件放在立即执行函数中
    	 */
    	function showContent(content){
    		document.getElementById('info').innerHTML = content;
    	};
    
    	function setContent(){
    		var infoArr = [
    			{'id':'email','content':'your email address'},
    			{'id':'name','content':'your name'},
    			{'id':'age','content':'your age'}
    		];
    		for (var i = 0; i < infoArr.length; i++) {
    			(function(){
    				var item = infoArr[i];
    				document.getElementById(item.id).onfocus = function(){
    					showContent(item.content)
    				}
    			})()//放立即执行函数，立即绑定，用每次的值绑定到事件上，而不是循环结束的值
    		}
    	}
    	setContent()
    
    	/**
    	 * 解决方案3		用ES6声明，避免声明提前，作用域只在当前块内
    	 */
    	function showContent(content){
    		document.getElementById('info').innerHTML = content;
    	};
    
    	function setContent(){
    		var infoArr = [
    			{'id':'email','content':'your email address'},
    			{'id':'name','content':'your name'},
    			{'id':'age','content':'your age'}
    		];
    		for (var i = 0; i < infoArr.length; i++) {
    			let item = infoArr[i]; 		//限制作用域只在当前块内
    			document.getElementById(item.id).onfocus = function(){
    				showContent(item.content)
    			}
    		}
    	}
    	setContent()
    ```
    
  - 支付时只支付一次

    ```javascript
    const once = (fn) => {
      let done = false
      return function(){
        if(!done){
          done = true
          fn('支付')
        }
      }
    }
    const pay = once((msg)=>{
      console.log("msg",msg)
    })
    pay()
    pay()
    //只会打印一次'支付'，因为done变量没有被回收，第二次调用时done的值为true
    ```

  - 求员工工资：相同参数不需要反复传递

    ```javascript
    const makeSalary = (base) => {
      return function(performance){
        return base+performance
    	}
    }
    let salaryLevel1 = makeSalary(12000)
    let salaryLevel2 = makeSalary(15000)
    console.log("salaryLevel1",salaryLevel1(3000))
    console.log("salaryLevel1",salaryLevel1(5000))
    console.log("salaryLevel2",salaryLevel2(3000))
    console.log("salaryLevel2",salaryLevel2(5000))
    //在此闭包中不需要重复声明工资等级一、二的基本工资，只需要makeSalary(12000)一次就好，之后基本工资变量会在内存中一直存在，在调用salaryLevel时传不同的绩效则可以计算出不用的工资
    ```

    

    


  - 防抖与节流

    ```javascript
    //参考下面的防抖节流
    ```

    

### 7.3 模仿块级作用域

> 采用匿名立即调用函数创建块级作用域

```javascript
function outputNumbers(count){ 
    (function () { 
        for (var i=0; i < count; i++){ 
            alert(i); 
        } 
    })(); 
    alert(i); //导致一个错误！ 
}
```
### 7.4 私有变量
> 任何在函数中定义的变量，都可以认为是私有变量，私有变量包括函数的参数、局部变量和在函数内部定义的其他函数；

> 有权访问私有变量和私有函数的共有方法称为特权方法，创建特权方法的方式：
1. 构造函数中创建特权方法：

    ```javascript
    function MyObject(){    
        //私有变量和私有函数 
        var privateVariable = 10; 
        function privateFunction(){ 
            return false; 
        } 
        //特权方法 
        this.publicMethod = function (){
            privateVariable++; 
            return privateFunction(); 
        };
    }
    ```
2. 通过在私有作用域中定义私有变量或函数，同样也可以创建特权方法：
    ```javascript
    (function(){ 
        //私有变量和私有函数 
        var privateVariable = 10; 
        function privateFunction(){ 
            return false; 
        } 
        //构造函数,初始化未经声明的变量，总是会创建一个全局变量。
        MyObject = function(){ };
        //公有/特权方法 MyObject.prototype.publicMethod = function(){ 
            privateVariable++; 
            return privateFunction(); 
        };
    })();
    ```

#### 7.4.1 静态私有变量
#### 7.4.2 模块模式
#### 7.4.3 增强模块模式
#### 7.4.5 小结
1. 函数表达式不同于函数声明。函数声明要求有名字，但函数表达式不需要。没有名字的函数表 达式也叫做匿名函数；
2. 在无法确定如何引用函数的情况下，递归函数就会变得比较复杂；
3. 递归函数应该始终使用 arguments.callee 来递归地调用自身，不要使用函数名——函数名可 能会发生变化；
4. 在后台执行环境中，闭包的作用域链包含着它自己的作用域、包含函数的作用域和全局作用域；
5. 通常，函数的作用域及其所有变量都会在函数执行结束后被销毁；
6. 但是，当函数返回了一个闭包时，这个函数的作用域将会一直在内存中保存到闭包不存在为止；
7. 创建并立即调用一个函数，这样既可以执行其中的代码，又不会在内存中留下对该函数的引用；
8. 结果就是函数内部的所有变量都会被立即销毁——除非将某些变量赋值给了包含作用域（即外 部作用域）中的变量；
9. 即使 JavaScript 中没有正式的私有对象属性的概念，但可以使用闭包来实现公有方法，而通过公 有方法可以访问在包含作用域中定义的变量；
10. 有权访问私有变量的公有方法叫做特权方法；
11. 可以使用构造函数模式、原型模式来实现自定义类型的特权方法，也可以使用模块模式、增强 的模块模式来实现单例的特权方法；
12. JavaScript 中的函数表达式和闭包都是极其有用的特性，利用它们可以实现很多功能。不过，因为 创建闭包必须维护额外的作用域，所以过度使用它们可能会占用大量内存；

### 7.5 函数式编程

#### 7.5.1 函数是一等公民

#### 7.5.2 高阶函数

> 函数的参数是函数，或者函数的返回结果是函数，则此函数为高阶函数，例如数组的map，foreach的参数都是函数，所以他们都是高阶函数，使用函数作为参数可以使函数更加灵活；

- 抽像可以屏蔽细节，只关注目标与结果；
- 高阶函数用来抽象通用问题；

#### 7.5.3 纯函数

> 概念：相同的输入永远有相同的输出，而且没有任何可观察的副作用

- 函数式编程不会保留计算的中间结果，所以变量是不可变的(无状态的)
- 我们可以把函数的执行结果交给另一个函数去处理
- lodash纯函数库

纯函数的优点

- 纯函数可以缓存：由于相同的输入有相同的输出，所以可以将纯函数的结果进行缓存，减少函数的调用，提高性能；例子中，多次使用getAreaWithMemory但只打印出一次4，缓存结果使用了闭包的概念

  ![image-20210202202555729](/Users/naebunsakai/study/notes/imgs/image-20210202202555729.png)

- 可测试：纯函数让测试更方便，因为纯函数有输入输出

- 并行处理：纯函数不需要访问共享数据，只依赖于入参，所以在并行环境下可以随意的运行纯函数

#### 7.5.4 副作用

> 副作用让一个函数变得不纯，纯函数根据相同的输入返回相同的输出，如果函数依赖外部的状态就无法保证输出相同，就会带来副作用

副作用的来源：

- 配置文件
- 数据库
- 获取用户输入

所有的外部交互都有可能产生副作用，副作用使方法通用性下降，但是副作用不可能完全禁止，尽可能控制他们在可控的范围内

#### 7.5.5 柯里化

- 概念
  - 当一个函数有多个参数的时候先传递一部分参数调用它（这部分参数永远不变）
  - 然后返回一个新的函数接收剩余的参数，返回结果

- 简单示例

  ```javascript
  //本身写一个函数要传递两个参数min、age，此示例使用闭包达到了数据缓存的效果，通过设置min年龄，之后验证传入的年龄是否符合标准
  function checkAge(min){
    return function(age){
      return age >= min
    }
  }
  let checkAge18 = checkAge(18)
  console.log("checkAge18",checkAge18(22))
  console.log("checkAge18",checkAge18(23))
  console.log("checkAge18",checkAge18(17))
  //es6写法
  const checkAge = (min => (age=> age >= min))
  ```

- 通用柯里化方法

  - 函数有几个参数就是几元函数，通过柯里化会把多元函数转换成一元函数

  - lodash中提供了柯里化方法curry，实现原理如下

    - 功能：创建一个函数。该函数接收一个或多个func的参数，如果func所需的参数都被传递则执行func并返回执行结果，否则返回该函数并继续等待接收剩余的参数

    - 参数：需要柯里化的函数

    - 返回值：柯里化后的函数

      ![image-20210206121230971](/Users/naebunsakai/study/notes/imgs/image-20210206121230971.png)

- 总结

  - 柯里化可以让我们给一个函数传递较小的参数，得到一个已经记住了某些固定参数的函数
  - 这是一种对函数参数的缓存，利用闭包做到缓存
  - 让函数变得更加灵活，让函数的颗粒更小
  - 可以把多元函数转换成一元函数，可以组合使用函数产生强大的功能

#### 7.5.6 函数组合

> 使用纯函数和柯里化函数很容易写出洋葱代码(fn(a(b(value))))，使用函数组合可以避免出现洋葱代码

- 数据管道：将处理数据的管道变成一段段的小管道，而不是一条处理数据的长管道，这样出现问题时容易定位位置，中间结果不需要关注

- 如果一个函数要经过多个函数的处理才能得到最终值，这时候就可以把中间过程的函数合并成一个函数

- 函数就像是数据的管道，函数组合就是把这些管道连接起来，让数据穿过多个管道形成最终的结果

- 函数组合默认是从右到左执行

- lodash中已实现api：flowRight()

  ![image-20210206130831609](/Users/naebunsakai/study/notes/imgs/image-20210206130831609.png)

- 函数组合结合律：符合数学中的结合律

  ![image-20210206131420639](/Users/naebunsakai/study/notes/imgs/image-20210206131420639.png)

- 函数组合调试

  ![image-20210206132521445](/Users/naebunsakai/study/notes/imgs/image-20210206132521445.png)

### 7.6 函数调用方式

#### 函数调用-this指向window

```javascript
//第一种
function Person(name){
  this.name = name//函数调用，this指向window
}
Person('abc')//函数调用，name属性被挂在在window上
//第二种
function fn(){
  this.age = 18//函数调用，age属性被挂在在window上,this指向window
}
fn()
console.log('age',age)//18
//第三种
var age = 18
var p = {
  age:15,
  say:function(){
    console.log(this.age)
  }
}
var f1 = p.say
f1()//此时打印出18，因为是函数调用
```

#### 方法调用-this指向调用方法的变量

```javascript
//第一种
function Person(name){
  this.name = name
}
Person.prototype.say = function(){
  console.log("this",this)//方法调用-this指向调用方法的变量p1实例
}
const p1 = new Person('mxm')
p1.say()
//第二种
var age = 18
var p = {
  age:15,
  say:function(){
    console.log(this.age)
  }
}
p.say()//此时打印出15，因为是方法调用，this指向了调用方法的变量p
//第三种
var clear = function(){
  console.log(this.length)
}
var length = 50;
var tom = {c:clear,length:100}
tom.c()//此时打印出100，this指向tom
//第四种
var clear = function(){
  console.log(this.length)
}
var length = 50;
var tom = {c:clear}
tom.c()//此时打印出undefined,this指向tom,因为tom的原型链上无length属性，此属性在window上
```

#### 构造函数调用方式-指向构造函数的实例

```javascript
function Fn(name){
  this.name = name
}
var n = new Fn()//此时是构造函数的方式调用，所以this指向构造函数的实例n，n上有属性name
```

#### 上下文调用方式【call,bind,apply】- this指向调用传递的第一个参数

```javascript
function f1(){
  console.log(this)
}
f1.call([1,2,3])//打印出[1,2,3]
f1.call({age:18})//打印出{age:18}
f1.call(1)//打印出Number {1}
f1.call('abc')//String {"abc"}
f1.call(true)//Boolean {true}
f1.call(undefined)//打印出window
//call，apply,bind第一个参数的总结：
//如果是一个引用类型，则this指向该对象
//如果是null、undefined，则this指向window
//如果是数字，则this指向对应Number构造函数的实例 
//如果是字符串，则this指向对应String构造函数的实例
//如果是布尔值，则this指向对应Boolean构造函数的实例

bind的传参与call一样，但是他与call、apply不同的是，需要再执行一次
function f1(){
  console.log(this)
}
const _f1 = f1.bind({age:18})//此时改变f1的this指向，生成一个新的函数返回，此时f1函数并未执行
_f1()
```



### 7.7 题目

1. ==闭包:函数定义与执行不在一个作用于内==

2. ==自由变量(一个变量在当前作用域没有被定义，但是被使用了)的查找在函数定义的地方向上级作用于查找，不是函数执行的时候==
   
    ```
    //函数作为返回值
    function create(){
        const a = 200
        return function(){
            console.log(a)
        }
    }
    const fn = create()
    const a = 100
    fn()//200
    //函数作为参数传递
    function print(fn){
        const a = 100
        fn()
    }
    const a = 200
    function fn(){
        console.log(a)
    }
    print(fn)//200
    ```
    
3. <font color="red">this取值:是在函数执行时产生的，不是函数定义时</font>
   
    1. 函数直接执行:
       
        ```javascript
        funciton fn1(){console.log(this)}
        fn1()//window
        ```
    2. 绑定call,apply,bind
        ```
        funciton fn1(){console.log(this)}
        fn1.call({x:100})//{x:100}
        fn1.apply({x:100})//{x:100}
        const fn2 = fn1.bind({x:100})
        fn2()//{x:100}
        ```
    3. 对象
        ```javascript
        const zhangsan = {
            name:'张三',
            sayHi(){
                console.log(this);
            },
            wait(){
                setTimeout(function(){
                    console.log('setTimeout',this)//window
                })
                function a(){
                  console.log("a",this)//window
                }
                a();
            }
        };
        zhangsan.wait()
        const zhangsan = {
            name:'张三'，
            sayHi(){
                console.log(this)//this指当前对象
            }
            wait(){
                setTimeout(()=>{
                 console.log(this)//this指当前对象(箭头函数的this永远取上一级作用域的this)
                })
              	a = () => {
                  console.log("a",this)//this指当前对象(箭头函数的this永远取上一级作用域的this)
                }
                a();
            }
        }
        
        var length = 100;
        function f1(){
          console.log(this.length)
        }
        var obj={
          length:10,
          f2:function(f1){
            f1();
            arguments[0]()
            console.log(arguments[0])
          }
        }
        obj.f2(f1,1)//100,2
        //100这个，执行f1,前面没有调用者则是默认指向window，var length把100映射到window上了，所以window.length为100，2这个，this指向arguments了，
        ```
    4. 构造函数
        ```javascript
        class People(){
            constructor(name){
                this.name =  name
                this.age = 20
            }
            sayHi(){
                console.log(this)
            }
        }
        const zhangsan = new People('张三')
        zhangsan.sayHi()//zhangsan实例
        ```
    
    5. 匿名函数
    
       ```javascript
       setTimeout(function(){
         console.log(this)//this永远指向window
       },200)
       ```
    
       
    
4. ==手写bind==

    ```javascript
    //bind主要用途在于改变函数的this，所以bind的方法调用的主体是函数，为了让所有函数都可以访问到bind方法，要把bind方法放在函数构造函数的原型上，也就是Function.prototype
    Function.prototype.bindTemp = function(){
        //将参数变成数组
        const arg = Arrray.prototype.slice.call(arguments)
        const that = arg.shift()
        //第一种方法
        const self = this
        return function(parames){
        //arg:bind定义参数，parames：执行参数
            return  self.apply(that,arg,parames)
        }
        //第二种方法，箭头函不用保存this值，因为this直接指向上一层作用域
        return (parames)=>{
        		this.apply(that,arg,parames)
        }
    }
    ```

5. ==闭包实际中的应用==：7.4私有变量

    1. 隐藏数据，只提供API进行调用
        ```
        function  creatCache(){
            const  data = {}//闭包中数据被隐藏，不被外界访问
            return  {
                set:function(key,value){
                    data[key] = value
                },
                get:function(key){
                    return  data[key]
                }
            }
        }
        const c = creatCache()
        c.set('a',100)
        console.log(c.get('a'))
        ```

6. ==创建10个a标签，点击弹出对应的索引==
    > 7.2.1 闭包与变量;7.3模仿块级作用域
    ```
    let a
    for(let i=0;i<10;i++){
        a = document.createElement('a')
        a.innerHTML = `${i}<br />`
        a.addEventListener('click',function(e){
            e.preventDefault()
            alert(i)
        })
        document.body.appendChild(a)
    }
    ```
## 第八章 BOM
==面试题==
1. ==如何识别浏览器类型==
> navigator.userAgent
2. ==拆分url各部分==
```
location.href
"https://note.youdao.com/web/#/file/WEBb2990122a53592da8cc14c9694a584c2/markdown/WEBb6dab9f21b4226209da0f51d2109f0c9/"
location.protocol
"https:"
location.pathname
"/web/"
location.search
""
location.hash
"#/file/WEBb2990122a53592da8cc14c9694a584c2/markdown/WEBb6dab9f21b4226209da0f51d2109f0c9/"
```
3. ==获取url参数==
```
    function query(name){
        //去掉问号
        const search = location.search.substr(1)
        const reg = new RegExp(`(^|&)${name}=([^&]*)(&|$)`,'i');
        const result = search.match(reg)
        if(result === null){
            return null
        }
        return result[2]
    }
    可以使用数组用&和=进行拆分
    function query(name){
        const search = location.search
        const p = new URLSearchParams(search)
        return p.get(name)
    }
```
## 第十章 DOM
### 10.1 节点层次
```
<html> 
    <head> 
        <title>Sample Page</title> 
        
    </head> 
    <body> 
        <p>Hello World!</p> 
    </body> 
</html>
```
> 文档节点是每个文档的根节点，在这个例子中，文档只有一个子节点，即<html>元素，我们称之为文档元素，每个文档只能有一个文档元素，在HTML页面中，文档元素始终都是<html>元素，在XML中，没有预定义的元素，因此任何元素都有可能成为文档元素

#### 10.1.1 Node类型
> 除了IE之外，在其他浏览器中都可以访问这个类型，JavaScript中所有节点类型都继承自node类型；每个节点都有一个nodeType属性，用于表明节点的类型，ie上没有公开node类型的构造函数

```
if (someNode.nodeType == Node.ELEMENT_NODE){ //在 IE 中无效 
    alert("Node is an element.")
}
if (someNode.nodeType == 1){ //适用于所有浏览器
    alert("Node is an element.")
}
```
1. nodeName和nodeValue属性

> 这两个属性的值完全取决于节点的类型，对于元素节点，nodeName中保存的始终都是元素的标签名，而 nodeValue 的值则始终为 null。

2. 节点关系

> 每个节点都有一个childNodes属性，其中保存着一个NodeList对象。NodeList是一种类数组对象，用于保存一组有序的节点，可以通过位置来访问这些节点。NodeList对象的独特之处在于，它实际上是基于DOM结构动态执行查询的结果，因此DOM结构的变化能够自动反映在NodeList对象中。我们常说，NodeList是有生命、有呼吸的对象，而不是在我们第一次访问它们的某个瞬间拍摄下来的一张快照。此外，包含在childNodes列表中的每个节点相互之间都是同胞节点。通过使用列表中每个节点的previousSibling 和 nextSibling属性，可以访问同一列表中的其他节点。列表中第一个节点的previousSibling属性值为 null，而列表中最后一个节点的nextSibling属性的值同样也为null
```
var firstChild = someNode.childNodes[0];
var secondChild = someNode.childNodes.item(1); 
var count = someNode.childNodes.length;
```
> 每个节点都有一个 parentNode 属性，该属性指向文档树中的父节点;

> hasChildNodes()判断某节点是否有子节点，有一个或多个返回true，这比查询childNodes列表的length属性更简单

3. 操作节点

> appendChild()，用于向childNodes列表的末尾添加一个节点;如果传入到appendChild()中的节点已经是文档的一部分了，那结果就是将该节点从原来的位置转移到新位置。即使可以将DOM树看成是由一系列指针连接起来的，但任何 DOM 节点也不能同时出 现在文档中的多个位置上;

```
var returnedNode = someNode.appendChild(newNode); 
alert(returnedNode == newNode); //true 
alert(someNode.lastChild == newNode); //true

var returnedNode = someNode.appendChild(someNode.firstChild); alert(returnedNode == someNode.firstChild); //false 
alert(returnedNode == someNode.lastChild); //true
```
> insertBefore():插入节点在某个特定的位置，两个参数：要插入的节点、作为参照的节点，返回插入的节点，如果参照节点是null,则插入成最后一个节点；

```
//插入后成为最后一个子节点 
returnedNode = someNode.insertBefore(newNode, null); 
alert(newNode == someNode.lastChild); //true 
//插入后成为第一个子节点 
var returnedNode = someNode.insertBefore(newNode, someNode.firstChild); alert(returnedNode == newNode); //true 
alert(newNode == someNode.firstChild); //true 
//插入到最后一个子节点前面 
returnedNode = someNode.insertBefore(newNode, someNode.lastChild); alert(newNode == someNode.childNodes[someNode.childNodes.length-2]); //true
```

> replaceChild():接收两个参数：插入的节点和替换的节点，返回要替换的节点，被替换的节点也会从文档树中移除；在使用replaceChild()插入一个节点时，该节点的所有关系指针都会从被它替换的节点复制过来。尽管从技术上讲，被替换的节点仍然还在文档中，但它在文档中已经没有了自己的位置。

4. 其他方法

> cloneNode():用于创建调用这个方法的节点的一个完全相同的副本；接收一个布尔值参数，表示是否执行深复制，参数为true,执行深复制，也就是复制节点及其整个子节点树；在参数为false的情况下，执行浅复制，只复制节点本身，复制后返回的节点副本属于文档所有，没有指定父节点

#### 10.1.2 Document类型

> Document类型表示文档，在浏览器中，document对象是HTMLDocument（继承自Document类型）的一个实例，表示整个HTML页面。而且，document对象是window对象的一个属性，因此可以将其作为全局对象来访问；Document类型可以表示HTML页面或者其他基于 XML的文档；

1. 文档的子节点：
- document.documentElement表示html

```javascript
var html = document.documentElement; //取得对<html>的引用 ，所有浏览器都兼容
alert(html === document.childNodes[0]); //true 
alert(html === document.firstChild); //true
var body = document.body; //取得对<body>的引用，所有浏览器都兼容
var doctype = document.doctype; //取得对<!DOCTYPE>的引用,不是所有浏览器都兼容

```
2. 文档信息
```
//取得文档标题 
var originalTitle = document.title; 
//设置文档标题 
document.title = "New page title";
//取得完整的 URL 
var url = document.URL; 
//取得域名
var domain = document.domain; //可以设置但是一定是url包含的域
//取得来源页面的URL 
var referrer = document.referrer;
```
3. 查找元素
```
<div id="myDiv">Some text</div> 
var div = document.getElementById("myDiv");//取得<div>元素的引用,id名称严格匹配(IE除外)
var images = document.getElementsByTagName("img");//返回的是包含零或多个元素的NodeList，在HTML文档中，这个方法会返回一个HTMLCollection对象，作为一个“动态”集合
var radios = document.getElementsByName("color");
```
4. 特殊集合
```
document.anchors，包含文档中所有带name特性的<a>元素;
document.applets，包含文档中所有的<applet>元素，因为不再推荐使用<applet>元素， 所以这个集合已经不建议使用了
document.forms，包含文档中所有的<form>元素，与document.getElementsByTagName("form") 得到的结果相同
document.images，包含文档中所有的<img>元素，与 document.getElementsByTagName ("img")得到的结果相同；
document.links，包含文档中所有带 href 特性的<a>元素。
```
5. DOM一致性检测
6. 文档写入

> write()、writeln()、open()和 close();

#### 10.1.3 Element类型
```
var div = document.getElementById("myDiv"); 
alert(div.tagName); //"DIV" 
alert(div.tagName == div.nodeName); //true
在HTML中标签名都以全部大写表示，而在XML中，标签名始终会与源代码中保持一致
if (element.tagName == "div"){ //不能这样比较，很容易出错！ 
    //在此执行某些操作
}
if (element.tagName.toLowerCase() == "div"){ //这样最好（适用于任何文档）
    //在此执行某些操作 
}
```
1. HTML元素
2. 取得特性

> 每个元素都有一或多个特性，这些特性的用途是给出相应元素或其内容的附加信息。操作特性的 DOM 方法主要有三个，分别是 getAttribute()、setAttribute()和 removeAttribute()。

```
//特征名称不区分大小写
var div = document.getElementById("myDiv"); 
alert(div.getAttribute("id")); //"myDiv" 
alert(div.getAttribute("class")); //"bd" 
alert(div.getAttribute("title")); //"Body text" 
alert(div.getAttribute("lang")); //"en" 
alert(div.getAttribute("dir")); //"ltr"
```
3. 设置特性
```
div.setAttribute("id", "someOtherId"); 
div.setAttribute("class", "ft"); 
div.setAttribute("title", "Some other text");
```
4. 删除特性
```
removeAttribute()，这个方法用于彻底删除元素的特性。调用这个方法不仅会清除特性的值，而且也会从元素中完全删除特性
div.removeAttribute("class");
```
5. attributes属性

> getNamedItem(name)：返回nodeName属性等于name的节点;
  removeNamedItem(name)：从列表中移除nodeName属性等于name的节点; setNamedItem(node)：向列表中添加节点，以节点的nodeName属性为索引; item(pos)：返回位于数字 pos 位置处的节点。

```
var id = element.attributes.getNamedItem("id").nodeValue; 
var id = element.attributes["id"].nodeValue;
```
6. 创建元素
```
var div = document.createElement("div");
document.body.appendChild(div);
```
7. 元素的子节点

#### 10.1.4 Text类型
```
var element = document.createElement("div"); 
element.className = "message"; 
var textNode = document.createTextNode("Hello world!"); 
element.appendChild(textNode); 
document.body.appendChild(element);
```
#### 10.1.5 Comment类型
#### 10.1.6 CDATASection类型
#### 10.1.7 DocumentType类型
#### 10.1.8 DocumentFragment类型
```
//如果逐个地添加列表项，将会导致浏览器反复渲染（呈现）新信息。为避免这个问题，可以像下面这样使用一个文档片段来保存创建的列表项，然后再一次性将它们添加到文档中;
var fragment = document.createDocumentFragment(); 
var ul = document.getElementById("myList"); 
var li = null; 
for (let i=0; i < 3; i++){ 
    li = document.createElement("li");
    li.appendChild(document.createTextNode("Item " + (i+1))); 
    fragment.appendChild(li); 
} 
ul.appendChild(fragment);

```
#### 10.1.9 Attr类型

#### 10.1.10 node接口

https://developer.mozilla.org/zh-CN/docs/Web/API/Node

#### 10.2 DOM操作技术
#### 10.2.1 动态脚本
```
function loadScript(url){ 
    var script = document.createElement("script"); 
    script.type = "text/javascript"; 
    script.src = url;
    document.body.appendChild(script); 
}
loadScript("client.js");



function loadScriptString(code){ 
    var script = document.createElement("script"); 
    script.type = "text/javascript"; 
    try { 
        script.appendChild(document.createTextNode(code)); 
    } catch (ex){ 
        script.text = code; 
    } 
    document.body.appendChild(script); 
} 
loadScriptString("function sayHi(){alert('hi');}");
```
#### 10.2.2 动态样式
```
function loadStyles(url){
    var link = document.createElement("link");
    link.rel = "stylesheet"; 
    link.type = "text/css"; 
    link.href = url; 
    var head = document.getElementsByTagName("head")[0]; 
    head.appendChild(link); 
}
loadStyles("styles.css");


function loadStyleString(css){ 
    var style = document.createElement("style");
    style.type = "text/css"; 
    try{ 
        style.appendChild(document.createTextNode(css));
    }catch (ex){ 
        style.styleSheet.cssText = css; 
    } 
    var head = document.getElementsByTagName("head")[0]; 
    head.appendChild(style); 
}
loadStyleString("body{background-color:red}");
```
#### 10.2.3 操作表格
#### 10.2.4 使用NodeList
```
//及时对查询到的DOM进行缓存，提高性能
var divs = document.getElementsByTagName("div"), 
    i, 
    len, 
    div; 
for (i=0, len=divs.length; i < len; i++){
    div = document.createElement("div"); 
    document.body.appendChild(div); 
}
```
### 10.3 小结
1. 最基本的节点类型是Node，用于抽象地表示文档中一个独立的部分；所有其他类型都继承自 Node；
2. Document 类型表示整个文档，是一组分层节点的根节点。在 JavaScript 中，document 对象是 Document的一个实例。使用 document 对象，有很多种方式可以查询和取得节点；
3. Element 节点表示文档中的所有 HTML 或 XML 元素，可以用来操作这些元素的内容和特性；

## 第十一章 DOM扩展
### 11.1 选择符API
1. querySelector()方法接收一个css选择符，返回与该模式匹配的第一个元素,如果没有找到匹配的元素，返回null;
2. querySelectorAll()方法接收的参数与 querySelector()方法一样，都是一个 CSS 选择符，但 返回的是所有匹配的元素而不仅仅是一个元素。这个方法返回的是一个 NodeList 的实例；
3. matchesSelector():一个css选择符,如果调用元素与该选择符匹配，返回 true；否则，返回 false;
```
    const  div = document.querySelector("#mxm")
    console.log("div",div)
    const  p = document.querySelectorAll("p")
    for(let i=0;i<p.length;i++){
        console.log("[]",p[i].className)
        console.log("item()",p.item(i).className)
    }
```
### 11.2 元素遍历
1. childElementCount：返回子元素（不包括文本节点和注释）的个数；
2. firstElementChild：指向第一个子元素；firstChild 的元素版；
3. lastElementChild：指向最后一个子元素；lastChild 的元素版；
4. previousElementSibling：指向前一个同辈元素；previousSibling的元素版；
5. nextElementSibling：指向后一个同辈元素；nextSibling 的元素版；
```
const  div = document.querySelector("#mxm")
console.log("div",div.childElementCount)
console.log("div element",div.firstElementChild,div.lastElementChild,div.previousElementSibling,div.nextElementSibling)
```
### 11.3 HTML5
1. 与类相关的扩充：
    1. getElementsByClassName()方法接收一个参数，即一个包含一或多个类名的字符串，返回带有 指定类的所有元素的NodeList；
    2. 为所有元素添加classList属性；
    ```
    const  p = document.getElementsByClassName("p2")
    console.log("p",p)
    const  p = document.getElementById("nump")
    p.classList.remove("dd")
    console.log("dd",p.className)
    p.classList.add("dd")
    console.log("adddd",p.className)
    p.classList.toggle("pp")
    // p.classList.toggle("pp")
    console.log("adddd",p.className)
    console.log("contains",p.classList.contains("pp"))
    ```
2. 焦点管理:document.activeElement
    ```
    const  button = document.querySelector("button")
    button.focus()
    console.log(document.activeElement)
    console.log(document.hasFocus())
    ```
3. HTMLDocument的变化:
    1. readyState属性
    ```
    console.log(document.readyState)
    setTimeout(()=>{
        console.log(document.readyState)
    },3000)
    ```
    2. head属性
    ```
    console.log(document.head)
    ```
4. 字符集属性
    ```
    console.log(document.charset)
    ```
5. 自定义数据属性
    ```
    var p0 = document.getElementsByClassName("p0")
    p0.item(0).dataset.mxm = "mxm"
    console.log("p0",p0.item(0).dataset)
    const  div = document.querySelector("#mxm")
    ```
6. 插入标记
    ```
    const p = document.createElement("p")
    p.innerHTML = 'innerHtml'
    p.appendChild(document.createTextNode("innerHtml"))
    div.appendChild(p)
    const  div = document.querySelector("#mxm")
    console.log("div",div.outerHTML)
    const  div = document.querySelector("#mxm")
    div.insertAdjacentHTML("beforebegin","<p>mxmbeforebegin</p>")
    div.insertAdjacentHTML("afterbegin","<p>mxmbafterbegin</p>")
    div.insertAdjacentHTML("beforeend","<p>mxmbbeforeend</p>")
    div.insertAdjacentHTML("afterend","<p>mxmbafterend</p>")
    ```
### 11.4 专有扩展
### 11.5 小结
1. Selectors API，定义了两个方法，让开发人员能够基于CSS选择符从DOM中取得元素，这两个方法是 querySelector()和 querySelectorAll();
2. Element Traversal，为 DOM 元素定义了额外的属性，让开发人员能够更方便地从一个元素跳到 另一个元素。之所以会出现这个扩展，是因为浏览器处理DOM元素间空白符的方式不一样;
3. HTML5，为标准的DOM定义了很多扩展功能。其中包括在 innerHTML 属性这样的事实标准基 础上提供的标准定义，以及为管理焦点、设置字符集、滚动页面而规定的扩展 API。

## 第十二章 DOM2和DOM3

==面试题==

1. ==DOM数据结构==
> DOM是一个DOM树，只有一个根节点
2. ==DOM操作==
    ```
    const  div = document.getElementById("#mxm")
    const  div = document.getElementsByTagName("div")
    const  div = document.getElementsByClassName(".user")
    const  div = document.querySelector(".user")
    const  div = document.querySelectorAll("div")
    ```
3. ==attr和proptery==
    1. proptery修改对象属性，不会体现在html结构中
    2. attr修改html属性，会改变html结构
    3. attr和proptery都会引起DOM重新渲染
    ```
    const  div = document.getElementById("#mxm")
    div.style.width = '100px'
    console.log("width",div.style.width)
    console.log("width",div.style.id)
    
    div.setAttribute('data-mxm',mxm)
    console.log("data-mxm",div.getAttributr("data-mxm"))
    ```
4. ==操作节点==
5. ==DOM性能==
    1. DOM操作非常昂贵，避免频繁DOM操作
    2. 对DOM查询做缓存：10.2.4 使用NodeList
    3. 将频繁操作改为一次操作：10.1.8 DocumentFragment类型
    ==面试题==
1. ==同步与异步区别==:同步是按照顺序一个一个去执行，异步是需要进行等待才会返回信息；同步会发生阻塞代码执行，异步不会阻塞代码执行；单线程：一次只能执行一条命令，只能排队进行（不能发生阻塞）
    ```
    console.log(100)
    alert(200)
    console.log(300)
    //100 300(在alert弹框点击确定是打印300，alert是同步的，发生了阻塞现象)
    ```
2. ==异步应用场景==
    1. 网络请求(Ajax)
        ```
        console.log('start')
        $.get('data.json',function(data){
            console.log('data')
        })
        console.log('end')
        //start end data
        ```
    2. 加载图片
        ```
        console.log('start')
        let img = document.createElment('img')
        img.onload = funciton(){
            console.log('img')
        }
        img.src = 'xxx.png'
        console.log('end')
        //start end img
        ```
    3. 定时器：所有的异步场景都会被拿出去，放到一边进行等着，什么时候有空就会执行，执行过程中先执行同步，再根据具体时间执行异步,setTimeout设置相同时间就会同时打印出内容
        ```
        console.log('100')
        setTimeout(function(){
            console.log('200')
        },1000)
        console.log('300')
        //100 300 200
        
        console.log('100')
        setTimeout(function(){
            console.log('200')
        },1000)
        console.log('300')
        setTimeout(function(){
            console.log('400')
        },0)
        //100 300 400 200
        ```
    4. 事件绑定(事件绑定不知道什么时候点所以是异步)
        ```
        console.log('start')
        let div = document.getElemteById('div')
        div.addEventListener(click,funciton(){
            console.log('clicked')
        })
        console.log('end')
        //start end clicked
        ```
3. 手写Promise加载图片
    ```
    function loadImg(src){
        return new Promise(
            (resolve,reject) =>{
                const img = document.createElement('img')
                img.onload = ()=>{
                    resolve(img)
                }
                img.onerror = () =>{
                    const err = '图片加载失败'
                    reject(err)
                }
                img.src = src
            }
        )
    }
    const url = 'http://a2.att.hudong.com/36/48/19300001357258133412489354717.jpg'
    loadImg(url).then((res)=>{
        console.log(res.width)
    }).catch((error)=>{
        console.log(error)
    })
    const url1 = 'http://a2.att.hudong.com/36/48/19300001357258133412489354717.jpg'
    const url2 = 'http://a0.att.hudong.com/78/52/01200000123847134434529793168.jpg'
    loadImg(url1).then((img1)=>{
        console.log(img1.width)
        console.log(img1.height)
        return loadImg(url2)
    }).then((img2)=>{
        console.log(img2.width)
        console.log(img2.height)
    }).catch((error)=>{
        console.log(error)
    })
    ```
## 第十三章 事件
==面试题==
1. ==编写通用的事件监听函数==
    ```
    function bindEvent (ele, type, selector, fn) { 
        // 加入选择器应对更多情况
        if (fn == null) {
            fn = selector
            selector = null
        }//当不使用selector时，把fn换到前面来
        ele.addEventListener(type, function(e){
            //绑定事件，绑定时执行判断
            var target = e.target
            if (selector) {
                    //需要代理
                    if (target.matches(selector)) {
                        //判断，是否匹配选择器
                        fn.call(target, e)//执行主体为e.target，所以要把函数给回它执行
                    }  
            } else {
                    //不代理
                    fn.call(target, e)
            }
        })
    }
    var ul = document.querySelector("#ul")
    bindEvent(ul,'click','li',function(event){
        // alert(event.target.innerHTML)
        event.preventDefault()//阻止默认行为
        alert(this.innerHTML)
    })
    var btn = document.querySelector("#btn")
    bindEvent(btn,'click',function(event){
        alert(this.innerHTML)
    })
    ```
    
2. ==描述事件冒泡的流程==
>冒泡流程：目标元素 >.......> body(document.body)>html(document.documentElement)>document>window；事件捕获与其相反

> 应用场景事件代理(本来是一个对象执行的事件，交由给另一个对象执行，就是代理(委托),一般用于多个子对象的同一个操作，绑定到父对象身上，从而实现代码和性能上的优化：
① 不用逐个绑定，绑定到父，解决所有子（节约代码且无需遍历）
② 即使后面动态加载进来的子对象也无需另外绑定。)
3. ==无限下拉的图片列表，如何监听每个图片的点击==
> 主要原理是使用事件代理同第二道面试题
4. ==DOM事件级别==
   1. DOM0级事件：绑定:btn.onclick = function() { alert('Hello World'); };解绑：btn.onclick = null;缺点:一个处理程序无法同时绑定多个处理函数;
   2. DOM1级标准中并没有定义事件相关的内容，所以没有所谓的1级DOM事件模型；
   3. DOM2级事件：绑定:btn.addEventListener('mouseover', showFn, false);解绑：btn.removeEventListener('mouseover', showFn, false);优点：允许给一个处理程序添加多个处理函数；
   4. DOM3级事件:增加了更多的事件类型，比如：load、scroll、blur、focus；

5. ==事件模型==

> 包括事件冒泡与事件捕获

6. ==事件流(浏览器与用户操作实现的过程)==

> 一共三步：事件捕获阶段、目标阶段、冒泡阶段

7. ==Event对象常用方法==
   1. preventDefault():阻止默认行为；比如a标签就是阻止跳转行为
   2. stopPropagation():阻止事件的冒泡方法，不让事件向window上层蔓延，但是默认事件仍然会执行;
   3. stopImmediatePropagtion():对同一个元素注册了两个click事件，那么默认情况下，两个事件都会被执行。用该方法，在A响应函数末尾加上该方法，可以阻止B事件执行；
   4. currentTarget和target:currentTarget：指的是当前元素，比如冒泡到父元素，那么currentTarget就是指当前父元素;target：当前被点击的元素，比如事件代理中，在父元素里面用target可以获取被点击的子元素

8. ==自定义事件==

```
<script type="text/javascript">
	//创建一个事件对象，名字为newEvent,类型为build,bubbles是否支持冒泡，默认false;cancelable:是否取消事	件的默认行为，默认false;composed:事件是否会触发shadow DOM（阴影DOM）根节点之外的事件监听器,默认false
	var newEvent = new Event('build',{bubbles:true,cancelable:true,composed:true});
	// 给这个事件对象创建一个属性并赋值 
	newEvent.name = '新的事件';
	//将自定义事件绑定在document对象上，这里绑定的事件要和我们创建的事件类型相同，不然无法触发
	document.addEventListener("build",function(){console.log(newEvent.name)});
	//触发自定义事件
	document.dispatchEvent(newEvent);
	
	
	//可以添加自定义数据
	var event = new CustomEvent('myEvent',{ 'detail':{
        time: new Date().toLocalDateString();
    } });
    document.addEventListener('myEvent',function (e){
        debugger;
    },false);
    document.dispatchEvent(event);
</script>
```



## 第二十章 JSON

## 第二十一章 Ajax与Comet
==面试题==
1. ==手写Ajsx==

   > 兼容性处理(IE浏览器)
```
function ajax(method,url,data){
  return new Promise((resolve,reject)=>{
    var xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function(){
        if(xhr.readystate === 4){
            if((xhr.status >= 200 && xhr.status < 300) || xhr.status === 304){
                console.log('response',xhr.responseText);
                reject(xhr.responseText)
            }else{
                console.log('response',xhr.status);
                reject(xhr.status)
            }
        }
    };
    xhr.open(method,url,true);
    xhr.send(data);
  })
};
ajax('get','/api',null).then(()=>{}).catch(()=>{})
```
2. ==同源策略==
> 同源:协议、域名、端口必须相同;ajax请求时，浏览器要求当前网页和server必须同源；
>
> 限制：Cookie、LocalStorage和IndexDB无法获取；DOM无法获取；AJAX请求不能发送；
3. ==跨域==
> 所有跨域都需要server端允许和配合，未经server端允许就实现跨域，说明浏览器有漏洞；

> img、script、JSONP方式(JSONP可以实现解决GET请求的跨域问题,但是不能解决POST请求的跨域问题)、CORS(在ajax的header中加入**Access-Control-Allow-Origin**，变异的ajax)、WebSocket、Hash(hash变动页面不刷新，search的改变页面刷新)、postMessage(h5中出现的)
>
> ```
> util.jsonp = function (url, onsuccess, onerror, charset) {
>   var callbackName = util.getName('tt_player');
>   window[callbackName] = function () {
>       if (onsuccess && util.isFunction(onsuccess)) {
>           onsuccess(arguments[0]);
>       }
>   };
>   var script = util.createScript(url + '&callback=' + callbackName, charset);
>   script.onload = script.onreadystatechange = function () {
>       if (!script.readyState || /loaded|complete/.test(script.readyState)) {
>           script.onload = script.onreadystatechange = null;
>           // 移除该script的 DOM 对象
>           if (script.parentNode) {
>               script.parentNode.removeChild(script);
>           }
>           // 删除函数或变量
>           window[callbackName] = null;
>       }
>   };
>   script.onerror = function () {
>       if (onerror && util.isFunction(onerror)) {
>           onerror();
>       }
>   };
>   document.getElementsByTagName('head')[0].appendChild(script);
> };
> // 利用hash，场景是当前页面 A 通过iframe或frame嵌入了跨域的页面 B
> // 在A中伪代码如下：
>   var B = document.getElementsByTagName('iframe');
>   B.src = B.src + '#' + 'data';
>   // 在B中的伪代码如下
>   window.onhashchange = function () {
>   var data = window.location.hash;
>   };
>  // postMessage(利用postMessage不能和服务端交换数据，只能在两个窗口（iframe）之间交换数据,两个窗口能通信的前提是，一个窗口以iframe的形式存在于另一个窗口，或者一个窗口是从另一个窗口通过window.open()或者超链接的形式打开的（同样可以用window.opener获取源窗口）)
>  // 窗口A(http:A.com)向跨域的窗口B(http:B.com)发送信息
>    Bwindow.postMessage('data', 'http://B.com');
>  // 在窗口B中监听
>    Awindow.addEventListener('message', function (event) {
>    console.log(event.origin//指的是发送消息的窗口的源
>    console.log(event.source);//指的是发送消息的窗口对象;
>    console.log(event.data);
>    }, false);
> // Websocket【参考资料】http://www.ruanyifeng.com/blog/2017/05/websocket.html
>   var ws = new WebSocket('wss://echo.websocket.org');
>   ws.onopen = function (evt) {
>   console.log('Connection open ...');
>   ws.send('Hello WebSockets!');
>   };
>   ws.onmessage = function (evt) {
>   console.log('Received Message: ', evt.data);
>   ws.close();
>   };
>   ws.onclose = function (evt) {
>   console.log('Connection closed.');
>   };
>  // CORS【参考资料】http://www.ruanyifeng.com/blog/2016/04/cors.html
>  // url（必选），options（可选）
>    fetch('/some/url/', {
>    method: 'get',
>    }).then(function (response) {
>   }).catch(function (err) {
>   // 出错了，等价于 then 的第二个参数，但这样更好用更直观
>   });
> ```
>
> 

4. ==ajax请求get与post区别==
    1. get一般用于查询操作、post一般用户提交操作
    2. get参数拼接在url上，post放在请求体内(数据体积可以更大)
    3. 安全性：post易于防止CSRF
5. ==解释jsonp原理，为何不是真正的ajax==
> jsonp是通过script标签使用callBack进行获取返回信息，ajax是通过new XMLHttpRequest()
6. ==前后端通信方式==

> Ajax(必须同源)、WebSocket(不受同源限制)、CORS(支持非同源通信)

## 第二十三章 离线应用与客户端存储

==面试题==

1. ==cookie、sessionStorage、localStorage==
    1. cookie本身用于浏览器与server通讯(请求头中带有cookie信息)，被借用做存储，使用document.cookie = 'a=100'进行修改和添加，最大4KB；
    2. sessionStorage、localStorage存储大小根据浏览器的不同最大为5M,拥有的api(setItem()、getItem()、removeItem()、key(index))，不会跟随http请求发送出去;localStorage数据会永久存储，除非使用代码或手动删除；sessionStorage数据只存在于当前的会话，浏览器关闭则清空

## 页面渲染
==面试题==
1. ==输入url到页面展示的过程==
   
   1. 用户在浏览器的地址栏输入访问的URL地址。浏览器会先根据这个URL查看浏览器缓存-系统缓存-路由器缓存，若缓存中有，直接跳到第3步操作，若没有，则按照下面的步骤进行操作；
      
   2. DNS解析：url地址->->主机名->ip地址，从url中获取端口号，浏览器与服务器建立连接；
   
   3. 浏览器根据ip地址以及端口向服务器发送http请求报文；
   
   4. 服务器处理http请求，并返回给浏览器一条响应报文；
   
   5. 浏览器渲染HTML过程(浏览器解析文档)；
   
      ```javascript
      - HTML被HTML解析器解析成DOM Tree, css则被css解析器解析成CSSOM Tree；
      - DOM Tree和CSSOM Tree解析完成后，被附加到一起，形成渲染树（Render Tree）;
      - reflow/layout(重排)：从根节点递归调用，计算每一个元素的大小、位置等，给出每个节点所应该在屏幕上出现的精确坐标；
      ```
      - 渲染绘制(重绘)，这个过程被叫做(Painting 或者 Repaint)。即根据计算好的信息绘制整个页面。
   
      ![image-20200426150424168](/Users/naebunsakai/Library/Application Support/typora-user-images/image-20200426150424168.png)
   
   6. 假如遇到<script>需要暂停渲染，优先加载并执行js代码，完成后继续渲染页面(js代码中可能会改变页面DOM,之前的渲染做无用功)；
   
2. 重排(重构/回流/reflow)与重绘(repaint或redraw)

    > 当DOM的变化引发了元素几何属性的变化，比如`改变元素的宽高`，`元素的位置`，导致浏览器不得不重新计算元素的几何属性，并重新构建渲染树，这个过程称为“重排”。完成重排后，要将重新构建的渲染树渲染到屏幕上，这个过程就是“重绘”。

    - 重排负责元素的几何属性更新，重绘负责元素的样式更新。而且，重排必然带来重绘，但是重绘未必带来重排；
    - 重排触发条件(任何页面布局和几何属性的改变都会触发重排):
      - 添加、删除可见的dom;
      - 元素的位置改变;
      - 元素的尺寸改变(外边距、内边距、边框厚度、宽高、等几何属性);
      - 页面渲染初始化(无法避免);
      - 浏览器窗口尺寸改变(resize事件发生时);
      - 填充内容的改变，比如文本的改变或图片大小改变而引起的计算值宽度和高度的改变;
      - 读取某些元素属性：（offsetLeft/Top/Height/Width,　clientTop/Left/Width/Height,　scrollTop/Left/Width/Height,　width/height,　getComputedStyle(),　currentStyle(IE)　)
    - 重绘触发的条件
      - 重绘发生在元素的可见的外观被改变，但并没有影响到布局的时候。比如，仅修改DOM元素的字体颜色
    - 优化
      - 浏览器自己的优化：浏览器会维护1个队列，把所有会引起回流、重绘的操作放入这个队列，等队列中的操作到了一定的数量或者到了一定的时间间隔，浏览器就会flush队列，进行一个批处理。这样就会让多次的回流、重绘变成一次回流重绘；
      - 直接改变元素的className；
      - display：none；先设置元素为display：none；然后进行页面布局等操作；设置完成后将元素设置为display：block；这样的话就只引发两次重绘和重排；
      - 不要经常访问浏览器的flush队列属性；如果一定要访问，可以利用缓存。将访问的值存储起来，接下来使用就不会再引发回流；
      - 使用cloneNode(true or false) 和 replaceChild 技术，引发一次回流和重绘；
      - 将需要多次重排的元素，position属性设为absolute或fixed，元素脱离了文档流，它的变化不会影响到其他元素；
      - 如果需要创建多个DOM节点，可以使用DocumentFragment创建完后一次性的加入document；

3. ==css为什么放在head中==
> 在DOM树生成之前，CSSOM树生成，不会出现页面无样式的情况
4. ==js为什么放在body最后==

> 不会导致页面的渲染过程较长，不会出现阻塞的情况
5. ==window.onload和DOMContentLoaded==
   1. window.onload(load)需要等待页面全部资源加载完毕才会执行包括视频，图片
   2. DOMContentLoaded(ready)只需要DOM渲染即可执行，此时图片、视频 可能没有加载完毕；
   3. img标签不会阻碍页面渲染，假如图片未加载出来也会继续向下进行渲染；

## 性能优化

1. 多使用内存、缓存或其他方法；减少使用CPU计算量、减少网络加载耗时；
2. 减少资源体积(代码压缩)：webpack打包
3. 渲染更快: css放在head,js放在body最后,懒加载(图片懒加载)，DOM查询缓存，多次DOM操作合并一次；防抖、节流
4. ==防抖与节流==
```javascript
> 防抖的思想：在设置时间间隔之内触发的事件中取消前一次触发事件的定时函数，在最后一次停留的时间大于设置的间隔时间，进行处理事件的定时函数;相当于就是多次执行，只执行一次,且执行最后一次；
> 应用场景：用户搜索，图片验证码点击，window触发resize的时候，不断的调整浏览器窗口大小会不断的触发这个事件，用防抖来让其只触发一次
var input = document.querySelector("#search")
function debounce(fn,delay=500){
  let time = null
  return function(){
  //用于取消上一次的定时函数
    if(time){
      clearTimeout(time)
    }
    time = setTimeout(function(){
      fn.apply(this,arguments)
      time = null
    },delay)
  }
}
input.addEventListener('keyup',debounce(()=>{
  console.log("11111",input.value)
},1000))
> 节流思想：在用户不断的触发事件中，按照设定的时间进行触发定时函数，并不是每一次触发事件都可以执行定时函数，而是根据定时函数执行完毕后立马执行下一次触发事件，触发事件的次数大于定时函数执行的次数，节流是将多次执行变为每隔一段时间执行，只执行规定会时间内第一次触发
> 应用场景：拖拽元素，下拉加载，鼠标不断点击触发，mousedown(单位时间内只触发一次)，监听滚动事件，比如是否滑到底部自动加载更多，用throttle来判断
const box = document.querySelector('#box');
function throttle(fn,delay=100){
  let time = null
  return function(){
  //用户连续触发事件中，time已经有值，直接返回，不进行对time赋值的操作
    if(time){
      return
    }
    time = setTimeout(function(){
      fn.apply(this,arguments)
      time = null
    },delay)
  }
}
box.addEventListener('drag',throttle((e){
    console.log('1111',e.offsetX,e.offsetY)
},100))
```


## 安全

1. XSS攻击:使用script获取cookie信息；预防：把左右尖括号替换成&lt;&gt
2. CSRF攻击:使用img src属性进行访问链接(用户已经在网站中登陆注册过了)，此时已经带有用户信息；预防：使用post接口，增加验证

==面试题==

1. 如何捕获异常
    1. try{}catch(error){console.log(error)}.finally{};
    2. window.onerror = function(){}

2.  前端错误分类：
   - 即时运行错误：代码错误，捕获错误方式：try{}catch(error){console.log(error)}.finally{};window.onerror = function(){}
   - 资源加载错误：object.onerror、performnce.getEntries()、Error事件捕获(冒泡不可以)；
   - 跨域的js运行错误可以捕获么，错误提示什么，应该怎么处理？
   - ![image-20200427173939442](/Users/naebunsakai/Library/Application Support/typora-user-images/image-20200427173939442.png)无法拿到具体信息
   - 上报错误的基本原理
     - 利用AJAX方式上报；
     - 使用Image对象：(new Image()).src = 'http://baidu.com'

## 页面性能

1. 资源压缩合并，减少http请求；
2. 非核心代码异步加载>异步加载方式>异步加载区别；
   1. 动态脚本加载、defer、async
3. 利用浏览器缓存>缓存的分类>缓存的原理；
   1. 强缓存(Cache-control)、协商缓存(需要询问再决定用不用缓存)
4. 使用CDN
5. 预解析DNS

## 第二十五章 新兴的API

requestAnimationFrame()

![image-20200427175600077](/Users/naebunsakai/Library/Application Support/typora-user-images/image-20200427175600077.png)

职业竞争力、职业规划



![image-20200427182231402](/Users/naebunsakai/Library/Application Support/typora-user-images/image-20200427182231402.png)

![image-20200427182725816](/Users/naebunsakai/Library/Application Support/typora-user-images/image-20200427182725816.png)





# ECMAScript 6 入门

## 第一章 块级作用域绑定

### 1.1 var声明及变量提升(Hoisting)机制

> 通过关键字var声明的变量，无论在哪里声明都会被当成当前作用域顶部生成的变量，这就是变量hoisting机制，而且var声明的变量可以在window中访问到

- var变量在提升的过程中直接赋值默认值undefined
- 所有未声明直接赋值的变量都会自动挂在顶层对象下，造成全局环境变量不可控、混乱
- 允许多次声明同一变量而不报错，造成代码不容易维护

```javascript
function getValue(type){
  if(type){
    var value = 'blue'
    return value
  }else{
    console.log("value",value)//undefined
    return null
  }
  console.log("value",value)//undefined
}
//代码中两处打印value值，没有报错说明value变量已经被声明，这就是hoisting的机制，会把var声明的变量直接提升到作用域的顶部声明

//所有未声明直接赋值的变量都会自动挂在顶层对象下
a = 2
console.log(window.a) // 2

function foo(){
    b = 3
}
foo()
console.log(window.b) // 3

//允许多次声明同一变量而不报错，造成代码不容易维护
var x = 1
var x = 2
```

- es6中强化了变量声明周期的控制

### 1.2  let声明

#### 1.2.1 定义

> let只在代码块内有效

```javascript
var a = [];
for (var i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);//var声明变量是全局变量，所以此处的i指向的是全局的变量i，所以输出为10
  };
}
a[6](); // 10

var a = [];
for (let i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);//let声明是局部变量，只在当轮有效，每次i都是一个新的变量
  };
}
a[6](); // 6

for (let i = 0; i < 3; i++) {
  let i = 'abc';
  console.log(i);//for循环中设置循环变量的那部分是一个父作用域，而循环体内部是一个单独的子作用域。所以可以正常发打印出三遍abc
}
// abc
// abc
// abc
```

#### 1.2.2 不存在变量提升

> let语法不存在变量提升，它所声明的变量一定要在声明后使用，否则报错

```javascript
// var 的情况
console.log(foo); // 输出undefined
var foo = 2;

// let 的情况
console.log(bar); // 报错ReferenceError
let bar = 2;
```

#### 1.2.3 暂时性死区(temporal dead zone)

- 块级作用域中使用let声明的变量后，此变量就绑定在这个作用域内，不再受外部影响,使用let命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”

  ```javascript
  var tmp = 123;
  if (true) {
    tmp = 'abc'; // ReferenceError,
    let tmp;
  }
  ```

- typeof命令不再安全(由于存在TDZ)

  ```javascript
  typeof x; // ReferenceError
  let x;
  ```

#### 1.2.3 不允许重复声明

- let命令不允许在相同作用内，重复声明一个变量

  ```javascript
  // 报错
  function func() {
    let a = 10;
    var a = 1;
  }
  // 报错
  function func() {
    let a = 10;
    let a = 1;
  }
  ```

- 函数中不允许重新声明接收到参数

  ```javascript
  function func(arg) {
    let arg;
  }
  func() // 报错
  ```

### 1.3  const声明

## 第九章 JavaScript中的类

### 9.1 基本语法

#### 9.1.1 es5实现

在es5中使用构造函数，在原型链上添加方法的方法实现实例对象

```javascript
function Point(x, y) {
  this.x = x;
  this.y = y;
}

Point.prototype.toString = function () {
  return '(' + this.x + ', ' + this.y + ')';
};

var p = new Point(1, 2);
```

此种方法和传统的面向对象有很大的差别，因此es6中出现了class

#### 9.1.2 es6实现

##### 9.1.2 .1 class

es6中添加class，可以定义类，实际上class就是es5中实现面向对象的方法糖，把es5中实现的功能进行封装，形成了class，实现的原理完全相同，使用class可以让对象原型的写法更加清晰、更像面向对象编程的语法而已,类不存在变量提升（hoist）

```javascript
class Point {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }

  toString() {
    return '(' + this.x + ', ' + this.y + ')';
  }
}
```

上面代码定义了一个“类”，可以看到里面有一个`constructor()`方法，这就是构造方法，而`this`关键字则代表实例对象。这种新的 Class 写法，本质上与本章开头的 ES5 的构造函数`Point`是一致的。类的所有方法都定义在类的`prototype`属性上面。在类的实例上面调用方法，其实就是调用原型上的方法;`prototype`对象的`constructor()`属性，直接指向“类”的本身,这与 ES5 的行为是一致的;类的内部所有定义的方法，都是不可枚举的,这一点与 ES5 的行为不一致。

##### 9.1.2 .2 constructor方法

`constructor()`方法是类的默认方法，通过`new`命令生成对象实例时，自动调用该方法，然后返回实例对象(即this)，也可以指定返回另一个对象，这样的话该实例不是该类的实例。

一个类必须有`constructor()`方法，如果没有显式定义，一个空的`constructor()`方法会被默认添加。

##### 9.1.2 .3 访问器属性

##### 取值函数（getter）和存值函数（setter）

```javascript
class MyClass {
  constructor() {
    // ...
  }
  get prop() {
    return 'getter';
  }
  set prop(value) {
    console.log('setter: '+value);
  }
}
let inst = new MyClass();
inst.prop = 123;
```

##### 9.1.2 .4 静态成员

类相当于实例的原型，所有在类中定义的方法，都会被实例继承。如果在一个方法前，加上`static`关键字，就表示该方法不会被实例继承，而是直接通过类来调用，这就称为“静态方法”。如果静态方法包含`this`关键字，这个`this`指的是类，而不是实例,父类的静态方法，可以被子类继承

```javascript
class Foo {
  static classMethod() {
    return 'hello';
  }
}

Foo.classMethod() // 'hello'

var foo = new Foo();
foo.classMethod()
// TypeError: foo.classMethod is not a function
```

##### 9.1.2 .5 可计算成员名称

```javascript
let methodName = 'getArea';

class Square {
  constructor(length) {
    // ...
  }

  [methodName]() {
    // ...
  }
}
```

> 访问器属性也可以如此定义

### 9.2 继承与派生类

#### 9.2.1 简介

> es6使用extends来实现继承，es5中集中继承的方式请复习JavaScript高级程序设计中第六章内容

## 第十章 数组扩展

### 10.1 Array.from()

#### 10.1.1 作用

- 此方法可以将两类对象转化为数组:类数组(Nodelist、arguments等)、可遍历的对象(Map、Set)

- 扩展运算符也可以进行转换成数组

- 类数组的定义:类似数组的对象，本质特征只有一点，即必须有`length`属性

- 扩展运算符与Array.from的区别:任何有`length`属性的对象，都可以通过`Array.from`方法转为数组，而此时扩展运算符就无法转换，扩展运算符背后调用的是遍历器接口（`Symbol.iterator`），如果一个对象没有部署这个接口，就无法转换
- `Array.from()`的另一个应用是，将字符串转为数组，然后返回字符串的长度。因为它能正确处理各种 Unicode 字符，可以避免 JavaScript 将大于`\uFFFF`的 Unicode 字符，算作两个字符的 bug。

```javascript
let arrayLike = {
  '0':'a',
  '1':'b',
  '2':'c',
  length:3
}
//es5
var arr1 = [].slice.call(arrayLike)//["a", "b", "c"]
//es6
const arr2 = Array.from(arrayLike) //["a", "b", "c"]
Array.from({ length: 3 });// [ undefined, undefined, undefined ]
```

#### 10.1.2 参数

- 第一个参数是要转变的类数组、可遍历对象
- 第二个参数作用类似于数组的`map`方法，用来对每个元素进行处理，将处理后的值放入返回的数组，这样不需要对数组的值进行再一次的单独处理
- 第三个参数用来绑定`this`

### 10.2 Array.of()

#### 10.2.1 作用

- 主要用于将一组值转为数组
- 主要用于弥补构造函数Array()的不足，Array()会根据参数个数的不同产生不同的结果，没有参数代表空数组，一个参数代表数组的长度，多个参数代表数组每一项的值
- `Array.of`基本上可以用来替代`Array()`或`new Array()`，并且不存在由于参数不同而导致的重载。它的行为非常统一

#### 10.2.2 参数

- `Array.of`总是返回参数值组成的数组。如果没有参数，就返回一个空数组。

```javascript
Array() // []
Array(3) // [, , ,]
Array(3, 11, 8) // [3, 11, 8]
Array.of() // []
Array.of(undefined) // [undefined]
Array.of(1) // [1]
Array.of(1, 2) // [1, 2]
```

### 10.3 copyWithin()

#### 10.3.1 作用

- 数组实例的`copyWithin()`方法，在当前数组内部，将指定位置的成员复制到其他位置（会覆盖原有成员），然后返回当前数组。也就是说，使用这个方法，会修改当前数组。

#### 10.3.2 参数

- target（必需）：从该位置开始替换数据。如果为负值，表示倒数。
- start（可选）：从该位置开始读取数据，默认为 0。如果为负值，表示从末尾开始计算。
- end（可选）：到该位置前停止读取数据，默认等于数组长度。如果为负值，表示从末尾开始计算。

### 10.4 find()、findIndex()

#### 10.4.1 作用

- find()用于找出<font color="red">第一个符合条件</font>的数组成员。它的参数是一个回调函数，所有数组成员依次执行该回调函数，直到找出第一个返回值为`true`的成员，<font color="red">然后返回该成员，不向下进行循环</font>。如果没有符合条件的成员，则返回`undefined`。
- findIndex()与`find()`方法非常类似，<font color="red">返回第一个符合条件的数组成员的位置，不向下进行循环</font>,如果所有成员都不符合条件，则返回`-1`

```javascript
[1, 4, -5, 10].find((n) => n < 0)
```

### 10.5 fill()

#### 10.4.1 作用

- `fill`方法使用给定值，填充一个数组
- `fill`方法用于空数组的初始化非常方便。数组中已有的元素，会被全部抹去
- 如果填充的类型为对象，那么被赋值的是同一个内存地址的对象，而不是深拷贝对象

#### 10.4.2 参数

- 第一个参数:数组填充的值
- 第二个和第三个参数，用于指定填充的起始位置和结束位置

```javascript
['a', 'b', 'c'].fill(7, 1, 2)//['a', 7, 'c']
```

### 10.6 includes()

#### 10.6.1 作用

- 表示某个数组是否包含给定的值，返回布尔值

#### 10.6.2 参数

- 第一个参数需要搜索的值
- 第二个参数开始搜索的位置

```javascript
[1, 2, 3].includes(3, 3);  // false
[1, 2, 3].includes(3, -1); // true
```

### 10.7 flat()|flatMap()

#### 10.7.1 作用

- flat():用于将嵌套的数组“拉平”，变成一维的数组。该方法返回一个新数组，对原数据没有影响
- flat():如果不管有多少层嵌套，都要转成一维数组，可以用`Infinity`关键字作为参数。
- flat():如果原数组有空位，`flat()`方法会跳过空位。
- `flatMap()`方法对原数组的每个成员执行一个函数（相当于执行`Array.prototype.map()`），然后对返回值组成的数组执行`flat()`方法。该方法返回一个新数组，不改变原数组。
- `flatMap()`只能展开一层数组。

#### 10.7.2 参数

- 参数代表需要拉平的层数，默认是1

```javascript
[1, 2, [3, [4, 5]]].flat()
// [1, 2, 3, [4, 5]]
[1, 2, [3, [4, 5]]].flat(2)
// [1, 2, 3, 4, 5]
[1, 2, , 4, 5].flat()
// [1, 2, 4, 5]
```

## 第十二章 代理(Proxy)和反射(Reflection)

### 12.1 Proxy

#### 12.1 定义及参数

> **Proxy** 可以理解成，在目标对象之前架设一层“拦截”，外界对该对象的访问，都必须先通过这层拦截，因此提供了一种机制，可以对外界的访问进行过滤和改写。Proxy 这个词的原意是代理，用在这里表示由它来“代理”某些操作，可以译为“代理器”。

> **Proxy** 对象用于创建一个对象的代理，从而实现基本操作的拦截和自定义（如属性查找、赋值、枚举、函数调用等），被代理的对象可以是任何类型的对象，包括原生数组、函数、甚至是另一个代理

```javascript
//target:要使用 Proxy 包装的目标对象
//handler:一个通常以函数作为属性的对象，各属性中的函数分别定义了在执行各种操作时代理 p 的行为。
const p = new Proxy(target, handler)
```

#### 12.2 Proxy.revocable()

> `**Proxy.revocable()**` 方法可以用来创建一个可撤销的代理对象。

##### 12.2.1 语法以及参数

```javascript
//target:用Proxy封装的目标对象，可以是任何类型的对象，包括原生数组、函数，代理对象
//handler:一个通常以函数作为属性的对象，各属性中的函数分别定义了在执行各种操作时的行为。
let {proxy, revoke} = Proxy.revocable(target, handler);
```

##### 12.2.1 返回值

```javascript
//proxy:表示新生成代理对象本身，和new Proxy创建的代理对象没有区别，只是它可以被撤销
//revoke:它表示撤销的方法， 调用时不需要参数，可以直接撤销调和它一起生成的代理对象，当执行revoke函数之后，再访问proxy代理对象会抛错
let target = {};
let handler = {};

let {proxy, revoke} = Proxy.revocable(target, handler);

proxy.foo = 123;
proxy.foo // 123

revoke();
proxy.foo // TypeError: Revoked
```

##### 12.2.3 使用场景

> `Proxy.revocable()`的一个使用场景是，目标对象不允许直接访问，必须通过代理访问，一旦访问结束，就收回代理权，不允许再次访问。

#### 12.3 handler 对象的方法

##### 12.3.1 get()方法

###### 12.3.1.1 概念

`get`方法用于拦截某个属性的读取操作，可以接受三个参数，依次为目标对象、属性名和 proxy 实例本身（严格地说，是操作行为所针对的对象），其中最后一个参数可选，返回任意值；

###### 12.3.1.2 拦截行为

> get方法一共拦截几种行为：

- 访问属性: `proxy[foo]和` `proxy.bar`；

- 访问原型链上的属性: `Object.create(proxy)[foo]`；

- `Reflect.get()`

- ```javascript
  var person = {
    name: "张三"
  };
  
  var proxy = new Proxy(person, {
    get: function(target, propKey) {
      if (propKey in target) {
        return target[propKey];
      } else {
        throw new ReferenceError("Prop name \"" + propKey + "\" does not exist.");
      }
    }
  });
  
  proxy.name // "张三"
  proxy.age // 抛出一个错误
  let obj = Object.create(proto);
  obj.name // "张三"
  ```

###### 12.3.1.3 约束行为

> 如果违背了以下的约束，proxy会抛出 `TypeError`:

- 如果要访问的目标属性是不可写以及不可配置的，则返回的值必须与该目标属性的值相同;

- 如果要访问的目标属性没有配置访问方法，即get方法是undefined的，则返回值必须为undefined。

- ```javascript
  var obj = {};
  Object.defineProperty(obj, "a", {
    configurable: false,
    enumerable: false,
    value: 10,
    writable: false
  });
  
  var p = new Proxy(obj, {
    get: function(target, prop) {
      return 20;
    }
  });
  
  p.a; //会抛出TypeError
  ```

##### 12.3.2 set()方法

###### 12.3.2.1 概念

`set`方法用来拦截某个属性的赋值操作，可以接受四个参数，依次为目标对象、属性名、属性值和 Proxy 实例本身，其中最后一个参数可选,，返回布尔值

###### 12.3.2.2 拦截行为

>  set方法一共拦截几种行为：

- 指定属性值：`proxy[foo] = bar` 和 `proxy.foo = bar`

- 指定继承者的属性值：`Object.create(proxy)[foo] = bar`                                                                         

- `Reflect.set()`

- ```javascript
  let validator = {
    set: function(obj, prop, value) {
      if (prop === 'age') {
        if (!Number.isInteger(value)) {
          throw new TypeError('The age is not an integer');
        }
        if (value > 200) {
          throw new RangeError('The age seems invalid');
        }
      }
  
      // 对于满足条件的 age 属性以及其他属性，直接保存
      obj[prop] = value;
    }
  };
  
  let person = new Proxy({}, validator);
  
  person.age = 100;
  
  person.age // 100
  person.age = 'young' // 报错
  person.age = 300 // 报错
  ```

###### 12.3.2.3 约束行为

> 如果违背以下的约束条件，proxy 会抛出一个 `TypeError` 异常：

- 若目标属性是一个不可写及不可配置的数据属性，则不能改变它的值。

- 如果目标属性没有配置存储方法，即 `[[Set]]` 属性的是 `undefined`，则不能设置它的值。

- 在严格模式下，如果 `set()` 方法返回 `false`，那么也会抛出一个 `TypeError`异常。

- ```javascript
  const obj = {};
  Object.defineProperty(obj, 'foo', {
    value: 'bar',
    writable: false,
  });
  
  const handler = {
    set: function(obj, prop, value, receiver) {
      obj[prop] = 'baz';
    }
  };
  
  const proxy = new Proxy(obj, handler);
  proxy.foo = 'baz';
  proxy.foo // "bar"
  
  'use strict';
  const handler = {
    set: function(obj, prop, value, receiver) {
      obj[prop] = receiver;
      // 无论有没有下面这一行，都会报错
      return false;
    }
  };
  const proxy = new Proxy({}, handler);
  proxy.foo = 'bar';
  // TypeError: 'set' on proxy: trap returned falsish for property 'foo'
  ```

##### 12.3.3 construct()方法

###### 12.3.3.1 概念

`**handler.construct()**` 方法用于拦截new操作符. 为了使new操作符在生成的Proxy对象上生效，用于初始化代理的目标对象自身必须具有[[Construct]]内部方法（即 `new target` 必须是有效的），construct()`方法可以接受三个参数。

- `target`：目标对象。
- `args`：构造函数的参数数组。
- `newTarget`：创造实例对象时，`new`命令作用的构造函数
- 返回一个对象

###### 12.3.3.2 拦截行为

> 用于拦截new操作符

- `new proxy(...args)`

- `Reflect.construct()`

- ```javascript
  var p = new Proxy(function() {}, {
    construct: function(target, argumentsList, newTarget) {
      console.log('called: ' + argumentsList.join(', '));
      return { value: argumentsList[0] * 10 };
    }
  });
  
  console.log(new p(1).value); // "called: 1"
                               // 10
  ```

###### 12.3.3.3 约束行为

如果违反以下约定，代理将会抛出错误 `TypeError`：

- 必须返回一个对象.

- ```javascript
  var p = new Proxy(function() {}, {
    construct: function(target, argumentsList, newTarget) {
      return 1;
    }
  });
  
  new p(); // TypeError is thrown
  ```

##### 12.3.4 其他方法

> 其他方法未列出，具体用到时看文档

### 12.2 Reflect

#### 12.2.1 定义以及参数

> **Reflect** 是一个内置的对象,`Reflect`不是一个函数对象，因此它是不可构造的;`Reflect`对象的设计目的有这样几个:

- 将`Object`对象的一些明显属于语言内部的方法（比如`Object.defineProperty`），放到`Reflect`对象上。现阶段，某些方法同时在`Object`和`Reflect`对象上部署，未来的新方法将只部署在`Reflect`对象上。也就是说，从`Reflect`对象上可以拿到语言内部的方法;

- 修改某些`Object`方法的返回结果，让其变得更合理。比如，`Object.defineProperty(obj, name, desc)`在无法定义属性时，会抛出一个错误，而`Reflect.defineProperty(obj, name, desc)`则会返回`false`

- 让`Object`操作都变成函数行为。某些`Object`操作是命令式，比如`name in obj`和`delete obj[name]`，而`Reflect.has(obj, name)`和`Reflect.deleteProperty(obj, name)`让它们变成了函数行为

- `Reflect`对象的方法与`Proxy`对象的方法一一对应，只要是`Proxy`对象的方法，就能在`Reflect`对象上找到对应的方法。这就让`Proxy`对象可以方便地调用对应的`Reflect`方法，完成默认行为，作为修改行为的基础。也就是说，不管`Proxy`怎么修改默认行为，你总可以在`Reflect`上获取默认行为

- ```javascript
  // 老写法
  try {
    Object.defineProperty(target, property, attributes);
    // success
  } catch (e) {
    // failure
  }
  
  // 新写法
  if (Reflect.defineProperty(target, property, attributes)) {
    // success
  } else {
    // failure
  }
  
  // 老写法
  'assign' in Object // true
  
  // 新写法
  Reflect.has(Object, 'assign') // true
  
  // 老写法
  Function.prototype.apply.call(Math.floor, undefined, [1.75]) // 1
  
  // 新写法
  Reflect.apply(Math.floor, undefined, [1.75]) // 1
  ```

## 字符串扩展

```javascript
const msg = 'I am a girl'
msg.startsWith('I')//true,以某字符串开头，返回布尔值
msg.endsWith('girl')//true,以字符串结尾，返回布尔值
msg.includes('girl')//是否包含某个字符串，返回布尔值
```



## 模板字符串

### 带标签的模板字符串

> 对模板字符串加工

```javascript
const name = 'mxm',age = 18
//strings表示模板字符串中被变量分隔字符的数组，其余参数依次是变量
const getInfo = (strings,name,age)=>{
  return strings[0]+name+strings[1]+age
}
const result = getInfo`我是${name}，年龄${age}`
console.log("result",result)//我是mxm，年龄18
```

## 对象扩展

- Object.is(value1,value2):比较两个值在是否相等，返回布尔值，具体值比较参考https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/is

## 第十三章 Set 和 Map 数据结构

### 13.1 Set

#### 13.1.1 定义

- 它类似于数组，但是成员的值都是唯一的，成员的值可以是任意的类型，没有重复的值，key与value相同
- Set 结构的实例默认可遍历，它的默认遍历器生成函数就是它的`values`方法，这意味着，可以省略`values`方法，直接用`for...of`循环遍历 Set
- Set 结构的实例与数组一样，也拥有`forEach`方法，用于对每个成员执行某种操作，没有返回值

#### 13.1.2 api

- Set():`Set`函数可以接受一个数组（或者具有 iterable 接口的其他数据结构）作为参数，用来初始化

  ```javascript
  const set = new Set();
  const items = new Set([1, 2, 3, 4, 5, 5, 5, 5]);
  const set = new Set(document.querySelectorAll('div'));
  const a = new Set('ababbc')
  ```

- add(value):添加某个值，返回 Set 结构本身,向 Set 加入值，不会发生类型转换，NaN与NaN是相等的值

  ```javascript
  let set = new Set();
  let a = NaN;
  let b = NaN;
  set.add(a);
  set.add(b);
  ```

- size():返回`Set`实例的成员总数

  ```javascript
  const s = new Set()
  s.add(1).add(2).add(2);
  s.size // 2
  ```

- has(value)：返回一个布尔值，表示该值是否为`Set`的成员。

  ```javascript
  const s = new Set()
  s.add(1).add(2).add(2);
  s.has(2)//true
  s.has(3)//false
  ```

- clear()：清除所有成员，没有返回值

  ```javascript
  s.has(3)//false
  ```

- keys()：获取成员的key

  ```javascript
  for (let item of set.keys()) {
    console.log(item);
  }
  ```

- values()：获取成员的values,Set 结构的实例默认可遍历，它的默认遍历器生成函数就是它的`values`方法，这意味着，可以省略`values`方法，直接用`for...of`循环遍历 Set

  ```javascript
  for (let item of set.values()) {
    console.log(item);
  }

- entries():获取成员的key与value

  ```javascript
  for (let item of set.entries()) {
    console.log(item);//['key','value']
  }
  ```

- 同步改变原来的 Set 结构,基本思想就是先变成数组，之后更改结构，在变成Set结构

  ```javascript
  let set = new Set([1, 2, 3]);
  set = new Set([...set].map(val => val * 2));
  
  let set = new Set([1, 2, 3]);
  set = new Set(Array.from(set, val => val * 2));

#### 13.1.3 实践功能

- 数组去重

  ```javascript
  const arr = [...new Set([1,2,3,4,4,5,6,6])]
  
  const items = new Set([1, 2, 3, 4, 5,6,6]);
  const array = Array.from(items);
  ```

- 字符串去重

  ```javascript
  const a = [...new Set('ababbc')].join('')
  ```

- set转数组

  ```javascript
  const arr = [...new Set([1,2,3,4,4,5,6,6])]
  
  const items = new Set([1, 2, 3, 4, 5]);
  const array = Array.from(items);
  ```

- 数组的并集，字符串并集和数字组并集一样的原理

  ```javascript
  const a = [1,2,3,4]
  const b = [2,3,4,5,6]
  const c = [...new Set(...a,...b)] 
  ```

- 数组的交集，字符串交集和数字组交集一样的原理

  ```javascript
  const a = [1,2,3,4]
  const b = [2,3,4,5,6]
  const c = a.filter(v=>new Set(b).has(a))
  ```

- 数组的差集，字符串差集和数字组差集一样的原理

  ```javascript
  const a = [1,2,3,4]
  const b = [2,3,4,5,6]
  const c = a.filter(v=>!new Set(b).has(a))
  ```

### 13.2 WeakSet

#### 13.2.1 定义

- WeakSet也是不重复成员的组合
- WeakSet的成员只能是对象，不能是基本类型
- WeakSet存放的成员属于弱引用类型，即垃圾回收机制不会考虑在WeakSet的引用，如果除WeakSet中的引用，无其他引用，则该变量会直接被回收，这样的主要好处就是不会导致内存泄漏
- 由于WeakSet成员有可能随时被垃圾回收，因此不能进行遍历

#### 13.2.2 api

- WeakSet():WeakSet 可以接受一个数组或类似数组的对象作为参数。（实际上，任何具有 Iterable 接口的对象，都可以作为 WeakSet 的参数。）该数组的所有成员，都会自动成为 WeakSet 实例对象的成员

  ```javascript
  const a = [[1, 2], [3, 4]];
  const ws = new WeakSet(a);
  // WeakSet {[1, 2], [3, 4]}
  ```

- add(value):向 WeakSet 实例添加一个新成员

  ```javascript
  const ws = new WeakSet();
  ws.add({})
  ```

- delete(value):清除 WeakSet 实例的指定成员

  ```javascript
  const ws = new WeakSet();
  ws.add(window);
  ws.delete(window);
  ```

- has(value)：返回一个布尔值，表示某个值是否在 WeakSet 实例之中

  ```javascript
  const ws = new WeakSet();
  ws.add(window);
  ws.has(window)//true
  ```

13.2.3 实践功能

- WeakSet 的一个用处，是储存 DOM 节点，而不用担心这些节点从文档移除时，会引发内存泄漏

### 13.3 Map

#### 13.3.1 定义

- 它类似于对象，也是键值对的集合，但是“键”的范围不限于字符串，各种类型的值（包括对象）都可以当作键；
- 无重复的键值
- Object 结构提供了“字符串—值”的对应，Map 结构提供了“值—值”的对应，是一种更完善的 Hash 结构实现；
- 如果 Map 的键是一个简单类型的值（数字、字符串、布尔值），则只要**两个值严格相等**，Map 将其视为一个键，比如`0`和`-0`就是一个键，布尔值`true`和字符串`true`则是两个不同的键。另外，`undefined`和`null`也是两个不同的键。虽然`NaN`不严格相等于自身，但 Map 将其视为同一个键
- 如果你需要“键值对”的数据结构，Map 比 Object 更合适；

#### 13.3.2 api

- Map(value):Map可以接受一个数组作为参数，该数组的成员是一个个表示键值对的数组；任何具有 Iterator 接口、且每个成员都是一个双元素的数组的数据结构都可以当作`Map`构造函数的参数。这就是说，`Set`和`Map`都可以用来生成新的 Map

  ```javascript
  const map = new Map([
    ['name', '张三'],
    ['title', 'Author']
  ]);
  
  map.size // 2
  map.has('name') // true
  map.get('name') // "张三"
  map.has('title') // true
  map.get('title') // "Author"
  
  //Map构造函数接受数组作为参数，实际上执行的是下面的算法
  const items = [
    ['name', '张三'],
    ['title', 'Author']
  ];
  
  const map = new Map();
  
  items.forEach(
    ([key, value]) => map.set(key, value)
  );
  ```

- size():Map的大小

- set(key, value):设置map成员，返回的是当前的`Map`对象，因此可以采用链式写法

- get(key)：获取成员的值，`get`方法读取`key`对应的键值，如果找不到`key`，返回`undefined`

- has(key)：`has`方法返回一个布尔值，表示某个键是否在当前 Map 对象之中

- delete(key):delete`方法删除某个键，返回`true`。如果删除失败，返回`false

- clear():清空

- 遍历方法同set的方法

#### 13.3.3 使用场景

- Map转数组,比较快速的方法是使用扩展运算符（`...`）

  ```javascript
  const map = new Map([
    [1, 'one'],
    [2, 'two'],
    [3, 'three'],
  ]);
  
  [...map.keys()]
  // [1, 2, 3]
  
  [...map.values()]
  // ['one', 'two', 'three']
  
  [...map.entries()]
  // [[1,'one'], [2, 'two'], [3, 'three']]
  
  [...map]
  // [[1,'one'], [2, 'two'], [3, 'three']]
  ```

- Map 转为对象:如果所有 Map 的键都是字符串，它可以无损地转为对象

  ```javascript
  function strMapToObj(strMap) {
    let obj = Object.create(null);
    for (let [k,v] of strMap) {
      obj[k] = v;
    }
    return obj;
  }
  
  const myMap = new Map()
    .set('yes', true)
    .set('no', false);
  strMapToObj(myMap)
  // { yes: true, no: false }
  ```

- 对象转为 Map

  ```javascript
  let obj = {"a":1, "b":2};
  let map = new Map(Object.entries(obj));
  
  
  
  function objToStrMap(obj) {
    let strMap = new Map();
    for (let k of Object.keys(obj)) {
      strMap.set(k, obj[k]);
    }
    return strMap;
  }
  
  objToStrMap({yes: true, no: false})
  // Map {"yes" => true, "no" => false}
  
  ```

### 13.4 WeakMap

- WeakMap原理同WeakSet
- `WeakMap`只接受对象作为键名（`null`除外），不接受其他类型的值作为键名

## 第十三章 Module语法

### 问题记录

- <font color="red">Cannot use import statement outside a module</font>

  ```javascript
  在运行js文件中，使用es6的export导出模块报以上错误
  import CreateBinaryTree from '../ArrToTree.js'
  var flipMatchVoyage = function(root, voyage) {}
  解决过程：
  npm init -y
  在 package.json 中添加字段 type
  {
    "name": "Algorithm-to-develop",
    "version": "1.0.0",
    "description": "算法养成",
    "main": "index.js",
    "type": "module",
    "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
    },
    "repository": {
      "type": "git",
      "url": "git+https://github.com/mxmxixixi/Algorithm-to-develop.git"
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "bugs": {
      "url": "https://github.com/mxmxixixi/Algorithm-to-develop/issues"
    },
    "homepage": "https://github.com/mxmxixixi/Algorithm-to-develop#readme"
  }
  
  ```

## 第十六章 异步编程

> 在JavaScript中属于单线程模式执行，主要原因是运行在浏览器端对dom进行操作，如果存在多线程，则会对dom操作造成不确定性，例如：一个线程改变dom的样色为红色，另一个线程改变dom点的样式为绿色，多线程模式下则会同时更改，最后页面呈现效果无法预知，使用单线程模式就可以解决此问题，两个线程是能按照顺序执行，优先:简单、安全，缺点：如果遇到一个时间执行较长的任务，后面的任务需要等待，出现假死的情况

### 16.1 同步模式

> 代码中的任务依次执行，后一个任务必须等待前一个任务结束后开始执行，程序执行顺序与代码书写顺序相同，所有任务都会放入调用栈中，执行后从栈中移除，同步模式会产生阻塞现象，所以有异步模式的出现

### 16.2 异步模式

>  异步模式执行策略，任务中遇到同步任务直接进入调用栈(Call stack)，遇到异步任务也放入调用栈中，但是异步执行的api放入webApi中，之后调用栈异步任务移除，webApi中的任务设置时间后进入消息队列(queue)时，使用event loop监听调用栈与队列，当调用栈中无任务时把消息队列中任务放入调用栈进行执行

![image-20210225104225836](/Users/naebunsakai/study/notes/imgs/异步调用栈.png)

#### 16.2.1 Promise

> 为了解决异步回调地狱，COMMON JS提出了Promise，在es2015中被标准化，成为语言规范

##### 概念

> Promise是一个对象，表示异步任务最后的结果，是成功还是失败，不同结果对应不同的处理函数，**状态只更改一次，更改后不再改变**，Promise构造函数不是异步的函数，then方法，catch方法是异步函数

##### 链式调用

> 使用链式调用的原理是每个then中都会返回一个全新的Promise，所以可以继续使用then方法，如果返回的值是不是Promise，则在then中直接作为结果展示，如果没有返回任何值，则默认是undefined

##### 异常处理

> 链式调用中失败会走catch方法，所有Promise的错误会向下传递，所以catch是捕获的前一个Promise，而不是调用的第一个Promise，能捕获到信息，是因为错误信息会向下传递，catch还能捕获到resolve后执行函数里面的错误信息

##### 静态方法

```javascript
Promise.resolve('foo')
Promise.reject('foo')
```

##### 并行执行

```javascript
Promise.all([])//状态不定：所有Promise都成功，才会进入resolve，只要有一个失败，就会进入reject
Promise.allSettled([])//状态固定(成功):所有Promise完成后，该方法返回的新的 Promise 实例，一旦结束，状态总是成功，不会根据任务的状态返回不同的状态
Promise.race([])//状态不定：有Promise任务完成，则结果变成任务的状态
Promise.any([])//状态不定：要参数实例有一个变成成功状态，包装实例就会变成成功状态；如果所有参数实例都变成失败状态，包装实例就会变成失败状态。使用场景：从最快的服务器检索资源，显示第一张已加载的图片
```

##### 执行时序

- 宏任务：需要进行排队，一般异步任务都是宏任务;script` 、`setTimeout`、`setInterval` 、`setImmediate` 、`I/O` 、`UI rendering` 、 `postMessage` 、 `MessageChannel
- 微任务：不需要进行排队，直接进入微任务队列，promise.then是微任务;`MutationObserver`、`Promise.then()或catch()`、`Promise为基础开发的其它技术，比如fetch API`、`V8`的垃圾回收过程、`Node独有的process.nextTick` 、 `Object.observe`（已废弃；`Proxy` 对象替代）

##### 手写Promise

> 主要完成以下几点功能，按照功能的顺序进行实现

- Promise共有三种状态：pending，fulfilled，rejected，通过resolve，reject方法来更换状态
- resolve方法把pending状态变成fulfilled状态，reject方法把pending状态变成rejected状态
- 在异步函数中调用resolve、reject方法时，then方法需要放入缓存队列中，resolve、reject调用时执行缓存队列中的函数
- then方法可以连续调用，也就是需要放到缓存队列中，then方法可以实现链式调用，也就是then方法返回一个Promise，返回的Promise不能是自己
- 使用静态方法实现Promise.resolve()、Promise.rejected()、返回的值也是Promise
- resolve、reject、then方法需要进行容错处理，使用try{}catch(){}
- 使用queueMicrotask进行创建微任务
- finally主要的特点是无论成功还是失败都会走一遍，它是then的语法糖，直接调用then方法就可以
- catch 方法是 then 方法的语法糖，只接受 rejected 态的数据。

```javascript
const PENDING = 'pending';
const FULFILLED = 'fulfilled';
const REJECTED = 'rejected'
class MyPromise {
  constructor(fun) {
    try {
      fun(this.resolve, this.reject)
    } catch (error) {
      this.reject(error)
    } 
  }
  status = PENDING
  value = null
  reason = null
  onFulfilledCallBack = []
  onRejectedCallBack = []
  resolve = (value) => {
    if (this.status === PENDING) {
      this.status = FULFILLED
      this.value = value
      if (this.onFulfilledCallBack.length) {
        this.onFulfilledCallBack.forEach(v => {
          v(value)
        })
      }
    }
  }
  reject = (reason) => {
    if (this.status === PENDING) {
      this.status = REJECTED
      this.reason = reason
      if (this.onRejectedCallBack.length) {
        this.onRejectedCallBack.forEach(v => {
          v(reason)
        })
      }
    }
  }
  then = (onFulfilled: Function = (value) => value, onRejected: Function = (reason) => reason) => {
    const promiseNew = new MyPromise((resolve, reject) => {
      if (this.status === PENDING) {
        this.onFulfilledCallBack.push(() => {
          queueMicrotask(() => {
            try {
              const thenReturn = onFulfilled(this.value)
              this.resolvePromise(thenReturn, promiseNew, resolve, reject)
            } catch (error) {
              reject(error)
            }
          })
        })
        this.onRejectedCallBack.push(() => {
          queueMicrotask(() => {
            try {
              const thenReturn = onRejected(this.reason)
              this.resolvePromise(thenReturn, promiseNew, resolve, reject)
            } catch (error) {
              reject(error)
            }
          })
        })
      }
      if (this.status === FULFILLED) {
        queueMicrotask(() => {
          try {
            const thenReturn = onFulfilled(this.value)
            this.resolvePromise(thenReturn, promiseNew, resolve, reject)
          } catch (error) {
            reject(error)
          }
        })
      }
      if (this.status === REJECTED) {
        queueMicrotask(() => {
          try {
            const thenReturn = onRejected(this.reason)
            this.resolvePromise(thenReturn, promiseNew, resolve, reject)
          } catch (error) {
            reject(error)
          }
        })
      }
    })
    return promiseNew
  }
  resolvePromise = (thenReturn, promiseNew, resolve, reject) => {
    if (thenReturn === promiseNew) {
      reject(new TypeError('#<Promise> no same'))
    }
    if (thenReturn instanceof MyPromise) {
      thenReturn.then(resolve, reject)
    } else {
      resolve(thenReturn)
    }
  }
  static resolve = (value) => {
    if (value instanceof MyPromise) {
      return value
    }
    return new MyPromise((resolve) => {
      resolve(value)
    })
  }
  static reject = (reason) => {
    return new MyPromise((resolve, reject) => {
      reject(reason)
    })
  }
  finally = (callBack)=>{
    return this.then((value)=>{
      return  MyPromise.resolve(callBack()).then(() => value)
    },(reason)=>{
      return  MyPromise.reject(callBack()).then(() => reason)
    })
  }
  catch = (callBack) => {
    return this.then(null,callBack)
  }
}
```

##### 手写Promise.all

- 入参是一个数组，数组的每一项都是Promise
- 返回是一个Promise,任意一个 `promise` 被 `reject` ，就会立即被 `reject` ，并且 `reject` 的是第一个抛出的错误信息，只有所有的 `promise` 都 `resolve` 时才会 `resolve` 所有的结果
- 只有所有的Promise都成功返回成功状态的Promise，否则返回失败状态的Promise

```tsx
Promise.all = (promises) => {
  if(!(promises instanceof Array)){
    return Promise.reject(new TypeError('arr must be an array.'))
  }
  return new Promise((resolve,reject)=>{
    const resolvedData = []
    promises.forEach((v,index)=>{
      v.then((result)=>{
        resolvedData.push(result)
      }).catch(error=>{
        reject({message:error,index})
      })
    })
    if(resolvedData.length === promises.length){
      resolve(resolvedData)
    }
  })
}
```

##### 手写Promise.any

- 入参是一个数组，数组的每一项都是Promise
- 返回是一个Promise,任意一个 `promise` 被 `resolve` ，就会立即被 `resolve` ，并且 `resolve` 的是第一个正确结果，只有所有的 `promise` 都 `reject` 时才会 `reject` 所有的失败信息
- 只要有一个Promise返回状态为成功，则返回成功的Promise，否则返回失败的Promise

```tsx
Promise.any = (promises) => {
  if(!(promises instanceof Array)){
    return Promise.reject(new TypeError('arr must be an array.'))
  }
  return new Promise((resolve,reject)=>{
    const rejectedData = []
    promises.forEach((v,index)=>{
      v.then((result)=>{
        resolve(result)
      }).catch(error=>{
        rejectedData.push(error)
      })
    })
    if(rejectedData.length === promises.length){
      reject(rejectedData)
    }
  })
}
```

##### 手写Promise.race

- 入参是一个数组，数组的每一项都是Promise
- 返回是第一个有结果的Promise

```tsx
Promise.race = (promises) => {
  if(!(promises instanceof Array)){
    return Promise.reject(new TypeError('arr must be an array.'))
  }
  return new Promise((resolve,reject)=>{
    promises.forEach((v,index)=>{
      v.then((result)=>{
        resolve(result)
      }).catch(error=>{
        reject(error)
      })
    })
  })
}
```

##### 事件循环

- 基本执行过程
  - 首先执行 `script` 宏任务
  - 执行同步任务，遇见微任务进入微任务队列，遇见宏任务进入宏任务队列
  - 当前宏任务执行完出队，检查微任务列表【微任务优先执行】，有则依次执行，直到全部执行完
  - 执行浏览器 UI 线程的渲染工作
  - 检查是否有`Web Worker`任务，有则执行
  - 执行下一个宏任务，回到第二步，依此循环，直到宏任务和微任务队列都为空

##### 总结

- `Promise` 构造函数是同步执行的， `then` 方法是异步执行的
- `.then` 或者 `.catch` 的参数期望是函数，**传入非函数则会发生值透传，之后then里面的参数会直接执行**
- `Promise`的状态一经改变就不能再改变，构造函数中的 `resolve` 或 `reject` 只有第一次执行有效，多次调用没有任何作用
- `.then`方法是能接收两个参数的，第一个是处理成功的函数，第二个是处理失败的函数，再某些时候你可以认为`catch`是`.then`第二个参数的简便写法
- 当遇到 `promise.then` 时， 如果当前的 `Promise` 还处于 `pending` 状态，我们并不能确定调用 `resolved` 还是 `rejected` ，只有等待 `promise` 的状态确定后，再做处理，所以我们需要把我们的两种情况的处理逻辑做成 `callback` 放入 `promise` 的回调数组内，当 `promise` 状态翻转为 `resolved`时，才将之前的 `promise.then` 推入微任务队列

### 16.3 回调函数

> 由调用者定义，交给执行者执行的函数，是所有异步函数的基础

### 16.4 Generator

> generator是解决异步编程的方案

## Symbol

### 概述

> 为一个对象添加属性时，保证属性名不冲突，es6中引入了`symbol原始类型`，使对象中的属性名是一个独一无二的值；所有对象的属性名有两种类型：字符串与symbol；symbol是原始类型不能添加属性，它是类似于字符串的数字类型；symbol可以接收一个字符串作为参数，表示对symbol的描述，symbol是基本数据类型

```javascript
let s1 = Symbol("dog")
let s2 = Symbol("cat")
console.log('s',s1,s2)//Symbol("dog"),Symbol("cat")
s1 === s2 //false
//symbol参数是对象时，会调用对象的tostring()的方法
const obj = {
  toString() {
    return 'abc';
  }
};
const sym = Symbol(obj);
sym // Symbol(abc)
//Symbol 值不能与其他类型的值进行运算,可以转为string类型、boolean类型
let s3 = Symbol("string")
String(s3)
s3.toString()
Boolean(s3)
```

### 获取描述

> 传给Symbol的参数就是对Symbol的描述

```javascript
let s = Symbol('describe')
s.description//describe
```

### 属性名的遍历

```javascript
let s1 = Symbol('key1')
let s2 = Symbol('key2')
const obj = {[s1]:1,[s2]:2,key3:3}
for (key in obj){
	console.log(key)//'key3'
}
for(key of obj){
  console.log(key)//'key3'
}
Object.keys(obj)//['key3']
Object.getOwnPropertyNames(obj)//["key3"]
JSON.stringify(obj)//"{"key3":3}"
Object.getOwnPropertySymbols(obj)//[Symbol('key1'),Symbol('key2')]
Reflect.ownKeys(obj)//[Symbol('key1'),Symbol('key2'),'key3']
```

### Symbol.for()、Symbol.keyFor()

> Symbol.for():它接受一个字符串作为参数，然后搜索有没有以该参数作为名称的 Symbol 值。如果有，就返回这个 Symbol 值，否则就新建一个以该字符串为名称的 Symbol 值，<font color="red">并将其注册到全局</font> ,可以用在不同的 iframe 或 service worker 中取到同一个值。

```javascript
let  s1 = Symbol.for('foo');
let  s2 = Symbol.for('foo');
s1 === s2 //true
```

> Symbol.keyFor():返回一个已登记的 Symbol 类型值的`key`

```javascript
let s1 = Symbol.for("foo");
Symbol.keyFor(s1) // "foo"

let s2 = Symbol("foo");
Symbol.keyFor(s2) // undefined
```

### 模块的 Singleton 模式

> 暂时无记录

### 内置的 Symbol 值

> 暂时无记录

## 可选链

## 第二十一 Class 的继承

> extends实现思想和寄生组合式继承一样

# ECMAScript2017(Es8)

## Async

- async 函数是 Generator 函数的语法糖
- `async`函数就是将 Generator 函数的星号（`*`）替换成`async`，将`yield`替换成`await`，仅此而已
- async与await配套使用
- `async`函数对 Generator 函数的改进，体现在以下四点
  - 内置执行器:不需要yield一步一步执行
  - 更好的语义:`async`和`await`，比起星号和`yield`，语义更清楚了。`async`表示函数里有异步操作，`await`表示紧跟在后面的表达式需要等待结果
  - 更广的适用性
  - `async`函数的返回值是 Promise 对象
- 当函数执行的时候，一旦遇到`await`就会先返回，等到异步操作完成，再接着执行函数体内后面的语句
- `async`函数返回的 Promise 对象，必须等到内部所有`await`命令后面的 Promise 对象执行完，才会发生状态改变，除非遇到`return`语句或者抛出错误。也就是说，只有`async`函数内部的异步操作执行完，才会执行`then`方法指定的回调函数。
- `await`命令后面是一个 Promise 对象，返回该对象的结果。如果不是 Promise 对象，就直接返回对应的值
- `await`命令只能出现在 async 函数内部，否则都会报错

# ECMAScript2018(Es9)

## Promise.prototype.finally()

- 返回一个 `Promise` ，在 `promise` 结束时，无论 `Promise` 运行成功还是失败，都会运行 `finally` ，类似于我们常用的  `try {...} catch {...} finally {...}`
- `Promise.prototype.finally()` 避免了同样的语句需要在 `then()` 和 `catch()` 中各写一次的情况
- `finally` 没有参数
- `finally` 会将结果和 error 传递

# ECMAScript2021(Es12)

## String.prototype.replaceAll()

- 返回一个全新的字符串，所有符合匹配规则的字符都将被替换掉

  ```javascript
  const str = 'abcdeabcde';
  str.replaceAll('a', '-'); // '-bcde-bcde'
  ```

## Promise.any()

- 定义

  - 与Promise.race([])类似，Promise.race([])的返回状态不定：有Promise任务**完成**（完成代表接口已经请求完成，不代表接口请求成功），则结果变成任务的状态
  - Promise.any():只要其中的一个 promise 成功，就返回那个已经成功的 promise，对第一个实现感兴趣。相反的情况（所有拒绝）导致拒绝
  - Promise.any():如果可迭代对象中没有一个 promise 成功（即所有的 promises 都失败/拒绝），就返回一个失败的 promise

- 应用场景

  - 从最快的服务器检索资源：来自世界各地的用户访问网站，如果你有多台服务器，则尽量使用响应速度最快的服务器，在这种情况下，可以使用 `Promise.any()` 方法从最快的服务器接收响应

  - 显示第一张已加载的图片

    ```javascript
     function fetchAndDecode(url) {
        return fetch(url).then(response => {
          if(!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
          } else {
            return response.blob();
          }
        })
      }
      
      let coffee = fetchAndDecode('coffee.jpg');
      let tea = fetchAndDecode('tea.jpg');
      
      Promise.any([coffee, tea]).then(value => {
        let objectURL = URL.createObjectURL(value);
        let image = document.createElement('img');
        image.src = objectURL;
        document.body.appendChild(image);
      })
      .catch(e => {
        console.log(e.message);
      });
    ```

- 手写 Promise.any 实现

  ```javascript
  MyPromise.any = function(promises){
    return new Promise((resolve,reject)=>{
      promises = Array.isArray(promises) ? promises : []
      let len = promises.length
      // 用于收集所有 reject 
      let errs = []
      // 如果传入的是一个空数组，那么就直接返回 AggregateError
      if(len === 0) return reject(new AggregateError('All promises were rejected'))
      promises.forEach((promise)=>{
        promise.then(value=>{
          resolve(value)
        },err=>{
          len--
          errs.push(err)
          if(len === 0){
            reject(new AggregateError(errs))
          }
        })
      })
    })
  }
  ```

  

## WeakRef

- 可以通过 `WeakRef` 类来给某个对象创建一个弱引用
- 可以通过 `FinalizationRegistry` 类，在某个对象被垃圾回收之后，执行一些自定义方法
- 一个 `WeakRef` 对象包含一个对于某个对象的弱引用，被称为 *目标* 或 *引用*。通过弱引用一个对象，可以让该对象在没有其它引用的情况下被垃圾回收机制回收。
- `WeakRef` 主要用来 **缓存** 和 **映射** 一些大型对象，当你希望某个对象在不被其它地方引用的情况下及时地被垃圾回收，那么你就可以使用它。

## 逻辑赋值运算符

- 逻辑赋值运算符结合了 **逻辑运算符** 和 **赋值表达式**。逻辑赋值运算符就是两种符号的组合

- 逻辑赋值返回的值不是更新的赋值，而是已计算表达式的值

- 基本逻辑运算符有&  ||  ！ ??

- 逻辑赋值运算符有 ||=、&&=、??=

  ```javascript
  a ||= b
  //等价于
  a || (a = b)
  
  a &&= b
  //等价于
  a && (a = b)
  
  a ??= b
  //等价于
  a ?? (a = b)
  ```

## 数字分隔符

```javascript
const money = 1_000_000_000 // 1000000000
//等价于
const money = 1000000000;
1_000_000_000 === 1000000000; // true
```



# 事件记录

### wheel

```javascript
//禁止浏览器在滚动时出现上下的白边
const func = (e) => { e.preventDefault() }
window.addEventListener('wheel', func, { passive: false })
return () => {
  window.removeEventListener('wheel', func, { passive: false })
}
```