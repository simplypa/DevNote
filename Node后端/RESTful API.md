##### Restful API
1. versioning 版本
	example.com/v1
	example.com/v2

2. 用名词来描述资源， 并且使用复数形式
	/v1/news
	/v1/users

3. 使用贴切的http method, 比如get只用来获取数据
	GET

4. URL 可以使用嵌套结构
	 posts {
		 comments
	 }
	 GET /v1/posts/:postId/comments
5. 注意数据返回的大小， 对数据进行分页
	GET /v1/posts?page=20&pageSize=100

6. 使用正确的， 恰当的状态码， status code 来表示返回的状态结果
		201 post success
		204 delete success
7. 返回human-readable,可读性高的错误信息


News API key:  f3030ed2a38c4771a11bf2dba49dac4c ^873a6b