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

