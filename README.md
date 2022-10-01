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