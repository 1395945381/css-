# CSS知识点

[CSS参考手册]: http://css.doyoe.com/



## 1.标签选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
   外部引用 <link rel="stylesheet" href="test1.css">
    内部引用：<style>
    h1{                          标签选择器的基本用法
        color: red;
    }
    </style>
</head>
<body>
    <h1>努力</h1><br>
</body>
</html>
```

## 2.类名选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
   外部引用 <link rel="stylesheet" href="test1.css">
    内部引用：<style>
    .change-color{                          类选择器的基本用法
        color: red;
    }
    .change-font{
        font-size:100px;
    }
    </style>
</head>
<body>
    <div class="change-color change-font">努力</div><br>
</body>
</html>
```

​			类名选择器可以有多个类名 ，类名之间用空格隔开.

## 3.id选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
   外部引用 <link rel="stylesheet" href="test1.css">
    内部引用：<style>
    #change-color{                          id选择器的基本用法
        color: red;
    }
    </style>
</head>
<body>
    <div id="change-color">努力</div><br>
</body>
</html>
```

​	id的命名是唯一的不能重复，只能使用一次

## 4.伪类选择器

向某些选择器添加特殊效果

### 4.1 链接伪类选择器

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
   外部引用 <link rel="stylesheet" href="test1.css">
    内部引用：<style>
    a:link{               未访问的状态           
        color: blue;
        font-size:13px;
    }
      a:visited{               已访问的状态           
        color: yellow;
        font-size:13px;
    }
      a:hover{               鼠标悬停时的状态           
        color: black;
        font-size:15px;
    }
      a:active{               鼠标点击时的状态           
        color: white;
        font-size:16px;
    }
    </style>
</head>
<body>
    <div id="change-color"><a href="#">点击</a></div><br>
</body>
</html>
```

- 如果需要给超链接定义：访问前，鼠标悬停，当前被点击，已访问这4种伪类效果，而又没有按照一致的书写顺序，不同的浏览器可能会有不同的表现

- 超链接的4种状态，需要有特定的书写顺序才能生效

- **超链接状态顺序：**

  > ```
  > a:link {} a:visited {} a:hover {} a:active {}
  > ```

  注意，a:hover 必须位于 a:link 和 a:visited 之后，a:active 必须位于 a:hover 之后
  可靠的顺序是：l(link)ov(visited)e h(hover)a(active)te, 即用喜欢(love)和讨厌(hate)两个词来概括

### 4.2结构（位置）伪类选择器（css3）

```css
<style>
li:nth-child(even){color:#f00;} /* 偶数 */
li:nth-child(odd){color:#000;} /* 奇数 */
</style>

<ul>
	<li>列表项一</li>
	<li>列表项二</li>
	<li>列表项三</li>
	<li>列表项四</li>
</ul>
```

```html
E:first-child		匹配父元素的第一个子元素E。
E:last-child		匹配父元素的最后一个子元素E。
E:only-child		匹配父元素仅有的一个子元素E。
E:nth-child(n)		匹配父元素的第n个子元素E。   可以是2n ,2n-1,3n 等 （n从0开始）
E:nth-last-child(n)	匹配父元素的倒数第n个子元素E。
```

​	

### 4.3目标伪类选择器

定位id的使用：target

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        :target{
            color: red;
            font-size: 100px;
        }
    </style>
</head>
<body>
    <div>
        <h2>导航</h2>
        <ol>
            <li><a href="#star">首页</a></li>
            <li><a href="#center"> 中心 </li>
            <li> <a href="#big">扩张</a> </li>
            <li> <a href="#my">个人中心</a> </li>
        </ol>
    </div>
        <h3 id="star">首页</h3>
    .....
    </body>
