# CSS 基本语法
- 每个CSS样式由两部分组成， 选择符 和 声明（声明分为属性 和 属性值）
```html

脸{
	眼睛：放大一公分；
	鼻子： 垫高一公分；	
	嘴巴： 缩小一公分 上嘴唇 下嘴唇；

}

```
- CSS is the language we use to style an HTML document
- CSS descdibes how HTML elements should be displayed.

## 选择器

- 标签选择器，如div p h1
- class选择器
- id 选择器
- ’*‘ 通配符选择器
- 群组和后代选择器

## 选择器的权重

<!-- 选择器的权重 -->

 <!-- !important > 行内属性样式 > 嵌套选择器(div p) > id选择器 > class选择器 > 标签选择器  -->

## CSS的属性

- CSS属性和属性值的定义
- CSS文本的属性
- CSS列表的属性
- CSS背景的属性
- CSS边框的属性
- CSS浮动属性

### CSS 文本属性

| 个数 | 属性            | 描述     | 说明                                             |
| ---- | --------------- | -------- | ------------------------------------------------ |
| 1    | font-size       | 字体大小 | 单位是PX                                         |
| 2    | font-family     | 字体     |                                                  |
| 3    | color           | 颜色     |                                                  |
| 4    | font-weight     | 加粗     | bolder, bold, normal                             |
| 5    | font-style      | 倾斜     | italic, oblique, normal                          |
| 6    | text-align      | 水平对齐 | left, right, center, justify(两端对齐，对于多行) |
| 7    | line-height     | 行高     |                                                  |
| 8    | text-indent     | 首行缩进 |                                                  |
| 9    | letter-spacing  | 字间距   |                                                  |
| 10   | text-decoration | 文本修饰 |                                                  |
| 11   | font            | 文字简写 |                                                  |



## 列表属性

- list-style-type 定义列表符合样式 disc(实心圆) circle(空心圆) square(实心方块) none(去掉符号)
- list-style-image 将图片设置为列表符合样式 list-style-image: url();
- list-style-position 设置列表项标记的放置位置 list-style-postion: outside; 列表的外面，inside 列表的里面
- list-style 简写 list-style;去除列表符号

## 背景属性

- background-color: 背景颜色 red
- background-image： 背景图片 url()
- background-repeat: 背景图片的平铺： no-repeat/repeat/repeat-x/repeat-y
- background-position 背景图片的定位： background-position 水平位置， 垂直位置；可以给负值
- background-attachment 背景图片的固定： scroll(滚动)/ fixed(固定)



## Display

![[8136bd69a00521ef5ef79f39025ac15.png]]



## Position
- static
- relative
- absolute
- fixed
- Sticky


## flexbox
- ![[6c4c7082ec1ad9e79dbb30d3f15b2d4.png]]
- ![[0ec57749466dfed754edacf0a58f820.png]]