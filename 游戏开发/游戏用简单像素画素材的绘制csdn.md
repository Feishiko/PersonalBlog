### 你需要10min来阅读这篇文章

突然想谈谈个人对游戏开发的时候绘制素材这一方面的见解。我不是专业搞美术的，目标也是能用就行，能看就行，今天就来谈谈如何在**只有***少量***基础的情况下绘制出能用的像素画素材**。

- - -

# 预备知识

- 形状
- 结构
- 比例
- 透视
- 线条
- 颜色

* * *

## 形状

无论是像素画还是插画，任何一种形式对于形状的把控都有很高的要求，有时候画出来的东西怪怪的，可能就是形状没有抓好的问题。特别是像素画，有时候差一个像素带来的视觉效果就有很大的不同。

**圆形**、**矩形**、**三角形**，是比较基础的三种形状，它们有着不同的属性。

**圆形**：柔和 

![Circle](https://img-blog.csdnimg.cn/img_convert/96f46fd0b7d7f3db6472ae11b517afe1.jpeg)

**矩形**：稳定

![Rectangle](https://img-blog.csdnimg.cn/img_convert/ec19111eae60f3959f1fd28de59d6ca6.jpeg)

**三角形**：危险

![Triangle](https://img-blog.csdnimg.cn/img_convert/0b5ceb7e16500632dd7ee828a0e9e5bc.jpeg)

不同的**形状**所表现的**功能**是不一样的，不同的形状带给人的感受也是不一样的，然后我们就可以用一些基础形状来搭建我们复杂的各种物体了。

因为像素画的尺寸很小，所以用**色块**来画比起插画会更方便一些，当然人各有所好，关于我自己是比较常用色块的。

比如说我们要画一个药水瓶，让我们先仔细观察一下药水瓶是什么样的，然后通过观察，去刨析出其形状是什么样的，画在纸上透视是什么样的，结构是什么样的，比例是怎么样的，最后是什么样的颜色看上去会更符合需求。

药水瓶有瓶底，瓶身，有个管口，有个软木塞，我们可以把各自的部位抽象成对应的形状，方便我们后续的工作。

![Shapes](https://img-blog.csdnimg.cn/img_convert/b434ffd23af1ed472ebc116338707cfb.png)

当然后续我们可以修正一下形状，调整一下位置，让其看起来更像一个药水瓶。然后填充对应的颜色，补充对应的细节。

## 结构

形状做到的是看上去是什么样，看上去是这个样，看上去是什么感受。结构则是所要画的物体在我们大脑中的**建模**应该是什么样，从各个角度观察应该用什么形状去把它画出来。

还是刚刚的药水瓶，这次我们要做的工作是把要画的物体在自己的头脑中立体化，底下是一个球形，上面是一个圆柱形，软木塞是一个倒圆台。

## 比例

为了确保我们的结构足够的准确，看着自然，我们要回到现实中或者给定的参考图中的各种高度比，长度比，按照这个比例进行头脑中的建模。很多时候看着**不像**的问题也可能是比例没有把控好。

![Human Ratio](https://img-blog.csdnimg.cn/img_convert/1a7476e5d670f9425c9613d4de98dce0.jpeg)

## 透视

透视有分为**一点透视**，**二点透视**，还有**三点透视**，最简单的一个原则是**近大远小**，实际情况下，我们在绘画的时候，特别是画物体，很难说只是单独的一点透视或者二点透视，需要多种相互结合，不过透视能够帮助我们去寻找物体之间的远近关系，以及要怎么从不同角度去看，去画这个物体。

这方面的知识点我在这里不展开详细的说明。

## 线条

这里专门把线条抓出来讲，这里的线条不仅仅是你看到的有些像素画外面的outline，也包括没有outline的一些图块出来的像素画，因为像素画的限制性，每一个像素都非常重要，这里简单谈几个让像素画线条表现的更自然的几个案例。

![Jagged](https://img-blog.csdnimg.cn/img_convert/098337cd0e2daecb55ca96b66b4cbf78.png)

一般来说，我们叫这种情况**Jagged**，这样的线条，看上去并不会很自然，实际上看上去会很不舒适，为了解决这种问题，我们可以选择一开始的时候就选择aseprite的**完美像素（Pixel-Perfect）**，或者手动修正。

具体来说是每次落差的像素格子要徐徐递增徐徐递减，不能一下子落差太大。

![WhatJagged](https://img-blog.csdnimg.cn/img_convert/655dc9ce97ea9e1eb60ce5fc88de6fce.png)

解决方法就是让段与段之间的差不要那么大，尽可能平缓一些。

![Solvejagged](https://img-blog.csdnimg.cn/img_convert/90d796459aa2f509cf36beb5ffdd7a0e.png)

顺便提醒一下，有时候尺寸过小弯曲的线条画不下可以通过改变一些饱和度明度之类的值造成视觉上的一种误差以为有弯曲实际上是两个像素点，但是看自己的像素画风格，少颜色风格的那没有必要

## 颜色

HSB色盘是个很好的颜色模式，大家应该也都知道RGB色盘，但是RGB色盘对于调色来说并不合适，一般我们用HSB调色。

个人推荐创建一个自己用的调色板，对于让自己游戏的颜色统一有着非常关键的作用，如果不会调色也没关系，网上都有现成的调色盘，拿过来用就行，而且颜色都很好看，这个不会有版权问题。

另外，Aseprite里面有非常多的预设调色盘，也非常推荐拿来用。

这是个人自己做的调色盘。

![Palette](https://img-blog.csdnimg.cn/img_convert/0013242f26fa667bf0e3c1fe1f36acfa.png)

关于颜色我还有一些要说的，大家可以试试颜色比较少的那种呈现形式，一个游戏里面只有几种颜色，这边有几种风格的游戏感兴趣的可以看看，[Downwell](https://store.steampowered.com/app/360740/Downwell/), [Apple Slash](https://store.steampowered.com/app/1127850/Apple_Slash/), [Red Death](https://store.steampowered.com/app/591560/Red_Death)

![Downwell](https://img-blog.csdnimg.cn/img_convert/06054bcc5ec21ac4d818d3be2366a5f0.jpeg)

![Apple Slash](https://img-blog.csdnimg.cn/img_convert/689a443c77e3554478d539c2c4b502b7.jpeg)

![Red Death](https://img-blog.csdnimg.cn/img_convert/7ba4aca3c2f7ea6b09ada5e72c0261e9.jpeg)

- - -

# 正文

- 艺术风格
- 便捷工具
- FX
- Shader

- - -

## 艺术风格

在这里，我会推荐几种实现起来比较简单的像素画风格。

### 雅达利

顾名思义，雅达利的风格，这种风格的像素画实现起来简单，但需要搭配一些简单的shader来实现一些屏幕效果。大概是**扫描线**。

这里有个推荐的游戏，[FAITH](https://store.steampowered.com/app/1179080/FAITH_The_Unholy_Trinity/)，有点放私货的意味了。

![FAITH](https://img-blog.csdnimg.cn/img_convert/ec41c771c4eb82df2274981cb345aafa.jpeg)

这是个恐怖游戏，画面雅达利风格，不过不是全部的雅达利，很多地方还有许多动画CG，实现起来应该不难，但是非常的丝滑。

故事方面也挺牛逼的，嘛，不能剧透，可以看看steam宣传片。一共三章，steam上这个版本是第三章夹杂前面两章一起打包发售的，最近刚刚发售。

### 极简像素

这种风格比前一种要常见太多了，制作也很简单，而且表现效果也很不错。

这边照样上游戏，[TowerClimb](https://store.steampowered.com/app/396640/TowerClimb/)，这个游戏是我最喜欢的roguelite（全是私货），讲的是A man climb with hope，玩这个游戏的朋友特别喜欢拿Spelunky类比，因为这个游戏和Spelunky的相似度还是挺高的，不过前提说一下，玩法还是完全不一致的，Spelunky2和TowerClimb我都很喜欢，我都是这两个游戏的粉丝。这个游戏精细的地方体现在像素动画，shader，特别是音乐。

![TowerClimb](https://img-blog.csdnimg.cn/img_convert/a0591f2168f5c9f7f1c51ce7a2e0931e.jpeg)

这个游戏是别人推荐给我的，还没买，但是也是这种风格。[Environmental Station Alpha](https://store.steampowered.com/app/350070/Environmental_Station_Alpha/)，是一个类银河恶魔城。

![Environmental Station Alpha](https://img-blog.csdnimg.cn/img_convert/439fb008eb9eec1fc2f03244b1032169.jpeg)

### ISO

这种风格应该不少见，第一次看可能以为是普通的二点透视，但是实际上两边并没有**消失点**！

ISO是Isometric的简称，在ISO的世界里遵循平行透视的原则，因此也不会存在消失点，这方面的游戏我玩的少，上一个老游戏，[Game Dev Story](https://store.steampowered.com/app/1847240/_Game_Dev_Story/)。

![Game Dev Story](https://img-blog.csdnimg.cn/img_convert/8b32281b65af6d4dfbb866ed1f636dc2.jpeg)

### ASCII

由像素组成的也是像素画（错乱）

这种风格也应该会挺少见的，主要是由字符组成，所以做ASCII游戏在美术上会非常省力，只需要用字体就能画出一个个贴图（

不过ASCII游戏由于**可观性**不是那么高嘛，玩的人就相对会少一些，所以除非你是做**Roguelike**，或者就指定了要做**ASCII游戏**，那我不建议你用这个风格。

照例上图，[Nethack](http://www.nethack.org/)

![Nethack1](https://img-blog.csdnimg.cn/img_convert/5c4a9a80ab648a9d8cb39081b140480f.png)

![Nethack2](https://img-blog.csdnimg.cn/img_convert/fd75162fe149cdd840e17c831f7aa053.jpeg)

## 便携工具

### 选择框

如果有的时候位置不太对，可以直接框起来然后移动一下位置，或者有的时候需要某一部位整体往某个方向移动几个像素，这个时候选择框就派上用场了。

![选择框](https://img-blog.csdnimg.cn/img_convert/dc01b72e0ad0611533c2f340175b2e31.gif)

### Jumble Tool

Aseprite里面的一个工具，大概是个画笔，类似于模糊工具，但是其作用是发生在像素画上的，它会将笔刷内的像素位置错排，造成一种很神奇的效果。

![Jumble Tool](https://img-blog.csdnimg.cn/img_convert/e77f12e1dfa6fad57605528c65975a58.gif)

### 镜像工具

用来画一些对称的图形比较方便

![镜像工具](https://img-blog.csdnimg.cn/img_convert/d85efd5c0c39922f254c9b82a6d61b85.gif)

### 重复tiles

可以轻松画出无缝贴图

![重复tiles](https://img-blog.csdnimg.cn/img_convert/742abdcc38122dcc7ef1c68d73ba7882.gif)

当然，此外还有很多小工具我们可以拿去用的，可以自己多多探索一下。

## FX

这个算投机取巧吧（

在aseprite里面有FX功能，里面的**Convolution Matrix**点进去之后可以给自己的素材加点花，不过这个适当加。

还有就是有时候我们希望给自己的素材加点outline，那就可以直接FX那一块添加Outline。比如黑色的outline，有些时候为了显得更可爱一些会用白色的outline，当然怎么用看自己。还有人会根据向内的像素颜色手动选择对应的outline。

## Shader

这个应该就不用我多说了，懂得都懂。

**GLSL ES**，许多游戏引擎都有提供shader的实现方法，但是比较常见的版本还是GLSL ES。

像Unity，Godot的Shader是进一步封装过的，但是其更原始的GLSL ES还是需要了解。

Shader的世界非常好玩，主要分**片元着色器**和**顶点着色器**，我们像素画主要用片元着色器，有时候增加一些合理的效果能为画面加分，但是请也**不要滥用**。

如果你没用学过Shader语言，这里我推荐看看[Book of Shaders](https://thebookofshaders.com/)，作为入门还是非常不错的。

希望你喜欢本期内容！

个人itch.io链接[点这里](https://feishiko.itch.io/)
个人Twitter链接[点这里](https://twitter.com/FeishikoMonster)

也**不要滥用**。

如果你没用学过Shader语言，这里我推荐看看[Book of Shaders](https://thebookofshaders.com/)，作为入门还是非常不错的。

希望你喜欢本期内容！

推荐从[Github](https://github.com/Feishiko/PersonalBlog/tree/main)这边看本人的博客以获得最佳体验

个人itch.io链接[点这里](https://feishiko.itch.io/)

个人Twitter链接[点这里](https://twitter.com/FeishikoMonster)

2022/10/27
