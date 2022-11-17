在Shader中要生成随机数，就要生成Noise图，通常来说我们都知道可以用sin+fract函数。这种方法也叫Sinhash。

$f(x) = fract(sin(x)*a)$

当**a**越来越大的时候，你会发现其函数图像会变得非常随机的样子，我们取其中一段就实现了**随机**。**fract**函数的意思是取小数部位。

![Book of shaders](https://pic.imgdb.cn/item/63760bda16f2c2beb152dded.png)

这也是**The Book of shaders**介绍的方法，这边是对应章节的链接 https://thebookofshaders.com/10/

我们随后可以用这个方法生成一些噪声图。

简单封装一下大概是这个样子。

![sinhash](https://pic.imgdb.cn/item/63760c4716f2c2beb15378ea.png)

我们可以用dot也就是dotproduct也就是**点积**，这种计算方法会更好一点。输入一个二维向量，然后输出一个范围在0-1的float浮点数。之后再乘以一个更大的数，我们就实现了基本的随机。

**随机数**会有影响，你可以自己随便选一个数字，但是可能会在具体功能上有一定的偏差，如果不需要解决问题那就用自己随便想的好了。

让我们再来看看另一种随机数生成方法，**Fracthash**。

这种方法没有用到sin，但是同样需要fract。

这是封装后的代码。

![fracthash](https://pic.imgdb.cn/item/63760e4816f2c2beb156d778.png)

这个也不是我自己想出来的，之前写了一个shader评论区下面有人给我指点的意见。

![comment](https://pic.imgdb.cn/item/63760eb316f2c2beb157688c.png)

直接调用这个函数，我简单的将两个生成方法放在一起做了对比

![对比](https://pic.imgdb.cn/item/63760fb016f2c2beb15914ab.png)

左边是**sinhash**，右边是**fracthash**，这咋看没啥区别，但是在后面加了一个**iTime**让其动起来后会发现sinhash有一丝割裂感，而**fracthash**会更加自然。

具体可以看看我在shadertoy写的这个shader：https://www.shadertoy.com/view/mssXz7

本期内容大概就是这些，希望对你有帮助。