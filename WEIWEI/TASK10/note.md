## 兼容性
IE11+

## 特性
块和内联模型依赖于流方向, 而Flexbox是布局模块，不是一个属性。包含父元素(flex container)和子元素(flex items)

## 实例
分为主轴和侧轴（方向与x轴和y轴差不多）

完全居中实例
重点在于，父display: flex. 子：margin: auto

html
```
    <div class="parent">
            <div class="child"></div>
        </div>
```
css
```
.parent {
  display: flex;
  height: 300px; /* Or whatever */
}

.child {
  width: 100px;  /* Or whatever */
  height: 100px; /* Or whatever */
  margin: auto;  /* Magic! */
}
```

多子实例
```
<ul class="flex-container">
        <li class="flex-item">1</li>
        <li class="flex-item">2</li>
        <li class="flex-item">3</li>
        <li class="flex-item">4</li>
        <li class="flex-item">5</li>
        <li class="flex-item">6</li>
    </ul>

.flex-container {
    /* We first create a flex layout context */
    display: flex;

    /* Then we define the flow direction and if we allow the items to wrap 
    * Remember this is the same as:
    * flex-direction: row;
    * flex-wrap: wrap;
    *  这个是“flex-direction”和“flex-wrap”属性的缩写版本。同时定义了伸缩容器的主轴和侧轴
    *  主轴：row从左到右，column从上到下
    *  侧轴：nowrap单行，wrap多行
    */
    flex-flow: row wrap;
    /* Then we define how is distributed the remaining space
    * 主轴的对齐方式。flex-start 左对齐，flex-end右对齐，center居中，space-between两端对齐，space-around平均分布
    */
    justify-content: space-around;
}
.flex-item {
    background: tomato;
    padding: 5px;
    width: 200px;
    height: 150px;
    margin-top: 10px;

    line-height: 150px;
    color: white;
    font-weight: bold;
    font-size: 3em;
    text-align: center;
}
```

## 属性介绍
1.display（flex container）
```
display: other values | flex | inline-flex;
```
2.flex-direction（flex container）
这个主要用来创建主轴，从而定义了伸缩项目放置在伸缩容器的方向。
```
flex-direction: row | row-reverse | column | column-reverse
```

* row(默认值)：在“ltr”排版方式下从左向右排列；在“rtl”排版方式下从右向左排列。
* row-reverse：与row排列方向相反，在“ltr”排版方式下从右向左排列；在“rtl”排版方式下从左向右排列.
* column：类似 于row，不过是从上到下排列.
* column-reverse：类似于row-reverse，不过是从下到上排列。

属性太多了……
基本上都是在定义如何排列，如何对齐，要如何分布，排列方式，内部的排列方式，有正序就有对应的倒序方法。


[Reference](https://segmentfault.com/a/1190000002910324#articleHeader5)


# Media Query
## 注意顺序问题（写在后面的属性会覆盖掉之前的属性）
@media (min-width: 768px){ //>=768的设备 }
@media (min-width: 992px){ //>=992的设备 }
@media (min-width: 1200){ //>=1200的设备 }
如果你把@media (min-width: 768px)写在了下面那么很悲剧，
@media (min-width: 1200){ //>=1200的设备 }
@media (min-width: 992px){ //>=992的设备 }
@media (min-width: 768px){ //>=768的设备 }
因为如果是1440,由于1440>768那么你的1200就会失效。

max-width就要把大的写在最前面，小的在下面