 

### div标签

* div是division "分割"的缩写，<div></div>标签对是用来将相关的内容组合到一起，以和其他内容分割，使文档结构更清晰

* "DIV + CSS"结构，实现网页的布局

* <div></div>标签像是一个盒子

## HTML5特性

* 空白折叠现象。文字和文字之间的空格、换行都会被折叠成一个空格；一段文本中，开始位置手动输入的空格是不显示的。

* 转义字符

  * 常见转义字符

    | 转义字符 | 意义             |
    | -------- | ---------------- |
    | &lt+;    | 小于号           |
    | &gt+;    | 大于号           |
    | &nbsp+;  | 空格(不会被折叠) |
    | &copy+;  | 版权符号&copy;   |



原型图--->设计图

项目起步：

* 创建文件夹结构，主要文件夹如下：

  | 文件夹名 | 意义       |
  | -------- | ---------- |
  | images   | 存放图片   |
  | css      | 存放样式表 |
  | js       | 存放js文件 |

* 网站首页大多数都是index.html

### div的常见类名

* <div&gt;标签可以添加class属性表示"类名"，类名服务于css

  | 区域     | 类名    |
  | -------- | ------- |
  | 页头     | header  |
  | logo     | logo    |
  | 导航条   | nav     |
  | 横幅     | banner  |
  | 内容区域 | content |
  | 页脚     | footer  |



### HTML是什么？如何创建网页？如何浏览网页？

HTML是超文本编辑语言，HTML是用来开发网页的语言，主要是用标签对的形式为文本添加语义或者放置文档的部件

创建网页：在vscode编辑器中新建网页；直接更改文件后缀为.html，因为html本身就是纯文本的所以可以直接更改文本后缀

浏览网页：插件live sever插件

### HTML5骨架是什么结构？什么是DTD?

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>标题</title>
	<meta name="Description" content="页面描述，seo的重要手段">
	<meta name="Keywords" content="关键字，seo的重要手段">
</head>
<body>
    写网页的内容
</body>
</html>
```

DTD：文档类型声明

### 标题和段落标签、div标签要如何使用?

用什么文字要看语言

段落标签是p标签，p只能放文字、图片、表单元素；段落标签可以解决文字换行问题

div标签是内容的划分

### 网页的字符集有什么区别？

utf-8:一个汉字占3个字节，文字比较全

gb2312:gbk 一个汉字占两个子节

### 常见的SEO配置项和应该遵循的规则有哪些？

SEO：search engine optimization 搜索引擎优化；常见就是title、meta的description、keywords

<h1&gt;不能使用多次<h1&gt;之后要顺序使用其他h标签

keywords中要使用，分割不同的关键词

### HTTP是什么？我们做好的网页如何被用户看见？

HTTP：超文本传输协议



