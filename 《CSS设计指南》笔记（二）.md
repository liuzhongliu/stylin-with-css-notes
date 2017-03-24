# 《CSS设计指南》——添加样式
<br/>
通过了第一章对HTML的学习了解，接下来就可以来了解一下CSS的工作原理了。CSS主要是给HTML添加样式的，正因为有了CSS，我们的网页不仅能设计的多样化，还能富有艺术性。讲到这里我突然想到有一个叫[中国色-中国传统颜色](http://zhongguose.com/)[这是链接内容](http://www.yaosansi.com/这是链接地址)的配色网站还挺不错的，它是模仿日本的一个传统颜色网站[NIPPON COLORS - 日本の伝統色](http://nipponcolors.com/) ，有时候我会在这里找找配色灵感。


## 为文档添加样式的三种方法
<br/>

### 行内样式
```    
<div style="clear:both; padding:100px 0 0 0;font-size:.85em; color:#666;">
  <p>A code example from <em>Stylin&rsquo; with CSS, Third Edition</em>by Charles Wyke-Smith. 
  Visit <a href="http://www.stylinwithcss.com">stylinwithcss.com</a>
  for more CSS information and updates.</p>
</div>
```
这种在标签元素内部写的CSS规则叫做行内样式，我觉得一般会在偷懒的时候使用😊。


### 嵌入样式
嵌入样式有时候地方也叫内联样式，是放在HTML文档的`<head>`元素中，如：
```
<head>
<meta charset="utf-8" />
<title>Stylin' with CSS - The Anatomy of a CSS Rule</title>

<style>
  h1 {font-size: 16px;}
  p {color:red;}
</style>

</head>
```
内联样式在使用时还是很方便的，因为html和css在同一个页面可以互相参照，等css样式设计完，组件功能齐全后，再把它转移到外部样式表中，这样其他的页面也能共用相同的样式了。


### 链接样式
在创建多个页面的网站时，需要把样式集中在一个单独的文件里，这个文件叫样式表通常以“styles”命名，扩展名为“.css”。这样就可以在任意HTML页面使用同一个样式表，只需在头部添加下面一行代码：
```
<link href="styles.css" rel="stylesheet" type="text/css">
```
使用链接样式（也叫外联样式）时，修改样式表中的样式，整站所有页面多少都会体现出来，这样方面全站外观同一，也便于整站更新。

**需要注意的地方，三个样式的优先级为：行内>嵌入>链接。**
也就是说，如果页面中同时有三种样式的话，首先呈现出来的样式将会是行内样式，然后是嵌入，最后是链接。同一属性的CSS样式，行内样式总是会覆盖嵌入样式和链接样式。


另外，还有一种特殊的添加样式的方法，它是在样式表中链接其他样式表的方法，应用@import指令（是一种@规则）：
```
@import url(css/styles2.css)
```
**需要注意的是，@import指令必须出现在样式表中其他样式之前，否则它不会被加载。**