</html>
```

<img src="C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220302153513543.png" alt="image-20220302153513543" style="zoom:50%;" />

## 5.文字样式

 line-height:10px  (越小行间距越大)

text-align:left/center/right (对齐方式)

text-indent：2em (两个汉字的距离)定义块内文本内容的缩进

letter-spacing：2px (字间距)

word-spacing:2px(单词间距，只对英文有效)

**text-shadow**：1px 2px  0px rgba(0,0,0,0.1)                            定义文字是否有阴影及模糊效果

第1个长度值用来设置对象的阴影水平偏移值。可以为负值

第2个长度值用来设置对象的阴影垂直偏移值。可以为负值

如果提供了第3个长度值则用来设置对象的阴影模糊值。不允许负值

设置对象的阴影的颜色。

## 6.颜色透明度

color：rgba(r,g,b,a) a是透明度 取值在0·1之间

## 7.三种样式表

（1）行内样式表  使用少     写在head标签里

（2)内嵌样式表   使用少    <h2 style="color: rgba(0,0,0,0.5);font-size: 100px;">样式</h2>

  (3)外部样式表 使用多 推荐    <link rel="stylesheet" href="#（.css文件）">

## 8.块级与行内标签

### （1）块级标签：<h1> - <h6> ,<p>,<div>,列表等，<div>为其典型

块级标签通常**独占一行或多行**，可对其设置**长，宽(默认100%)，高，对齐属性**，用于网页布局与结构

### （2)行内标签：<a>,<strong>,<b>,<del>.....<span>...等 <span>是其典型

**不占独立区域**，仅仅靠里面的文字大小和图片尺寸支撑其大小，一般**不设置宽，高，对齐方式**

**行内元素只能容纳文本或其他行内标签，但是<a>不能套<a>**

**只有文字才能组成段落,<p>不能放块级元素，同理<h1>-<h6>**

<img src="C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306141404840.png" alt="image-20220306141404840" style="zoom:50%;" />

### (3)行内块标签

<img src="C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306141605634.png" alt="image-20220306141605634" style="zoom:50%;" />

### **（4）display**属性

![image-20220306142657880](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306142657880.png)

## 9. css复合选择器

### 1.交集选择器

![image-20220306143218115](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306143218115.png)

### 2.并集选择器

![image-20220306151006191](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306151006191.png)

### 3.后代选择器

![image-20220306151052751](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306151052751.png)

### 4.子元素选择器

子选择符只能命中子元素，而不能命中孙辈。

![image-20220306162728719](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306162728719.png)

### 5.属性选择器

选取标签带有某些特殊属性的选择器。

![image-20220306165019233](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220306165019233.png)

### 6.伪元素选择器

![image-20220307092758822](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220307092758822.png)

## 10. 文字凹凸效果

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        body {
            background-color: #ccc;
        }
        div {
            font-family: "微软雅黑";
            font-size: 100px;
            color: #ccc;
        }
        div:first-child {
            text-shadow: 1px 1px 1px #000,-1px -1px 1px #fff;
        }
        div:last-child {
            text-shadow: -1px -1px 1px #000,1px 1px 1px #fff;
        }
    </style>
</head>
<body>
    <div>凸文字</div>
     <div>凹文字</div>
</body>
</html>
```

![image-20220307102833940](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220307102833940.png)

## 11.CSS的特性

### 1.CSS层叠性

样式冲突，遵循就近原则。

样式不冲突，不会层叠

### 2.CSS继承性

子元素可以继承父元素的样式（text,font,line,color）

**继承的权重为0**

### 3.CSS优先级

**CSS 优先规则1：** 最近的祖先样式比其他祖先样式优先级高。

**CSS 优先规则2：**"直接样式"比"祖先样式"优先级高。

先说说 CSS 7 种基础的选择器：

![image-20220308093840259](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220308093840259.png)

**CSS 优先规则3：**优先级关系：内联样式 > ID 选择器 > 类选择器 = 属性选择器 = 伪类选择器 > 标签选择器 = 伪元素选择器

**CSS 优先规则4：**计算选择符中 ID 选择器的个数（a），计算选择符中类选择器、属性选择器以及伪类选择器的个数之和（b），计算选择符中标签选择器和伪元素选择器的个数之和（c）。按 a、b、c 的顺序依次比较大小，大的则优先级高，相等则比较下一个。若最后两个的选择符中 a、b、c 都相等，则按照"就近原则"来判断。

**CSS 优先规则5：**属性后插有 **!important** 的属性拥有最高优先级。若同时插有 **!important**，则再利用规则 3、4 判断优先级。

## 12 外边距合并问题

1. 使用marhin定义块元素的垂直外边距时，两个不嵌套的快元素，可能出现外边距合并

他么之间的外边距距离会是外边距较大的那个

​			2.两个嵌套的块元素，如果父元素没有内边距及边框，则父元素的上边距会与子元素的上边距合并，合并后外边距较大的。即使父元素的上外边距为0，也会合并。 （解决：1.定义父元素边框，2.使用overflow:hidden）

## 13.content 宽度和高度

![image-20220311100521788](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220311100521788.png)

## 14 CSS3盒子模型

box-sizing属性

1.值为content-box  就是以前的和模型

2.值为border-box (再写盒子的padding和border不会撑大盒子 ，宽和高为定义 好的width和height)

## 15 盒子阴影

![image-20220313203944620](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220313203944620.png)

## 16 浮动特性

