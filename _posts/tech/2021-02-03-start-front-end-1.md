---
layout: post
title:  "前端菜鸡破壳记一"
category: tech
date: 2021-02-03 23:07:22 +0800
tags: 前端 html+css
---
前端学习记录

> 最近依葫芦画瓢也写了不少前端代码了，在可以自己做完前端和后端之后，对很多功能的构思完整了很多，因此决定来系统的进行前端的学习。这个系列作为前端学习之路上的学习笔记和随笔。

感谢[嘉涛](https://github.com/bojueWjt)提供的书目《Head First HTMLCSS》、《JavaScript高级程序设计》、Vue项目文档及《vue.js实战》

## 第一本书 《Head First HTMLCSS》
html和css在我看来是可以随用随查的，因此这部分只会留下一些提示性的内容。


<div style="margin: 60px 0">
	<h4> 第一至第五章 </h4>
	<p>前五章科普性质的介绍了html，列举了常用标签，并简单提到了css, 这里只做一些简单的笔记</p>
</div>

<h4 style="text-decoration: underline;">HTML</h4>

- html是标记语言，其所有的内容都包裹在形如`<html>`的标签中
- 一组标签分为开始标签`<html>`，结束标签`</html>`，有部分标签可以不需要结束标签（如`<img>`）
- 完整的html内容应包裹在`<html></html>`标签中，同时具备`<head></head>`和`<body></body>`两对标签

<h4 style="text-decoration: underline;">CSS</h4>  

- css用来控制页面元素的样式，其内容被位于`<head>`标签中的`<style type="text/css">`标签包裹着
- css的语法如下:
```css
body {
	background-color: #aabbcc
}
```

**`html`控制页面内容结构, `css`控制页面元素样式**

<h4 style="text-decoration: underline;">块元素和内联元素</h4>  

瞎理解：块元素独占全部宽度，或者说自带前后换行，比如`<h2>`, `<p>`, `<blockquote>`；内联元素不自带换行，比如`<a>`, `<em>`, `<strong>`

---

瞎记

- 只用来换行的元素`<br/>`**

- 有序列表`<ol>`, 无序列表`<ul>`, 两种列表元素都用`<li>`包裹

- `<a>`标签表示链接，点击`<a>`标签包裹的元素将跳转至`src`属性指定的链接，且`target`属性表示在哪个窗口进行跳转，如果`target="_blank"`则会在新的窗口打开。  

- `<img src="some/path/to/image.jpg" alt="alternative text">` 是一个`img`标签示例，`src`属性表示图片源，`alt`表示当图片不存在或加载失败时显示的文本


<div style="margin: 60px 0; font-style: oblique;">
	第六章讨论html标准，第七章讨论xhtml，略过略过
</div>


<div style="margin: 60px 0">
	<h4> 第八章 CSS </h4>
</div>

> CSS里面的每个语句都包括一个场所（就像卧室），一个属性（就像窗帘和地毯）和一个提供给属性的样式（就像蓝色，或者一寸的瓷砖）

<p style="background-color: red; border: 1px solid gray; color: maroon">
	示例：为段落添加背景颜色、字体颜色和边框
</p>

css代码：
```css
p {
	background-color: red; 
	border: 1px solid gray; 
	color: maroon;
}
```

为多个标签添加相同的样式：
```css
h1, h2 {
	font-family: sans-serif;
	color: gray;
}
```

> pausing on page 335...

