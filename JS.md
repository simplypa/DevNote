# JAVASCRIPT
---
- 这篇JS文档主要基于，Udemy上的课程总结
### For more Javascript basic visit [[JS_Advance]]

# JAVASCRIPT BASIC
---
## for each function
- anther way to look through an array
```Javascript
let luckyNumbers = [7,15,23,66,91,10,13];

luckyNumbers.forEach(function checkNum(n){
	if (n > 20) {
		console.log(n);
	}
});
//for each function takes one parameter -function
//里面的function我们叫他callback function
// call back function is to execute on each element.
luckyNumbers.forEach(function (n){
	if (n > 20) {
		console.log(n);
	}
});

luckyNumbers.forEach(checkNum);

function checkNum(n){
	if (n > 20) {
		console.log(n);
	}
}

```


## difference between function declaration and **Arrow function Expression**
1. function declaration 有**Hoisting**
2. 在function中, this的用法也会有不一样， function declaration中， this代表这个对象object, 而在arrow function expression中，this代表包裹他的括号所属object，但是包裹它的括号中， object不算。

## DOM (Document Object Model)

---
### nodelist, HTMLCollection, Array(三个很相似)
```Js

//array
let lucky = [15,7,23,14];
//push pop shift unshift 仅可以用在array上
//return HTMLCollection
let secondElement = document.getElementsByClassName("second");

// reutrn Nodelist
let secondQuery = document.querySelectorAll('.second');

```

- HTMLCollection and NodeList has the Length property and index
- array and nodelist can use forEach method, but HTMLCollection cannot.
- querySelectorAll() 因为是Nodelist因为它可以用foreach

### Element Object
---
##### children and childNode Property
- children returns HTML collection
- childNode returns NodeList
- document.querySelectorAll() also returns NodeList
- 常常使用children，而不使用nodelist, 因为nodelist里不但有element标签还有别的

##### parentElement
```js

let myp = document.querySelector("p.second");

console.log(myp.parentElement)
```

##### innerHTML, innerText
```js
let h1 = document.querySelector('h1.myH1');

h1.innerHTML = 'my name is yifan';

h1.innerHTML = '<mark>my name is yifan</mark>';
//innerHTMl不一样的地方在于这里读入可以识别HTML标签

h1.innerText = 'my name is yifan';
//和innerHTML都差不多

```
就相当于
```html
<h1 class = myH1>my name is yifan</h1>
```

##### 加入标签createElement, appendChild

```js
let body = document.querySelector('body');

let myh1 = document.createElement('h1');
myh1.innerText = 'hi I am wilson';

body.appendChild(myh1);


```

##### classList object metheds( add, remove, toggle, contain)
```html
<body>
	<p class = 'blue'>aa  bbb ccccc<p>

	
</body>

```

```css
.red{
	background-color: red;
}

.blue{
	background-color: blue;
}

.blod{
	font-weight: bolder;
}
```

```js
let myP = document.querySelector('p');
console.log(myP.classList);
//tokenlist
//加入CSS 样式（标签应该是class把）
myP.classList.add("red");

//remove就是移除
myP.classList.remove('blue');

//toggle 就是和目前的情况相反的意思，就是说，如果有这个class就删除，如果没有那就加入

myP.classList.toggle("bold");

console.log(myP.classList.contains('yellow'));
//return false


```

##### getAttribute method
```js

//html part
<a href = "www."></a>


let a = document.querySelector("a");
console.log(a.getAttribute("href")); 

```

##### queryselector in element object
```js

//我们知道DOM中的document .querySelectorAll()
let redP = document.querySelectorAll('p.red');
console.log(redP);

//我们还可以用element 来实现queryselector
let section = document.querySelectorAll("section");
let redP = section.querySelectorAll("p.red");


```

##### remove element
```js
let heading = document.querySelector('h1');
heading.remove();
```

##### Style object
- background-color 会变成 backgroundColor
```js
let buttom = document.querySelector('button');

//这些设定全都为inline styling级别
// inline styling > id > class > ..
button.style.backgroundColor = 'black';
button.style.color = "white";


//或者你也可以这样写
button.style = 'background-color： black; color: white';

//如果不要styleing
button.style = "";


```

### Event
---
- callback function是foreach loop里面不断被嗲用的函数
- window object和element object都有addEventListener
- js event 都是一个个object
```js
//addEventListener(Event type, callback function(e))
//window object
winddow.addEventListener('click', (e) => {
	console.log(e);
})
```

