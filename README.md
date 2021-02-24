# canvas
canvas学习总结以及各种实例

### 渲染上下文
canvas有两种绘图方式：1、2d平面绘图 2、webgl的3d立体绘图

### canvas的单位和坐标体系
和数学中的坐标系很像，坐标原点(0,0) 是在左上角，以px为单位
绘图顺序会覆盖之前画的，超过画板的范围，canvas截取在画板上的部分

### 画板和画布是什么？

### 【ctx.strokeRect】画笔绘制一个矩形方法
值：x,y,width,height

### 【ctx.strokeStyle】设置画笔属性
可选值：color、gradient、pattern(绘画对象，一个canvasPattern对象（可重复的图片），可以是一张图片或者另一个画布)

### 【ctx.fillrect】 填充矩形方法
值：x,y,width,height默认填充颜色为black
填充的矩形没有绘制边框

### 【ctx.fillStyle】设置填充样式属性
可选值：color、gradient、pattern(绘画对象，一个canvasPattern对象（可重复的图片），可以是一张图片或者另一个画布)
列子：绘制调色板

### 绘制路径
1、 ctx.beginPath()开启一个新路径
2、 ctx.moveTo(x, y)将新路径的起始点移动到坐标(x, y)
3、 ctx.lineTo(x, y)使用直线链接路径到坐标(x, y)并不会真正的绘制
4、 ctx.closePath()将画笔返回到当前子路径的起始点，也就是beginPath刚开始的那个位置。
5、 ctx.stroke() 根据当前的划线样式绘制当前已存在的路径，beginpath -> closepath的那些位置，或者是上一次moveTo的位置到lineTo的位置

绘制矩形方法：
1、按照路径绘制
2、ctx.rect(x, y, width, height)方法直接绘制

绘制弧线方法：
1、按照路径，ctx.arcTo(x1, y1, x2, y2, radius(角度))

绘制圆弧方法：
1、按照路径，圆心，起始角度，结束角度ctx.arc(x, y, radius, startangle, endangle, anticlockwise),anticlockwise-true,逆时针绘制，false-顺时针绘制，arc()也是需要stroke()实体化

### 贝塞尔曲线
- 伯恩斯坦多项式
- de casteljau算法，三个不共线的点，寻找两条线上的等比列的点，连接之后，在该线上寻找等比列的点，而从某条线起点运行到终点，不断寻找等比列的点，该点连接成线就是贝塞尔曲线
- 








