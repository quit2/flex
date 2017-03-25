# flex 整理
*兼容*
- display: -webkit-box;
- display: -moz-box;
- display: -ms-flexbox;
- display: -moz-flex;
- display: -webkit-flex;
- display: flex;

*属性*
- flex-grow: 3  定义弹性盒子项（flex item）的拉伸因子。 负值无效，初始值：1。
- flex-shrink 属性指定了 flex 元素的收缩规则。初始值：1
- flex-basis：用来指定伸缩基准值，即在根据伸缩比率计算出剩余空间的分布之前，「- flex子项」长度的起始数值。
- flex：none | <' flex-grow '> <' flex-shrink >'? || <' flex-basis '>  
- flex: 0 0 33.33333%;   0 0 auto;

- 如果缩写「flex: 1」, 则其计算值为「1 1 0%」
- 如果缩写「flex: auto」, 则其计算值为「1 1 auto」
- 如果「flex: none」, 则其计算值为「0 0 auto」
- 如果「flex: 0 auto」或者「flex: initial」, 则其计算值为「0 1 auto」，即「flex」初始值.


- *flex-flow 属性是 flex-direction 和 flex-wrap 的简写*
- align-items 属性以与justify-content相同的方式在侧轴方向上将当前行上的弹性元素对齐。
- align-self 会对齐当前 flex 行中的 flex 元素，并覆盖 align-items 的值. 如果任何 flex 元素的侧轴方向 margin 值设置为 auto，则会忽略 align-self。
-  justify-content 属性定义了浏览器如何分配顺着父容器主轴的弹性元素之间及其周围的空间。
-  flex-wrap 指定 flex元素单行显示还是多行显示。如果允许换行，这个属性允许你控制行的堆叠方向。


###### 例子
- .flex{display:flex;width:800px;margin:0;padding:0;list-style:none;}
- .flex :nth-child(1){flex:1 1 300px;}
- .flex :nth-child(2){flex:2 2 200px;}
- .flex :nth-child(3){flex:3 3 400px;}
- 本例定义了父容器宽（即主轴宽）为800px，由于子元素设置了伸缩基准值flex-basis，相加300+200+400=900，那么子元素将会溢出900-800=100px；
- 由于同时设置了收缩因子，所以加权综合可得300*1+200*2+400*3=1900px；
- 于是我们可以计算a,b,c将被移除的溢出量是多少：
- a被移除溢出量：(300*1/1900)*100，即约等于16px
- b被移除溢出量：(200*2/1900)*100，即约等于21px
- c被移除溢出量：(400*3/1900)*100，即约等于63px
- 最后a,b,c的实际宽度分别为：300-16=284px, 200-21=179px, 400-63=337px。