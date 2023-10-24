# flex有关属性总结  
----

给父元素添加display:flex属性，则父元素成为flex-container，子元素成为flex-item。

当元素设置为flex框是，它们会沿着两个轴来布局：

主轴：沿着flex元素放置的方向延伸的轴，由flex-direction属性定义。

交叉轴：垂直于主轴的轴

---

### flex-direction： row | row-reverse | column | column-reverse
用于控制主轴的方向，决定flex-item在主轴上的排列方向。

### flex-wrap： nowrap | wrap | wrap-reverse
控制当flex-item的在主轴方向的尺寸之后大于contanier的main-size时是否换行，默认nowrap不换行。

### flex-flow： flex-direction || flex-wrap
flex-diretion和flex-wrap的简写

---

## flex: flex-grow || flex-shrink || flex-basis
flex是flex-grow、flex-shrink和flex-basis的简写。
默认值为 flex: 0 1 auto;

flex-grow：控制flex-item在主轴方向上的扩展比例，默认值为0。

flex-shrink：控制flex-item在主轴方向上的收缩比例，默认值为1。

flex-basis：控制flex-item在主轴方向上的初始大小，默认值为auto。

当flex-basis为auto时，flex-item的size由其内容决定。

当flex为默认值时，当容器main-size变宽时，flex-item并不会灵活地扩展，当容器main-size变窄时，flex-item灵活地会收缩（半灵活）。

flex: 1 1 auto;时为完全灵活

flex: 0 0 auto;时为完全不灵活

当flex: 一个正数； 时  相当于 flex: 正数 1 0; 此时flex-item变为全灵活，且flex-basis为0。这意味着flex-item本身的width（flex-direction: row）将不在起作用，从而时flex-item的尺寸为contanier中指定比例的可用空间。

---

### order: number， 对flex-item使用，默认值为0。可以改变flex-item在主轴方向上的顺序。

---

## 各种对齐方式

### 主轴方向上对齐方式
justify-content: flex-start | flex-end | center | space-between | space-around   用于控制主轴上所有flex-item的对齐

### 交叉轴方向上对齐方式
align-items: flex-start | flex-end | center | baseline | stretch  用于控制交叉轴上所有flex-item的对齐

algin-self: flex-start | flex-end | center | baseline | stretch  用于控制单个flex-item的对齐 当对单个flex-item设置align-self时，会覆盖align-items属性。

align-content: flex-start | flex-end | center | space-between | space-around | stretch  用于控制"多条主轴"的flex-item的对齐，当flex只有一行时，align-content属性不起作用。
