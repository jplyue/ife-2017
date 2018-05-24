真是一个恼人的页面==||

## Q1 外间距合并
使用padding-top


## Q2 悲伤的ABOUT TECHNOLOGY
first-letter字号变大之后，下划线也变粗了。
A: 使用了border-bottom，还对h3使用了inline属性，好让border-bottom紧贴底部。

搜索到了    font-variant: small-caps; 这个属性，最后也不得而知答主是如何解决的。


## Q3 前端前端前端前端前端前端 ....................前端
对目录结构使用dl dd dt布局我有着迷一般的执着==但是尝试了许久之后我放弃了。手动打上了这些...

## Q4 首字母下沉
```
#row3 > .left p:first-of-type {
    text-indent: 0;
}

//记得使用float
#row3 > .left p:first-of-type:first-letter {
    float: left;
    font-size: 70px;
    line-height: 70px;
}
```