### 1.浮动主要目的是为了让多个块级元素按一行显示

浮：加了浮动特性的元素盒子是浮起来的，漂浮在标准盒子之上

漏：加了浮动的盒子不占位置，他原来的位置漏给标准盒子

特：这是特殊使用，使用需谨慎

**不管是块元素还是行元素加入浮动后就具有行内块元素的特点**

最好和父盒子搭配起来使用

### 2.*清除浮动的方法**

**清除浮动的本质是为了解决父级元素因为子级浮动引起的自己内部高为0的问题**

代码：

```HTML
<style>
        .box1 {
            width: 300px;
            
        }
        .son1 {
            width: 100px;
            height: 100px;
            float: left;
            background-color: pink;
        }
        .son2 {
            width: 100px;
            height: 100px;
            float: right;
            background-color: red;
        }
        .box2 {
            width: 200px;
            height: 200px;
            background-color: blue;
        }
</style>
<body>
    <div class="box1 clearfix">
        <div class="son1"></div>
        <div class="son2"></div>
    </div>
    <div class="box2"></div>
</body>
```

1.在浮动盒子后面添加一个空盒子写上clear：both属性

2.在父级元素里增加属性（overflow:hidden | auto | scroll）也可以解决

3.在父级元素里加伪元素

```css
.clearfix:after {
    content:".";
    display:block;
    height:0;
    clear:both;
    visibility:hidden;
}
.clearfix {
    *zoom : 1;  /* IE6，7专有*/
}
```

4.使用before和after双伪元素清除浮动

```css
.clearfix:before,.clearfix:after {
    content:"";
    display:table; /*触发BFC，清除浮动*/  
}
.clearfix:after {
    clear:both; 
}
.clearfix {
    *zoom: 1;
}
```

## 17 定位属性

position属性left,right,top,bottom使用

1.**static**默认值

2.**relative**：相对自己原本的位置（原左上角）移动（**原来的位置继续占有**）（不脱离标准流）

3.absolute：绝对定位完全脱离标准流，**不占位置**

4.fixed : 和父盒子没关系，只认浏览器当前窗口，脱离标准流，不占位置

**父盒子没有定位，孩子盒子绝对定位，孩子会以浏览器为基点**

**父亲有定位（不管绝对还相对），孩子就以父亲定位**

一般父亲相对定位 ，孩子绝对定位

**absolute与fixed定位会改变行内元素的特性--->行内块元素**

### 2.定位的盒子距中

 子盒子加了定位于父盒子居中 margin：左右auto 不管用

1.首先left：50%

2.再往左走盒子的宽度一半

## 18.隐藏与显示

display:none (隐藏元素，不是删除，**不保留位置**)

display:block(显示元素与转换与块级元素，)

visibility:hidden(隐藏元素，但**是保留元素位置**)  | visiable(显示)



overflow属性

auto： 超出内容才显示滚动条

scroll: 不管超没超出内容，都显示滚动条

hidden：隐藏超出的部分

## 19.鼠标样式

cursor属性

![image-20220319204856395](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220319204856395.png)

## 20.取消轮廓线

outline:0;

## 21.防止拖拽文本域

![image-20220319205514852](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220319205514852.png)

## 22.文字垂直对齐

vertical-align：middle

对块级元素无效，一般用于表单或图片 与文字之间的垂直对齐

## 23.去除图片底侧缝隙

1. 将行内块元素改为块级元素
2. 加入vertical-align：top;

## 24.  word-break（英文）和white-space

## 25.text-overflow

text-overflow：clip  超出直接省略

text-overflow：ellipsis超出省略号显示



需要搭配white-space:nawrap 强制一行显示

还要overflow:hidden  直接裁剪

## 26.伪元素的本质

::before  或 ::after 本质上是插入一个行内元素

1）伪元素即伪类，它是一个元素的子元素，其意思就是说，我们无法用JS获取到这些伪元素，我们无法通过JS对其进行增、删、改，所以这也是它们的优点，因为它们不会增加JS查询DOM的负担，即对于JS来说伪元素是透明的。然后因为它们也不是实际的HTML标签，所以可以加快浏览器加载HTML文件，对SEO也有帮助（SEO  搜索引擎优化）。

2）如果我们把伪类的样式有absolute定位的话会把伪类强制变成块级元素，**伪类本身是行内元素的。**

**3）img、input和其他的单标签是没有after和before伪元素的，因为单标签本身不能有子元素。**

## 27.过渡属性

![image-20220324103026693](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220324103026693.png)

前两项属性必须写；花费时间为秒（s）；

