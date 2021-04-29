## HTML:
### 如何理解 HTML 语义化
#### &emsp;比较下面两段代码
```HTML
<div>标题</div>
<div>
    <div>一段文字</div>
    <div>
        <div>列表1</div>
        <div>列表2</div>
    </div>
</div>
```
```HTML
<h1>标题</h1>
<div>
    <p>一段文字</p>
    <ul>
        <li>列表1</li>
        <li>列表2</li>
    </ul>
</div>
```
#### &emsp;体现语义化的作用:

​	

##### &emsp; 1.让开发人员更容易读懂 
##### &emsp; 2.让搜索引擎更容易读懂(SEO)
### 默认情况下，哪些 HTML 标签时块级元素、哪些时内联元素（异同点?） 
#### &emsp;块状元素(独占一行display:block/table): 有 div h1 h2 table ul p
#### &emsp;(内联元素display:inline/inline-block)：有 span img input button
## CSS:
### 布局
#### &emsp;盒模型宽度计算
```HTML
<!--如下代码，请问 div1的 offsetWidth 是多大-->
<style>
    #div1{
        width:100px;
        padding:10px;
        border:1px sold #ccc;
        margin:10px;
    }
</style>

<div id="div1">
</div>
```
##### offsetWith = (内容宽度+内边距+边框) = (100+10x2+1x2)122
##### 如果要让 offsetWidth 为100 怎么做？加上样式:box-sizing:border-box;（以边框外边框尺寸定义 做 width 属性）

#### &emsp;margin 纵向重叠问题
```HTML
<!--如下代码，AAA 和 BBB 之间的距离是多少-->
<style>
    p{
        width:16px;
        line-height:1;
        margin-top:10px;
        margin-bottom:15px;
    }
</style>
<p>AAA</p>
<p></p>
<p></p>
<p></p>
<p>BBB</p>
```
#### &emsp;margin 负值问题
##### &emsp;对 margin 的 top left right bottom 设置负值，有何效果?
###### &emsp;margin-top、margin-left 负值 元素分别向上、向下移动
###### &emsp;magin-bottom、margin-right 负值，底部的或右边的元素向上或向下移动,自身不受影响
#### &emsp;BFC 理解和应用
##### &emsp;什么是BFC？如何应用
###### &emsp;Block format context块级格式化上下文
###### &emsp;独立渲染区域,内部元素元素渲染不会影响外部区域渲染
##### &emsp;形成 BFC 的条件
###### &emsp;float 不是 none
###### &emsp;或position 是 absolute 或 fixed
###### &emsp;或overflow 不是 visible
##### &emsp;BFC常见应用
###### &emsp;清除浮动(例子)
#### &emsp;float 布局问题,clearfix 问题
##### &emsp;如何实现圣杯布局和双飞翼布局?(float方式，一般用于PC网页))(3-6课时)
###### &emsp;三栏布局,中间一栏最先加载和渲染(内容最重要)
###### &emsp;两侧内容固定,中间内容随宽度适应
###### &emsp;1.使用 float 布局 2.侧使用 margin 负值，以便和中间内容横向重叠 3.防止中间内容被两侧覆盖，一个用 padding 一个用 margin

##### &emsp;手写clearfix
#### &emsp;flex 布局画三点色子
### 定位
#### absolute 和 relative 分别依据什么定位
##### relative 依据自身定位
##### absolute 相对第一个先辈定位元素定位，定位元素包括 body 标签、relative\absolute\fixed 样式的元素
#### 居中对齐有哪些方式实现
##### 1.inline 元素:text-align:center(水平居中)
##### 2.block 元素:margin:auto（水平居中）
##### 3.absolute 元素:left 50%+margin-left:负值(水平居中)(需要知道子元素宽度)
##### 4.inline 元素:line-height 的值等于 height 值(垂直居中)
##### 5.absolute 元素:top:50%+margin-top负值(垂直居中)(需要知道子元素高度)
##### 6.trasform(-50%,-50%)（垂直居中）
##### 7.absolute 元素:top,left,bottom,right=0+margin:auto;(垂直居中)

### 图文样式
#### &emsp;line-height继承问题(这里有个坑)
```HTML
<!--p 标签的行高是多少-->
<style type="text/css">
body{
    line-height:200%;
    font-size:20px;
}
p{
    font-size:16px;
}
<p>AAA</p>
</style>
```
##### 答案是 40
###### 1.line-height 写具体值，则继承该值
###### 2.写比例，如2/1.5,则继承该比例
###### 3.写百分比,如200%,则继承计算出来的值

#### &emsp;rem 是什么?与pm、em 的区别?
#### &emsp;如何实现响应式
### 响应式
#### rem 是什么？
##### 	px,绝对长度单位,最常用
##### 	em，相对长度单位,相对于父元素,不常用
##### 	rem,相对长度单位，相对于根元素的长度单位,常用于响应式布局

#### 响应式的常见方案
### css3
#### &emsp;flex 
#### &emsp;动画