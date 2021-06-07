# JavaScript语言核心

JavaScript对象

```javascript
var book = {
	topic: "JavaScript",
	fat: true
};

//可以通过"."或"[]"来访问对象属性
book.topic
book.["fat"]
book.author = "abaka"	//通过赋值创建一个新的属性
book.contents = {};		//{}是一个空对象，没有属性
```

JavaScript数组

```js
var primes = [1,2,3,4];
primes[1]		//=>2
primes.length	//=>4,数组中的元素个数
primes[primes.length - 1]	//=>4,数组的最后一个元素
primes[4] = 9;	//通过赋值添加新元素
primes[4] = 10;	//通过赋值改变已有元素内容

var empty = [];	//空数组
empty.length	//=> 0
```

数组和对象中都可以包含另一个数组或对象

```js
var points = [	//具有两个元素的数组
	{x: 0, y: 0},//每个元素都是一个对象
	{x: 1, y: 1}
]
var data = {				//一个包含两个属性的对象
	arr1: [[1, 2],[3, 4]],	//每一个属性都是数组
	arr2: [[2, 3],[4, 5]]	//数组的元素也是数组
}
```

```js

var book = {
topic: "JavaScript",
fat: true
};

//可以通过"."或"[]"来访问对象属性
book.topic
book.["fat"]
book.author = "abaka" //通过赋值创建一个新的属性
book.contents = {}; //{}是一个空对象，没有属性
JavaScript数组

var primes = [1,2,3,4];
primes[1] //=>2
primes.length //=>4,数组中的元素个数
primes[primes.length - 1] //=>4,数组的最后一个元素
primes[4] = 9; //通过赋值添加新元素
primes[4] = 10; //通过赋值改变已有元素内容

var empty = []; //空数组
empty.length //=> 0
数组和对象中都可以包含另一个数组或对象

var points = [ //具有两个元素的数组
{x: 0, y: 0},//每个元素都是一个对象
{x: 1, y: 1}
]
var data = { //一个包含两个属性的对象
arr1: [[1, 2],[3, 4]], //每一个属性都是数组
arr2: [[2, 3],[4, 5]] //数组的元素也是数组
}
//函数是一段带有参数的JavaScript代码段，可以多次调用

function plus1(x) {    //定义了名为plus1的一个函数，带有参数x
    return x+1;
}
plus1(y)

var square = function(x) {    //函数是一种值，可以赋值给变量
    return x*x;    
}
当将函数和对象合写在一起时，函数就变成了"方法"；

var a = [];
a.push(1,2,3);    //push()方法

控制语句

function abs(x) {
    if (x >= 0) {
        return x;
    }
        else {
            return -x;
        }
}

function factorial(n) {
    var product = 1;
    while (n > 1) {
        product *= n;
        n--;
    }
    return product;
}

function factorial2(n) {
    var i, product = 1;
    for (i = 2; i <=n; i++)
        peoduct *= i;
    return product;
}

对象的创建和使用

//定义一个构造函数以初始化一个新的Point对象
function Point(x,y) {        //按照惯例，构造函数均以大写字母开始
    this.x = x;            //关键字this指代初始化的实例
    this.y = y;            //将函数参数存储为对象的属性
}

//使用new关键字来创建一个实例
var p = new Point(1,1);

//通过给构造函数的prototype对象赋值
//来给Point对象定义方法
Point.prototype.r = function() {
    return Math.sqrt(
    this.x * this.x + this.y * this.y);
};
//Point的实例对象p(以及所有的Point实例对象)继承了方法r()
p.r()


```

