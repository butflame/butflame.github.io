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

**只用来换行的元素`<br/>`**

> ongoing...pause in page 139