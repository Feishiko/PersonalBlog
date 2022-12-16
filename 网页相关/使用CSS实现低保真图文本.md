最近在学网页前端，想试着实现低保真图下的那种**伪文本**，然后我试着去实现了一下。

首先在HTML里面写下以下文本

```html
<!--HTML-->
<div class = "colright">
            <span class = "firstlow"> </span><br>
            <span class = "low"> </span><br>
            <span class = "low"> </span><br>
            <span class = "low"> </span><br>
            <span class = "low"> </span>
        </div>
```

我一般会在一个新块定义一个class，这样方便后续操作，然后接着因为我们要在对应行进行一定的操作，所以每一个span都有一个class，并且每一行都要**手动换行**。

每个span里面的内容都是一个空格，主要的效果还是在CSS里面实现。

```css
/*CSS*/
.low {
    width: 10em;
    border-width: .5em;
    border-style: solid;
    border-radius: 2.9em;
    zoom: 200%;
    display: inline-block;
}

.firstlow {
    margin-left: 2em;
    width: 8em;
    border-width: .5em;
    border-style: solid;
    border-radius: 2.9em;
    zoom: 200%;
    display: inline-block;
}
```

CSS部分主要分两个部分，一个是low类里面进行操作，一个是firstlow类里面进行操作。**控制第一行和其他行不一样**。

**width**属性控制低保真图文本的长度

**border-width**属性控制低保真图文本的宽度

**border-style**属性控制低保真图文本样式，因为本质是border

**border-radius**属性控制边缘光滑程度

**zoom**属性放大

**display:inline-block**保持文本以inline-block的形式display

**magin-left**属性控制第一行位置的偏移

最后结果大概是这个样子

![](https://pic.imgdb.cn/item/639c1793b1fccdcd361c977f.png)

希望本文章能帮助到你