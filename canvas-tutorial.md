#Canvas教程

##基本用法
我们从`<canvas>`html元素开始我们的教程,在文末,你将会知道如何使用canvas 2D context及在浏览器中开始你的第一个例子.

```html
<canvas id="tutorial" width="150" height="150"></canvas>
```
这里,首先我们像申明一个

##绘制形状
###绘制一个填充的矩形
```javascript
	fillReact(x,y,width,height)
```
###绘制一个矩形的边框
```javascript
	strokeRect(x,y,width,height)
```
###清除指定矩形区域,让清除部分完全透明
```javascript
clearRect(x, y, width, height)
```

###绘制路径
####新建一条路径，生成之后，图形绘制命令被指向到路径上生成路径
 ```javascript
 beginPath()
 ```
####闭合路径之后图形绘制命令又重新指向到上下文中
 ```javascript
  closePath()
 ```
####通过线条来绘制图形轮廓。
```javascript
 stroke()
 ```
####通过填充路径的内容区域生成实心的图形
 ```javascript
 fill()
 ```
####将笔触移动到指定的坐标x以及y上。
 ```javascript
 moveTo(x,y)
 ```
####绘制一条从当前位置到指定x以及y位置的直线。
 ```javascript
 lineTo(x,y)
 ```
####画一个以（x,y）为圆心的以radius为半径的圆弧（圆），从startAngle开始到endAngle结束，按照anticlockwise给定的方向（默认为顺时针）来生成。
 ```javascript
 arc(x,y,radius,startAngle,endAngle,anticlockwise)
 ```
####根据给定的控制点和半径画一段圆弧，再以直线连接两个控制点。
 ```javascript
 arcTo(x1,y1,x2,y2,radius)
 ```
####绘制贝塞尔曲线，cp1x,cp1y为控制点，x,y为结束点
 ```javascript
 quadrticCurveTo(cp1x,cp1y,x,y)
 ```
####绘制二次贝塞尔曲线，cp1x,cp1y为控制点一，cp2x,cp2y为控制点二，x,y为结束点。
 ```javascript
 bezierCurveTo(cp1x,cp1y,cp2x,cp2y,x,y)
 ```
####绘制一个左上角坐标为（x,y），宽高为width以及height的矩形
 ```javascript
 rect(x, y, width, height)
 ```
###Path2D 对象
 Path2D()会返回一个新初始化的Path2D对象（可能将某一个路径作为变量——创建一个它的副本，或者将一个包含SVG path数据的字符串作为变量）。	
####Path试例
 在这个例子中，我们创造了一个矩形和一个圆。它们都被存为Path2D对象，后面再派上用场。随着新的Path2D API产生，几种方法也相应地被更新来使用Path2D对象而不是当前路径。在这里，带路径参数的stroke和fill可以把对象画在画布上。
 ```javascript
 function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext){
    var ctx = canvas.getContext('2d');

    var rectangle = new Path2D();
    rectangle.rect(10, 10, 50, 50);

    var circle = new Path2D();
    circle.moveTo(125, 35);
    circle.arc(100, 35, 25, 0, 2 * Math.PI);

    ctx.stroke(rectangle);
    ctx.fill(circle);
  }
}
 ```
####使用 SVG paths
 新的Path2D API有另一个强大的特点，就是使用SVG path data来初始化canvas上的路径。这将使你获取路径时可以以SVG或canvas的方式来重用它们。
 ```javascript
 var p = new Path2D("M10 10 h 80 v 80 h -80 Z");
 ```





