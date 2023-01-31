### create a server
---

```js

const express = require('express');
const app = express(); 
//在node中，不常见，一般是module.export.morning = morning;
//express 中的引用来自express文档中， module.export = express;


//设定网址 + function
app.get('/', (req, res) => {
	res.send('<h1>you are on the homepage<h1>');
	//只能写一次
});

app.get('/wilson', (req, res) => {
	res.send("This is wilson's page");
});





app.listen(3000, () => {
	console.log('server is running on port 3000.');
});
```

### Routing in express
---
- res.send 之能送一次html
- res.sendfile
```js
const express = require('express');
const app = express(); 
//在node中，不常见，一般是module.export.morning = morning;
//express 中的引用来自express文档中， module.export = express;
const path = require('path');
const bodyParser = require("body-parser");
app.use(bodyParser.urlencoded({ extended: true}));


//routing 
//设定网址 + function
app.get('/', (req, res) => {
	res.send('<h1>you are on the homepage<h1>')；
	res.sendfile(__dirname + '/index.html')
});
//another way
app.get('/', (req, res) => {
	res.sendFile(path.join(__dirname, 'index.html'));
});


//routing for all
//一定要写在最下面
app.get('*', (req, res) => {
	
	res.status(404);
	console.log(res.statusCode);
	res.send('Cannot find what you want');
	res.sendFile(path.join(__dirname, "error.html"));
	
})

//routing for pattern
app.get('/fruit/:someFruit', (req, res) => {

	console.log(req.params);
	//output: {someFruit: apple};
	
	res.send('you are looking for' + req.params.someFruit);
	//or
	//destructing an object way.
	let { someFruit } = req.params;
	res.send('you are looking for' + someFruit);
});

//routing for query
//post
app.post('/formHandling', (req, res) => {
	console.log(req.body);
	let {fullname, age} = req.body;
	res.send(`thanks for posting. your name is ${fullname} and your age is ${age}`);
} )

//get
app.get('/formHandling', (req, res) => {
	console.log(req.query);
	let {fullname, age} = req.query;
	res.send(`thanks for posting. your name is ${fullname} and your age is ${age}`);
} )


app.listen(3000, () => {
	console.log('server is running on port 3000.');
});


```

##### relate html for upper routing for query
```html

//on the home page

//for the method is POST
<body>
	<form action="/formHandling" method='POST'>
		<label for='fullname'>your name:<label>		
		<input type='text' id='fullname' name='fullname'>
		<label for='age'>your Age: <label>
		<input type='number' id='age' name='age'>
		<button type='submit'>submit<button>
	<form>
<body>


//for method is GET
<body>
	<form action="/formHandling" method='GET'>
		<label for='fullname'>your name:<label>		
		<input type='text' id='fullname' name='fullname'>
		<label for='age'>your Age: <label>
		<input type='number' id='age' name='age'>
		<button type='submit'>submit<button>
	<form>
<body>

```


### static file （链接style.css）

```html
	<link rel='stylesheet' href='/styles/style.css'>
	//所有文件都从public出发
<body>
	<h1>this is the homepage.<h1>
<body>

```

```js
const express = require('express');
const app = express(); 
const path = require('path');
const bodyParser = require("body-parser");


//制作一个public资料夹，里面放styldes/style.css
app.use(express.static("public"));





```

### htttp status code
---
- 去Google htttp 状态码
- https://zh.m.wikipedia.org/zh/HTTP%E7%8A%B6%E6%80%81%E7%A0%81
- https://en.wikipedia.org/wiki/List_of_HTTP_status_codes
- ![[23-1-17-1.png]]



### package.json
---
![[23-1-18-1.png]]

##### dependencies
- major. minor. patch 
	- patch bug修复
	- minor加 feature
	- major, break change.feature
![[23-1-18-2.png]]

- devDependencies, 只在实际开发中有用比如说nodemon (不断跟新server)





