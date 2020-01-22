# JavaScript

## JavaScript学习预备知识

### 如何插入JS

- 使用\<script>标签在HTML中插入JavaScript代码，标签要成对存在，代码写在标签之间。
- \<script type="text/javascript">表示在\<script>\<\script>之间的是文本类型(text),javascript是为了告诉浏览器里面的语言属于JavaScript语言。

### JS在页面中的位置

- JavaScript代码可以放在html文件中任何位置

  - 放在\<head>部分，浏览器解析head部分就会这个代码，然后才解析页面的其余部分。

  - 放在\<body>部分，JavaScript代码在网页读取到该语句的时候就会执行。

    **注意:** javascript作为一种脚本语言可以放在html页面中任何位置，但是浏览器解释html时是按先后顺序的，所以前面的script就先被执行。比如进行页面显示初始化的js必须放在head里面，因为初始化都要求提前进行（如给页面body设置css等）；而如果是通过事件调用执行的function那么对位置没什么要求的。

### JS的语句符号