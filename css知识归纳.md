## **1.flex布局**

设为Flex布局后子元素的float、clear、vertical-align属性将失效：

### 容器的6个属性

- [ ] flex-direction：决定主轴的方向，即项目的排列方向。（row（默认）、row-reverse、column、column-reverse）
- [ ] flex-wrap：定义如果一条轴线排不下剩下的如何换行。（nowrap（默认）、wrap、wrap-reverse）
- [ ] flex-flow：flex-direction 和 flex-wrap 属性的复合属性。flex-flow：<flex-direction>||<flex-wrap>
- [ ] justify-content：定义项目在主轴上的对其方式。（flex-start（默认值）、flex-end、center、space-between（两端对齐，项目之间的间隔都相等）、space-around（每个项目两侧的间隔都相等，项目间的间隔比边框大一倍））
- [ ] align-items：定义项目在交叉轴上如何对齐。（flex-start（起点对齐）、flex-end（终点对齐）、center、baseline（项目的第一行文字的基线对齐）、stretch（默认，如果未设置高度或者设为auto，将占满整个容器的高度））
- [ ] align-content：定义多根轴线的对齐方式，如果项目只有一条轴线则不起作用。（flex-start（起点对齐）、flex-end（终点对齐）、center、space-between（交叉轴两端对齐）、space-around（每个轴线两侧的间隔都相等）、stretch（默认，占满整个交叉轴））

### 项目的6个属性

- [ ] order：定义项目的排列顺序，默认是0。（数值越小，排列越靠前）
- [ ] flex-grow：定义项目的放大比例，默认是0。
- [ ] flex-shrink：定义项目的缩小比例，默认是1。
- [ ] flex-basis：定义在分配多空间之前，项目占据的主轴空间，默认是auto。
- [ ] flex：flex-grow、flex-shrink、flex-basic的简写，后两个属性是可选的。
- [ ] align-self：允许单个项目与其他项目不一样的对齐方式，可以覆盖align-items属性。默认是auto

## 2.变形（transform）、过渡（transtion）、动画（animation）

1、transform：

- [ ] 旋转：rotate(<angle>)。eg：transform:rotate(30deg)
- [ ] 移动：translate（<translation-value>[, <translation-value>]）。translate(x,y)水平方向和垂直方向同时移动（也就是X轴和Y轴同时移动）；translateX(x)仅水平方向移动；translateY(y)仅垂直方向移动。eg：transform:translate(100px,20px)
- [ ] 缩放：scale（<number>[, <number>]）。与translate相似，有scale、scaleX、scaleY。eg：transform：scale（1,2）
- [ ] 扭曲：skew（<angle> [, <angle>]）。与translate相似，有skew、skewX、skewY。eg：transform：skew（10deg，30deg）
- [ ] 矩阵：matrix(<number>, <number>, <number>, <number>, <number>, <number>) 。

2、transition：**transition: <property> <duration> <animation type> <delay>**

- [ ] ​	执行变换的属性：transition-property：none 、 all 、 indent。
- [ ] ​	指定元素转换过程的持续时间：transition-duration:time,单位为s或者ms。
- [ ] ​	改变属性值的变换速率：transition-timing-function（ease（逐渐变慢）、linear（匀速 ）、ease-in（加速）、ease-out（减速）、ease-in-out（加速然后减速）。cubic-bezier（贝塞尔曲线））。
- [ ] ​	指定动画开始执行的时间：transtion-delay：time。默认是0，即没有延迟。

3、animation：

​		关键帧（@keyframes）：定义动画在不同阶段的状态。

​		动画属性（properties）：决定动画的播放时长，播放次数，以及用何种函数式去播放动画等。

​		CSS属性：就是CSS元素不同关键帧下的状态

## 3.CSS3选择器

​		1、基本选择器

​			  通用选择器：*{}；标签选择器：标签名{}；类选择器：.class{}；id选择器：#id{}

​		2、复合选择器

​				多元素选择器：同时匹配选择器1和选择器2，多个选择器之间用逗号分隔。eg：p,h1,h2{}

​				后台选择器：E F   匹配后代元素，空格分隔。eg：#main p{}

​				子元素选择器：E>F   匹配所有元素的子元素,> 分隔。eg：div>p

​				相邻元素选择器：E+F   匹配所有紧随E元素之后的同级元素 F。 eg：div+div

​		3、伪类选择器：用来给超链接的不同状态来设置样式，设置有顺序

​				：link：未被访问的链接样式 ，：visited：已被访问的链接样式；：hover：鼠标悬浮元素上方；：active：鼠标					放在元素上面点击的一瞬间

​				：first-child、：last-child、

​				伪类和伪元素的区别：伪类其实是弥补了css选择器的不足，用来更方便的获取信息，而伪元素本质上是创建了													一个虚拟容器（元素），我们可以在其中添加内容或样式。

​		4、属性选择器：通过标签的属性名和属性值来匹配元素

​				[attr]：匹配所有居右attr属性的元素；eg：input[type]{}

​				[attr = 'val']：在上一条的基础上增加值的匹配

​				[attr^ = 'val']：匹配元素中attr属性以指定值开头的所有元素

​				[attr$= 'val']：匹配元素中attr属性以指定值结尾的所有元素

​				[attr*= 'val']：匹配元素中attr属性包含指定值的所有元素；eg：Font[color*="00"]