##### event object property and method
- target
- preventDefault
```js

let h1 = document.querySelector("h1");
h1.addEventListener('click', e => {
	console.log(e.target.innerHTML);
	console.log(e.target.parentElement);
	//鼠标所选中的内容的。。。
})


//preventDefault

let button = document.querySelector('button');
button.addEventListener('click', e => {
	e.preventDefault();
	//buton按钮本来默认点击会提交表单，但是使用了preventDefault之后表单就不会自动提交
})


```




### React老师的JS复习，以及和面试相关
---

- 为什么选用react??
	- simple page application
- ES6新特性
	- this 
	- closure 
	- spread 
	- map reduce filter

##### const, let and var
```
let const -- block 

```


### shallow copy and deep copy, (vscode前lesson 6里面有讲到)
---
- object.assgin 可以做对象浅拷贝
- 解构运算符也可以做浅拷贝
```js
const newOjj = {...a, ...b};
```


### 关于object的方法
---
- Object.keys()
- Object.values()
- Object.entries() 返回一个数组
- Object.assign() 浅拷贝
- Object.freeze() 冻结一个对象然后之后就不能修改了
- Object.seal() 无法添加删除，可以修改


```js
// Object.keys()
let profile = {
	name: 'Rober Dw.Jr',
	age: 45,
	work: 'Actor'
};

console.log(Object.keys(profile));//是一个数组
let str = 'abc';
console.log(Object.keys('str'));

//如果想要知道object里面的长度
let length = Object.key(profile).length;


//Oject.values()
// for in + Oject.hasOwnProperty = Oject.values()
const person = {
	firstName: 'John',
	lastName: 'Doe',
	age: 25
};

for (const key in person){
	if(person.hasOwnProperty(key)){
		console.log(person[key]);
	}
}

const values = Object.values(person);
console.log(values)// values的一个数组

// object.entries()

const obj = {
	name: 'ben',
	age: 26
}

console.log(Object.entries(obj));

// Object.assign()
//1
const newObj = Object.assign({}, obj);//浅拷贝
console.log(newObj);
//2

const obj1 = {first: 1};
const obj2 = {second: 2};
const obj3 = {third: 3};
//想让输出成为： {first: 1, second: 2, third: 3}
const newObj = Object.assign({}， obj1, obj2, obj3);
console.log(newObj);

//3想让 assign的第一个输入不为空的情况

const obj = {some: 'value'}

const newObj = Object.assign( obj， obj1, obj2, obj3);//连着在一起
console.log(newObj);

// object.freeze() 
// 浅冻结，只能冻结第一层， 第二层是可以被修改的
let obj = {name: 'ben', age: 22};
Object.freeze(obj);

obj.name: 'Alice'; //无法改动
//同样不能delete, 不能修改不能添加

//同样也可以运用到数组
let arr = [1,2];
Oject.freeze(arr)


```

-  上面object.entries所返回的结果
![[23-1-9-01.png]]


### advanced JavaScript 3
---
* 2022 网页开发全攻略

##### copy of array
```js
//spread operater

let friends = ['Mike', 'Josh'];
let copy = [...friends];

```

##### Higher Order function
- f(g(x)) = g(x) + 3
- forEach is a higher order function

##### Ternary Operator
-  let price = (condition) ? true : false

##### Default parameter
```js
function multiply(a = 1, b = 1) {

}
```

##### back-tick
```js
let maName = 'Wilson Ren';
console.log(`${myName} says' hi`);
```

IIFE (immediately invoked function expression) ^4a5a9a
```js
(function sayHi(name) {
	console.log("Hello!" + name);
})('wilson');
//library source code 

//还可以把一个公有变量变成私有变量
const counter = ( function () {

	let counter = 0;

	function increment() {
		counter++;
	}

	function getCurrentCount() {
		return counter;
	}

	return {
		increment,
		getCurrentCount,
	};

}
)(); 

counter.increment();
console.log(counter.getCurrentCount());


```

### 异步 asynchronous
---
- 因为JS是单线程的所以需要异步来保证像多线程一样快速运行
- [promise and callback hell](https://www.freecodecamp.org/news/javascript-promise-tutorial-how-to-resolve-or-reject-promises-in-js/)
- promise 就是其中一个异步方案


- [Aysnc await](![[Pasted image 20230124104348.png]])

```js

async function async1() {
console.log('async1 start');
await async2();
console.log('async1 end');
}

async function async2() {
console.log('async2');
}

console.log('script start');
async1();
console.log('scripte end');

```

