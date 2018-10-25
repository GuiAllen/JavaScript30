# github中的markdown语法如何解决带html<>标签文本的显示  
- Markdown 与HTML标签不能嵌套使用
  - 解决办法 加\转义
# 第一章 模拟敲鼓
## HTML <link> 标签的 href 属性  
- 一.\<link rel="stylesheet" href="style.css"\>
- href 属性规定被链接文档的位置（URL）
1.  超链接的 URL。可能的值：
绝对 URL - 指向另一个站点（比如 href="http://www.example.com/theme.css"）
相对 URL - 指向站点内的某个文件（href="/themes/theme.css")  
- 二.\<kbd\>A\</kbd\>
- kbd标签
 1. \<kbd\> 标签定义键盘文本。它用来表示文本是从键盘上键入的  
\<kbd\> 标签已废弃，不推荐使用，但 是可以通过CSS实现丰富的效果  
- 三.data-key="65"
 1. HTML data-* 属性  
属性用于存储页面或应用程序的私有自定义数据。存储的（自定义）数据能够被页面利用，以创建更好的用户体验（不进行调用或服务器端数据库查询）。  
- 四.event 对象  
  - event是JS的一个系统内置对象。平时无法使用，当DOM元素发生按键、鼠标等等各种事件时，系统会自动根据DOM元素触发的事件生成一个event对象。然后你可以直接取、使用这个新创建的对象去查询一些信息或者完成一些功能
  - 要注意只有在事件发生的过程中， event对象才生效。所以我们一般通过事件绑定函数，调用函数的方式使用、查看 event 的信息。而且在IE中event是一个全局对象。就是说在你想使用他的时候可以随时调用。不需要受什么约束。
  - event 的浏览器兼容问题  
  （1）在IE中，event 是一个全局的变量，不存在作用域的问题。  
  （2）谷歌做的也不错，使用也没有什么问题。在 Chrome 中，event并不是全局变量。他是在每个事件绑定的函数中都默认传入了一个形参event，注意函数的第一个形参就是event对象，而且我们不需要去写这个形参。如果你要在事件绑定的函数中使用 event，那直接 event . 点他的属性即可。系统默认将event对象以参数的形式传递到了函数中。这里不需要你做任何操作，只管用，简单粗暴。  
  （3）火狐就麻烦一点了。因为火狐中压根就没有event这个变量。不过解决方法也是很简单的。想要使用 event，我们就需要先使用如下语句　　var e = arguments.callee.caller.arguments[0] || window.event; 很简单吧，加上他火狐就可以兼容了，可以和谷歌等一样使用 event 对象。
- 五.const audio = document.querySelector(\`audio[data-key="${event.keyCode}"]\`)
1. document.querySelector  
querySelector()方法接收一个CSS选择符，返回与该模式匹配的第一个元素，如果没有找到匹配的元素，返回null。该方法既可用于文档document类型，也可用于元素element类型。 本例中即查找单引号内选择符--audio[data-key="${event.keyCode}]  
2. querySelectorAll()接收一个CSS选择符，返回一个类数组对象NodeList的实例。具体来说，返回的值实际上是带有所有属性和方法的NodeList，而其底层实现则类似于一组元素的快照，而非不断对文档进行搜索的动态查询。这样实现可以避免使用NodeList对象通常会引起的大多数性能问题。只要传给querySelectorAll()方法的CSS选择符有效，该方法都会返回一个NodeList对象，而不管找到多少匹配的元素。没有匹配元素时，返回空的类数组对象，而不是null
3. Array.from  
Array.from()方法就是将一个类数组对象或者可遍历对象转换成一个真正的数组。　那么什么是类数组对象呢？所谓类数组对象，最基本的要求就是具有length属性的对象。要将一个类数组对象转换为一个真正的数组，必须具备以下条件：

　　1、该类数组对象必须具有length属性，用于指定数组的长度。如果没有length属性，那么转换后的数组是一个空数组。

　　2、该类数组对象的属性名必须为数值型或字符串型的数字

　　ps: 该类数组对象的属性名可以加引号，也可以不加引号  
  4. $符号的意义  
  三种具体用法：
1、$()可以是$(expresion)，即css选择器、Xpath或html元素，也就是通过上述表达式来匹配目标元素。 
比如：$("a")构造的这个对象，是用CSS选择器构建了一个jQuery对象——它选择了所有的\<a/\>这个标签。如： 
$("a").click(function(){...}) 
就是在点击页面上的任何一个链接时的触发事件。确切地说，就是jQuery用\<a/\>这个标签构建了一个对象$("a")，函数 click()是这个jQuery对象的一个（事件）方法。   
2、$()可以是$(element)，即一个特定的DOM元素。如常用的DOM对象有document、location、form等。如这样一行代码：$(document).find("div>p").html()); $()中的document是一个DOM元素，即在全文寻找带\<p\>的\<div\>元素，并显示\<p\>中的内容。  
3.$()可以是$(function)，即一个函数，它是$(document).ready()的一个速记方式。
