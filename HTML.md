# html 基本语法

## <常规标记> 也叫双标记

```html
<标记 属性 = “属性值” 属性 = “属性值”> </标记>
标记也可以叫标签或者元素
```

## 空标记也叫单标记

```html
<标记/>
<标记 属性 = “属性值”/>
```

##  hr 标签属性

```html
<hr color = "green">
```

## 特殊符号

- 尖角号：

  - 左尖角号 &lt;
  - 右尖角号 &gt;

- 空格：

  - ```
    &nbsp;
    ```

  - ```
    &emsp;
    ```

- 版权： &copy;

- 商标： 1. &trade; 

    2. &reg;

## div 和 span标签

```html
    <!-- div*3就是直接创建三个div标签 -->
    <!-- div{1111}*3 -->
    <!-- div标签，没有具体含义， 用来划分页面的区域，独占一行 -->
    <div>11111</div>
    <div>222222</div>
    <div>33333</div>
    <!-- span没有实际意义，主要应用在对于文本独立修饰的时候， 内容有多宽就占用多宽的空间距离。 -->
    <h3>体育 <span style = "color: gray;">Sports</span></h3>
```

## 列表

1. 无序列表

```html
<ul>
    <li>无序列表</li>
    <li>无序列表</li>
</ul>
```



1. 有序列表

```html
<ol type = "A" start = "4">
    <li>有序列表</li>
    <li>有序列表</li>
</ol>
```



1. 自定义列表

```html
<dl>
    <dt>可以是文字也可以是图片</dt>
    <dd>相关文字</dd>

</dl>
```

## 图片的标签属性

```html

<img src = "图片路径" title = "鼠标悬停上去后的提示信息" alt = "图片不显示或者加载失败的提示信息" width = "" height = ""/>
```

## 超链接
```html
<a href = '路径' title = '鼠标悬停上去后的提示信息' target = '规定在何处打开文档'>内容</a>
```

## table
```html

%%快速创建table: table>tr*2>td %%
<table>
	<tr> %%表示行%%
		<td>1</td> %%表示单元格%%
		<td>2</td>	
	</tr>
	<tr> %%表示行%%
		<td>1</td> %%表示单元格%%
		<td>2</td>
	</tr>
</table>
```

### 表格的属性
- 宽度 width
- 高度 height
- 边框 border
- 边框颜色 bordercolor
- 背景颜色 bgcolor
- 水平对齐 align='left或者right'
- cellspacing = "单元格与单元格之间的距离"
- cellspacing = "单元格与内容之间的空隙"

### 行 <tr>的属性
- 高度 height
- 背景颜色 bgcolor
- 文字水平对齐 aglin = 'left' 'right'
- 文字垂直对齐 vaglin = 'top' 'middle' 'bottom'


### 单元格 <td> 的属性
- 宽度 width
- 高度 height
- 背景颜色 bgcolor
- 文字水平对齐 align
-  文字垂直对齐 valign



## 表单

```html
<form method = 'get'或者'post' action = '向何处发送表单数据'>
    <input/>
    	a. 属性 type定义输入框的类型
    		1. 文本框 type = 'text' 密码框 type = 'password'
    		2. 提交框 type = 'submit' 和 <button>提交按钮</button>一样
    		3. 按钮框 type = 'button' 单纯的按钮
    		4. 重置框 type = 'reset' 清空的效果
    	b. 属性 placeholder 描述输入字段预期值的简短的提示信息。 兼容到IE8以上
    	c. 属性 name 必须设置， 否则在提交表单时， 用户在其中输入的数据不会被发送给服务器
    	d. 属性 value
</form>
    
    
```

### form当中method的post和get的区别

1. get是从服务器上获取数据，post 是向服务器传送数据
2. get是把参数数据队列加到提交表单的action属性所指的URL中， 值和表单内各个字段一一对应 ==在URL 中可以看到==。 POST 是通过HTTP post的机制， 将表单内各个字段与其内容放置在HTML HEADER 内一起传送到ACTION属性所指的URL地址。 ==用户看不到这个过程==
3. 



























