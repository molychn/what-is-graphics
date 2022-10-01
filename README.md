# what-is-graphics

## 从 Canvas 开始

- 获取 canvas 对象

```javascript
// 这意味着需要有id为canvas的DOM元素canvas标签
const canvas = document.getElementById('canvas');
```

- 获取画布（2D环境）

```javascript
const context = canvas.getContext('2d');
```

- 基于状态绘制

canvas的绘制在于先进行画笔的移动与定点，类似于绘画中的底稿，而后才是选择画笔属性，如粗细颜色等进行绘制。

绘制只有两种方法，fill 和 stroke，前者指填充，后者为描边。

利用上述两个关键点，获取对象与画布，然后对画笔进行配置，从而绘制出一条简单的直线。[DrawALine](/canvas/drawALine.html)
![drawALine](/assets/canvas_draw_a_line.png)

- 使用beginPath保存上一次绘制

对于定位移动好画笔底稿后，使用stroke实现绘制，但每次绘制如果没有给出起始状态改变的信号，则再次调用stroke时会覆盖之前的状态。
```javascript
context.beginPath();
context.moveTo(x, y);
context.lineTo(x1, y1);
context.lineWidth = 5;
context.strokeStyle = 'blue';

context.beginPath();
context.moveTo(x2, y2);
context.lineTo(x3, y3);
context.lineWidth = 5;
context.strokeStyle = 'yellow';
```
> beginPath()是绘制设置状态的起始点，它之后代码设置的绘制状态的作用域结束于绘制方法stroke()、fill()或者closePath()

- APIs

1. closePath，可以对线条的绘制形成闭合，即会在终点与起始点连接成直线。 [闭合三角形](/canvas/triangle.html)
2. fill，与stroke用于绘制，但其绘制作用主要在于填充。 [填充三角形](/canvas/triangle.html)
3. rect，绘制矩形的方法，其参数分别为左上，右下的坐标。[矩形](/canvas/triangle.html)
4. fillRect和strokeRect实现快捷绘制实心空心矩形
5. createLinearGradient和createRadialGradient创建线性与径向渐变效果。[渐变](/canvas/gradient.html)
