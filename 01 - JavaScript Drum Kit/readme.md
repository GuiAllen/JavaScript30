# github中的markdown语法如何解决带html<>标签文本的显示  
- Markdown 与HTML标签不能嵌套使用
  - 解决办法 加\转义
# 第一章 模拟敲鼓
## HTML <link> 标签的 href 属性
一. \<link rel="stylesheet" href="style.css"\>
- href 属性规定被链接文档的位置（URL）
1.  超链接的 URL。可能的值：
绝对 URL - 指向另一个站点（比如 href="http://www.example.com/theme.css"）
相对 URL - 指向站点内的某个文件（href="/themes/theme.css")  

二. \<kbd\>A\</kbd\>
- kbd标签
 1. \<kbd\> 标签定义键盘文本。它用来表示文本是从键盘上键入的  
  \<kbd\> 标签已废弃，不推荐使用，但 是可以通过CSS实现丰富的效果
- data-key="65"
 1. HTML data-* 属性  
  属性用于存储页面或应用程序的私有自定义数据。存储的（自定义）数据能够被页面利用，以创建更好的用户体验（不进行调用或服务器端数据库查询）。