**transition-timing-function** 有不同的曲线

过渡属性写在div中,不在变换，如hover里写

如果需要所有的属性都变，在前面写一个all就行

## 28.transform属性

###  2D变形

1.**translate(x,y)**:平移属性值  x:向x轴移动   其值可以为百分号

2.scale(x,y):缩放属性       默认值为 1    ，》1 放大   《1 缩小

3.rotate(deg【度数】):旋转属性  如  90deg 顺时针   -90deg逆时针

4.transform-origin: 可以调整元素转换变形的原点  有两个参数  （ left right bottom top |left right bottom top）或者（10px,10px）

5.skew(deg,deg): 倾斜     一个水平（正直向左倾斜） 二垂直   （正直往上）

### 3D变形

![image-20220324154204462](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220324154204462.png)

rotateX(deg【度数】):旋转属性  绕X轴旋转  。。。。

### 透视 （perspective）

![image-20220324155822097](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220324155822097.png)

视距：眼睛到屏幕的距离  视距越大效果与越明显



### translate3d(x,y,z)

### backface-visibility:hidden 不是正面对屏幕就隐藏

## 29.动画

```
1.定义动画
@keyframes go(动画名称) {
from {
transform:translateX(0);
}
to{
transform:translateX(600px);
}
}
-------------------------------------------------------
2.引用动画
div {
animation:go 2s ease 0s infinite（无限循环） alternate
(动画名称，运动时间，运动曲线，何时开始，播放次数，是否反方向)
}

```

如果有多组动画，用空格隔开就行

## 30 弹性布局

浏览器窗口变换时可以按比例缩放

父盒子设置display:flex  子盒子就可以设置flex:1 (份数)  **按份数比例划分长宽**

还可以在父盒子设置最小缩放长款 min-width

**属性**

flex-direction:column      **排列方式：垂直排列**     **默认水平**

flex-wrap：wrap（换行 ）默认不换行（若子盒子宽之和大于父盒子，会自动压缩子盒子宽以便一行显示）

flex-flow: <flex-direction>  <flex-wrap>  (简写形式)

![image-20220331211852297](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331211852297.png)

![image-20220331212538076](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331212538076.png)

align-items 只作用一行

![image-20220331213216245](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331213216245.png)

align-content:center  (把所有的当整体居中显示)

![image-20220331213556700](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331213556700.png)

flex-basis : 设置完基准值 宽度属性不在生效

一个扩大一个缩小

![image-20220331215518774](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331215518774.png)

## 31.grid布局

**二维布局**

**列的设置**

grid-template-columns:100px 100px 100px;                       每一列的宽度占100px                3列

grid-template-columns:1fr 1fr 1fr ;  	                           浮动宽度 每一列占1份                     3列 （和弹性布局类似）

**间距**

gap  统一设置

column-gap:24px     ;         设置列间距

row-gap:24px     ;				设置行间距

**grid-template-areas **  区域设置

![image-20220426100843978](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220426100843978.png)

![image-20220426100902148](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220426100902148.png)

![image-20220426100919117](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220426100919117.png)

**对齐方式**与flex类似

align-items:center  垂直方向对齐

justify-items:center  水平方向对齐

**子元素整体小于父盒子**可以整体对齐

align-content:center  垂直方向对齐

justify-content:center  水平方向对齐



# CSS3  新特性简介

## 1.简介

1.强大的CSS3的选择器

2.不借助图片的视觉效果

3.盒模型变化（多列布局和弹性盒模型）

4.阴影效果

5.Web字体和web Font图标

6.CSS3过渡与动画交互效果

7.媒体查询

 **渐进增强**：满足大部分浏览器

**优雅下降**：满足大部分用户

# 简单图形实现

## 1.三角型

```
 <style>
        .box {
            margin: 50px auto;
            width: 0;
            height: 0;
            border-top: 50px solid red;
            border-right: 50px solid yellow;
            border-bottom: 50px solid green;
            border-left: 50px solid blue;
        }
    </style>
    
    <body>
    <div class="box"></div>
</body>
```

![image-20220331194902676](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331194902676.png)

```
 <style>
        .box {
            margin: 50px auto;
            width: 0;
            height: 0;
           
            border: 50px solid transparent;
            border-top: 50px solid red;
            
             /* border-top: 50px solid red;
            border-right: 50px solid transparent;
            border-bottom: 0 solid transparent;
            border-left: 50px solid transparent; */
        }
    </style>
```

![image-20220331195052595](C:\Users\13959\AppData\Roaming\Typora\typora-user-images\image-20220331195052595.png)
