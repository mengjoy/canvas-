# canvas
canvas学习总结以及各种实例

### canvas渲染上下文
canvas有两种绘图方式：1、2d平面绘图 2、webgl的3d立体绘图

### canvas的单位和坐标体系
1、和数学中的坐标系很像，坐标原点(0,0) 是在左上角，以px为单位
绘图顺序会覆盖之前画的，超过画板的范围，canvas截取在画板上的部分

### canvas的画板和画布是什么？

### 【ctx.strokeRect】画笔绘制一个矩形方法
1、值：x,y,width,height

### 【ctx.strokeStyle】设置画笔属性
1、可选值：color、gradient、pattern(绘画对象，一个canvasPattern对象（可重复的图片），可以是一张图片或者另一个画布)

### 【ctx.fillrect】 填充矩形方法
1、值：x,y,width,height默认填充颜色为black
2、填充的矩形没有绘制边框

### 【ctx.fillStyle】设置填充样式属性
1、可选值：color、gradient、pattern(绘画对象，一个canvasPattern对象（可重复的图片），可以是一张图片或者另一个画布)
2、列子：绘制调色板

### canvas绘制路径
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
1、伯恩斯坦多项式
2、de casteljau算法，三个不共线控制点时，寻找两条线上的等比列的点，连接之后，在该线上寻找等比列的点，而从某条线起点运行到终点，不断寻找等比列的点，该点连接成线就是贝塞尔曲线
3、曲线为二次曲线、三次曲线同理

### 【ctx.bezierCurveTo()】绘制贝塞尔曲线
1、值：cp1x, cp1y, cp2x, cp2y, x, y
  cp1x-第一个控制点的x
  cp1y-第一个控制点的y
  cp2x-
  cp2y-
  x-结束点的x
  y-结束点的y
2、用途：可以用于制作平滑的动画效果

### 【ctx.fill() 】填充路径（必须是闭合的路径）
三种用法：
- ctx.fill(path, fillRule)
- ctx.fill(fillRule)
- ctx.fill()
path: 可选，需要填充的路径
fillRule: 决定点在路径内还是外，"nonzero"(非零环绕)、"evenodd"（奇偶环绕）有点像数学里面计算象限啥的？？【待查询】
边框还存在，只填充内部
  
### 【ctx.lineWidth】设置路径厚度
1、值：value，0，负数，infinity，NaN会被忽略
  
### 【ctx.setLineDash】设置虚线样式的方法
1、值：[], 一组描述交替绘制线段和间距
  
### 【ctx.lineDashOffset】设置虚线样式的起始偏移量属性
  
1、例子：跑马灯效果（蚂蚁线）
  
### canvas的渐变对象【CanvasGradient对象】
1、gradient = ctx.createLinearGradient 线性渐变 x1,y1,x2,y2
2、gradient = ctx.createRadialGradient 放射渐变 x1,y1,r1,x2,y2,r2
3、会创建出一个CanvasGradient对象，他有一个方法gradient.addColorStop(offset, color)
  - offset: 0 到 1 之间的值
  - color:  CSS颜色值
    
### canvas纹理【CanvasPattern】
1、给图形填充效果，三种，纯色，渐变，图案填充
2、填充用到的一小块图形称为纹理，可以是图，也可以是另一个canvas
1、创建纹理【ctx.createPattern(image, repetition)】唯一创建方法
  - image: CanvasImageSource对象
  - repetition： 重复图像方式
将创建的纹理赋值给fillStyle

### canvas阴影效果


### canvas的文本对齐方式textalign
1、和html/css的textalign对齐方式不一样，html/css是相对于父容器的位置对齐的，但是canvas的textalign是相对于绘制点的位置
2、start和end会受到 direction方向设置的影响变得不一样。

### canvas预测文本宽度【measureText()】

### cnvas绘制文本骨架【storkeText()】

### 绘制文本注意事项
1、


### 绘制图像
1、

### canvas的translate()
几何图形的变化变化的不是图形本身，而是画布的位置，当translate(50,50)，那么图形距离坐上考的位置就变成了(50,50)

### canvas的缩放
1、

### canvas的基本动画


 
    
  

  









