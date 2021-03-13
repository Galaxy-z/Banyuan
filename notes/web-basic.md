# HTML

## 标签

```html
<!-- 标题(h1-h6) -->
<h1>title</h1>

<!-- 图片 -->
<img src="html.jpg" alt="HTML图片">

<!-- 超链接 -->
<a href="http://info.cern.ch/">世界上第一个网页</a>

<!-- 换行 -->
<br>

<!-- 段落 -->
<p> </p>

<!-- 列表 -->
<!-- 无序列表 -->
<ul>
  <li></li>
  <li></li>
</ul>
<!-- 有序列表 -->
<ol>
  <li></li>
  <li></li>
</ol>
```

## html文档基本结构

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
</body>
</html>
```

## VS code快速生成代码

```html
<!-- .box -->
<div class="box"></div>
<!-- p#text -->
<p id="text"></p>
<!-- .box#text -->
<div class="box" id="text"></div>
<!-- p{你好} -->
<p>你好</p>
<!-- a[href=#] -->
<a href="#"></a>
<!-- ul>.class -->
<ul>
  <li class="class"></li>
</ul>
<!-- table>.row>.cow -->
<table>
  <tr class="row">
    <td class="col"></td>
  </tr>
</table>

<!-- div+p -->
<div></div>
<p></p>
<!-- ul>li*3>a -->
<ul>
  <li><a href=""></a></li>
  <li><a href=""></a></li>
  <li><a href=""></a></li>
</ul>

<!-- (.foo>h1)+(.bar>h2) -->
<div class="foo">
  <h1></h1>
</div>
<div class="bar">
  <h2></h2>
</div>

<!-- ul>li.item$*3 -->
<ul>
  <li class="item1"></li>
  <li class="item2"></li>
  <li class="item3"></li>
</ul>
<!-- div.class>div.class1_$*5 -->
<div class="class">
  <div class="class1_1"></div>
  <div class="class1_2"></div>
  <div class="class1_3"></div>
  <div class="class1_4"></div>
  <div class="class1_5"></div>
</div>
<!-- div.class>div.class1_$@3*4 -->
<div class="class">
  <div class="class1_3">
  </div>
  <div class="class1_4"></div>
  <div class="class1_5"></div>
  <div class="class1_6"></div>
</div>
```

# CSS

## 将页面的css样式移除

开启chrome开发者工具，点击console，输入以下内容并回车

```
$('style,link[rel="stylesheet"]').remove()
```

## 设置html样式

### 行内样式

通过标签的style属性指定元素的样式。

通常在开发中使用行内样式进行调试，在交付代码中尽量避免使用行内样式。行内样式会给后续样式调整带来极大的困难。行内样式只作用于单一元素，通用性极差。



使用行内样式，将p元素的样式进行调整

```
<p style="color: red; font-size: 24px;">字体调整为红色</p>
```

属性值格式，`样式属性名: 样式设置值;`可以对元素多个属性样式进行设置，依次使用`;`隔开

### 内部样式

在head标签内，定义style标签，style标签的内部编写css样式

```
<head>
	...
	<style>
		选择器 {
			样式属性名: 样式设置值;
			样式属性名: 样式设置值;
		}
	</style>
</head>
```

通过选择器，可以将一类样式作用于多个元素，更好的应对未来对样式的调整。

### 外部样式

内部样式的样式使用仅限于当前html文件内部，将内部样式style中的所有内容放到一个文件中，文件以.css结尾。把需要使用这类样式的html文件引入css文件，这样就可以让样式作用于更多的文件中的元素。更大的提高样式的通用性，也提高了修改样式的效率。



html引入css文件样式的语法，在head标签中，增加link标签，link元素不需要结束标签，href属性使用的是css文件相对于当前html文件所在的路径。

```
<head>
	...
  <link rel="stylesheet" href="css/common.css">
</head>
```

### 注释

在CSS语句中间可以使用 `/*  */`包裹一些文本内容，对语句内容进行说明。浏览器会自动忽略其中的内容。

## 选择器

### 标签选择器

通过标签选择器的方式移除浏览器对li的默认样式

```
<head>
  <meta charset="utf-8" />
  <title>便签</title>
  <style>
    li {
      list-style: none;
    }
  </style>
</head>
```

浏览器将会移除列表左侧的`·`，向以上这种直接以标签名称作为选择器，被称作做标签选择器或元素选择器，可以通过直接指定HTML标签，为这些元素设置样式。`p`,`h1`,`body`,`html`都可以作为标签选择器。

### 类选择器

元素中使用class定义属性，class的值可以自己定义，可以定义多个属性值，使用空格隔开，每个属性值是一个类名。css可以针对类名设置样式，样式将会作用于带有相应class属性值的元素。

定义class属性，使用空格隔开多个属性值

```
<p class="odd big">床前明月光，</p>
```

为每个class单独设置css样式

```css
.odd {
  color: red;
}

.big {
  font-size: 24px;
}
```

### id选择器

```
<p id="one">床前明月光，</p>
```

保证定义id值在一个html文件中唯一。如果需要为多个元素添加相同样式，使用`class`属性样式

使用`#`+ id值，为每个ID元素配置样式。

```css
#one {
  color: red;
}

#two {
  color: blue;
}
```

### 后代选择器

后代选择器也称为上下文选择器，使用空格分隔多个标签，构成的选择器如下

```
ul li {
  list-style: none;
}
```

以上规则将会对作为`ul`元素后代的`li`元素生效，如果HTML中同时包含  `ol`元素，该元素也有`li`作为其子元素，但是这些`li`元素则不会被应用上述规则。

## 长度

### 绝对单位-px

### 相对单位-em

## 边距

### 盒子模型

height, width： 内容区

padding：内边距

border：边框

margin：外边距

### 清除默认边距

```
* {
  margin:0;
  padding: 0;
}
```

## 摆放元素

### 块级元素

 像`p`、`h2`、`ul`、`li`这些元素在文档流中独占一行，我们把这种元素称作块级元素，顾名思义，该元素呈现“块”状，可以使用`width`和`height`定义块级元素内容区域的宽高，块级元素比较霸道，它独自占据一行高度，会把相邻的其他元素盒子"推开"，块级元素中可以包含其他的块级元素和行内元素。

- 每个块级元素都是独自占一行。 
- 元素的高度、宽度、行高和边距都是可以设置的。　　 
- 元素的宽度如果不设置的话，默认为父元素的宽度（父元素宽度100%）。

### 行内元素

行内元素不可以设置宽（width）和高（height），但可以与其他行内元素在文档流中位于同一行，行内元素内一般不可以包含块级元素。行内元素的高度一般由元素内部的字体大小决定，宽度由内容的长度控制。行内元素有以下特点： 

- 每一个行内元素可以和别的行内元素共享一行，相邻的行内元素会排列在同一行里，直到一行排不下了，才会换行。 
- 行内元素的高度、宽度、行高及顶部和底部边距不可设置。 
- 元素的宽度就是它包含的文字或图片的宽度，不可改变。

### 浮动

设置了浮动属性的元素会脱离文档流的控制，摆脱块级元素和行内元素的限制。为了让每个`li`排到相同一行中，我们将`li`设置为向左浮动，摆脱块级元素在文档流中独占一行的限制。如下

```
ul li {
  list-style: none;
  background: #ffc;
  width: 10em;
  height: 10em;
  margin: 1em;
  padding: 1em; 
  float: left;
}
```

## 阴影

### box-shadow属性语法

box-shadow 用于给盒模型增加阴影，这里给每个`li`元素增加阴影，可以让每个便签在页面上显示更突出。

box-shadow 属性接受值最多由五个不同的部分组成。

```
box-shadow: offset-x offset-y blur spread color position;
```

含义为

```
对象选择器 {box-shadow:X轴偏移量  Y轴偏移量  阴影模糊半径  阴影扩展半径  阴影颜色  投影方式 } 
```

### offset-x

offset-x的值指明了阴影水平方向的偏移，即阴影在 x 轴的位置。值为正数时，阴影在元素的右侧；值为负数时，阴影在元素的左侧。

```
.left { box-shadow: 20px 0px 10px 0px rgba(0,0,0,0.5) }
.right { box-shadow: -20px 0px 10px 0px rgba(0,0,0,0.5) }
```



![img](/Users/edz/Documents/2131-basic/web-basic/02-CSS/doc/images/4d2a7c846562f69b413e009d107d0ca85e4.jpg)

### offset-y

 offset-y的值指明了阴影竖直方向的偏移，即阴影在 y 轴的位置。值为正数时，阴影在元素的下方；值为负数时，阴影在元素的上方。

```
.left { box-shadow: 0px 20px 10px 0px rgba(0,0,0,0.5) }
.right { box-shadow: 0px -20px 10px 0px rgba(0,0,0,0.5) }
```

![img](/Users/edz/Documents/2131-basic/web-basic/02-CSS/doc/images/3b519c367d067afad6b71da98ee4d1269f1.jpg)

### blur

  blur的值代表了阴影的模糊半径，值为 0 意味着该阴影是固态而锋利的，完全完全没有模糊效果。blur 值越大，阴影则更不锋利而更模糊。负值是不合法的，会被修正成 0。

```
.left { box-shadow: 0px 0px 0px 0px rgba(0,0,0,0.5) }
.middle { box-shadow: 0px 0px 20px 0px rgba(0,0,0,0.5) }
.right { box-shadow: 0px 0px 50px 0px rgba(0,0,0,0.5) }
```



![img](/Users/edz/Documents/2131-basic/web-basic/02-CSS/doc/images/2fe2cbfe2175d04e5c700b0290e03cac0c5.jpg)

### spread

 这是一个可选参数，spread代表了阴影扩展半径，其值可以是正负值，如果值为正，则整个阴影都延展扩大，反之值为负值是，则缩小。前提是存在阴影模糊半径。

```
.left { box-shadow: 0px 0px 0px 0px rgba(0,0,0,0.5) }
.middle { box-shadow: 0px 0px 20px 20px rgba(0,0,0,0.5) }
.right { box-shadow: 0px 0px 50px 50px rgba(0,0,0,0.5) }
```

![img](/Users/edz/Documents/2131-basic/web-basic/02-CSS/doc/images/de59c21c855a1cb3babd71382baa3f166bb.jpg)

### color

  color 的值是指阴影的颜色。它可以是任意的颜色单元 。

```
.left { box-shadow: 0px 0px 20px 10px #67b3dd }
.right { box-shadow: 0px 0px 20px 10px rgba(0,0,0,0.5) }
```



![img](/Users/edz/Documents/2131-basic/web-basic/02-CSS/doc/images/693136a6d3c9689294a145a5a094947c305.jpg)

### position

  此参数是一个可选值，如果不设值，其默认的投影方式是外阴影；  如果取其唯一值“inset”,就是将外阴影变成内阴影，也就是说设置阴影类型为“inset”时，其投影就是内阴影。

```css
.left { box-shadow: 0px 0px 20px 10px #67b3dd }
.right { box-shadow: 0px 0px 20px 10px rgba(0,0,0,0.5) inset}
```

![img](/Users/edz/Documents/2131-basic/web-basic/02-CSS/doc/images/55e21e01a8df4436a46770ba968db0a72a3.jpg)



## 旋转



```css
transform: rotate(45deg);
```

rotate接收一个参数“角度”，单位deg为度的意思，**正数为顺时针旋转**，负数为逆时针旋转，上述代码作用是顺时针旋转45度。

## 样式叠加

CSS可以把多个样式加到同一个元素上。如果多个样式有重合，浏览器会根据权重的大小进行样式覆盖，这就是为CSS(层叠样式表)这个名称的由来，当多个选择器选中某个元素，并修改元素相同的样式属性。浏览器会根据选中该元素的选择器计算一个权重值，根据这个权重值先应用权重小的样式，然后再拿权重大的样式去覆盖相同的样式。

### nth-child()选择器

## 鼠标悬停样式

我们接下来为每个便签增加鼠标悬停的样式，鼠标悬停到哪个标签上，标签将显示一个放大的效果。使用`:hover` 选择器定义样式语句。定义的样式语句在鼠标悬停到选择器指定的元素上时将获得样式，鼠标移除后，样式也跟着移除。

增加如下样式语句

```
ul li:hover {
  box-shadow: 10px 10px 7px rgba(0, 0, 0, .7);
  transform: scale(1.25);
}
```

表示为`li`元素增加鼠标悬停样式，当鼠标悬停到`li`元素上时，会将阴影的面积增大颜色变暗，在 `ul li` 选择器中定义的阴影样式为`box-shadow: 5px 5px 7px rgba(33, 33, 33, .7);`

transform:  scale(1.25)表示将元素放大1.25倍，另外之前设置的 `transform: rotate` 值也会被清空掉。因为transform 指定的旋转和缩放需要在设置的时候一起传入，如果只传一个值，相当于另一个传了默认值，rotate的默认值就是0deg。因此附加此样式后，鼠标悬停时，元素旋转角度将归零，并且显示放大，阴影加深，鼠标移动到别处后，样式恢复。

## 过渡

鼠标悬停的样式变化是瞬间完成的，可以通过设置让整个变化的过程更平滑，效果更好。使用 `transition` 属性进行设置，该属性将会监听元素的某项样式数据的变化，如果发生变化，则将变化的过程放慢，可以指定从原始值到达变化值总共花费多长时间，在这段时间中，如同动画一般进行过渡。给`li`设置`transition`属性如下

```
ul li {
  ...略
  transition: transform .15s linear;
}
```

 传入的三个属性值分别为 

- `transform` 表示监听的属性，当该属性值发生变化，则进行过渡效果，该值在鼠标悬停的时候会发生变化，一个是角度归零，一个是方大，这两个效果将会以动画的方式进行过渡
- `.15s` 表示整个过渡的时长为 0.15秒
- `linear`表示单位时间数值的变化是平均的

## 相对位移

使用 `position: relative`表示`li`元素为相对位置，然后再设置 `top`的值，就可以让`li`元素相对于当前位置上移或者下移(下移只需要设置一个负值即可)

### 元素遮挡

当鼠标悬停在`li`上放大显示后，会出现旁边的元素遮挡住放大元素阴影的情况，可以使用 `z-index`属性将放大的元素置于顶层，将`z-index`的选择器指定到`:hover`中，当鼠标悬停后获取`z-index`属性值，因为其他的元素都没有设置过`z-index`属性值，因此给一个值1 即可保证放大元素位于相邻元素上面。



