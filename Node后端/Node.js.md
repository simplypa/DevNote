- 关于网页后端的内容需要学的内容如下
	- Node
	- [[Express.js]]
	- MongoDB
	- [[RESTful API]]
- Back-End Web Development
	- PHP
	- Node.js + Express + MongoDB (based on node.js)
	- Java
	- Ruby on Rails
	- Python(Django)
	- .NET
 ---

![[12-1-15-1.png]]

- nvm 可以帮忙切换node版本
- before node 需要了解一下IFFE [[JS#^4a5a9a]]



---
### create a server
```js

const http = require('http');
const fs = require('fs');
const path = require('path');

const homePage = fs.readFileSync(path.join(__dirname, 'home.html'));

const server = http.createServer((req, res) => {
	if (req.url === '/about') {
		res.write('about me');
		res.end();
		return;
	}
	if (req.url === '/home') {
		res.write(homePage);
		res.end();
		return;
	
	}
	res.write('hello');
	res.end();
});

server.listen(3000);



```

##### common used http method
![[23-1-16-1.png]]

- get request（获取数据）
- post request （发布, 给server数据）
- put request（完整的替换数据）
- delete  request（删除资源）
- patch request (更新数据) 



##### Js object <--> Json
```js

const obj = {a:1, b: "@"};

JSON.stringify(obj);

JSON.parse('a json type');


```


