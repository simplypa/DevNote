https://www.mongodb.com/json-and-bson'
mongodb是使用Bson储存的

在CMD / Powershell里输入Mongosh启动
```cmd
mongosh

show dbs // 查看有哪些数据库

use [trydb] // 进入trydb数据库

// collections 就是table的意思
// 一个数据库里会有很多表格

show collections // 看数据库中的表格

db // 查看现在的资料库

```

### MongoDB CRUD 增删改查
---
- insertion
- find
- update
- delete
https://www.mongodb.com/docs/v5.0/crud/


```cmd

// insertion
db.collection.insertOne()
eg. db.students.insertOne({
	name: "wilson Ren",
	age: 22, 
	major: "Computer Science",
	scholarship: {
		merit: 3000,
		other: 1500
	}
})
//查看已经加入的
db.students.find()

// 放入很多
db.collection.insertMany()



// find
db.students.find({major: "Chemistry"})

//update
db.collection.updateOne
eg. db.students.updateOne(
	{name: "Wilson Ren"}, 
	{
		$set: {name: "Wilson Wu" }, 
		$currentDate: {lastModified: true}
	}
)

db.collection.updateMany
db.collection.replaceOne



```

### Mongoose
---
- use mongoose to connect MongoDB to our web project
- use nodejs to install mongoose (one of an node module) 
- 