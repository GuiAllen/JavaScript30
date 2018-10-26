# 02 纯 JS、CSS 时钟  
HTML 结构，表盘内有三个 `div` 对应三个指针。最外层div对应时钟
- style标签理解  
style 修改网页样式  可以根据html中的标签定义 如p{}；h1{};html{};body{};或者定义类 如之前类中定义class=number,style后可以.number修改样式
- 涉及到的特性
- `transform-origin`、`transform: rotate()`  
设置旋转元素的基点位置：transform-origin 属性允许您改变被转换元素的位置。
2D 转换元素能够改变元素 x 和 y 轴。3D 转换元素还能改变其 Z 轴。
- `transition`  
transition 属性是一个简写属性，用于设置四个过渡属性：
1. transition-property
2. transition-duration
3. transition-timing-function
4. transition-delay
注释：请始终设置 transition-duration 属性，否则时长为 0，就不会产生过渡效果。
- `transition-timing-function: cubic-bezier(x, x, x, x)`
- `setInterval(callback, time)`
- `new Date()  
Date 对象用于处理日期和时间。
可以通过 new 关键词来定义 Date 对象。Date 对象自动使用当前的日期和时间作为其初始值。
