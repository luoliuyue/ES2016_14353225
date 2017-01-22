#### Lab3 DOL实例分析&编程
##### 代码分析
src文件夹：各进程（生产者，消费者，处理模块等）的功能定义 
example1.xml：系统架构即模块连接方式定义 
/src 文件夹内包含2种文件：.c, 与对应的.h，就是实现的模块，就是.dot的框框的功能 描述。（每个模块要实现2个接口，xxx_init和xxx_fire两个函数，分别是初始化这个模 块是干了什么，以及这个模块开干的时候做什么） 
./example*.xml 里面定义了模块与模块之间是怎么连接的，就是有哪些框，哪些线， 比如A框跟B框用一根线连起来，他们就在一起了。 
xml是这样的：process就是那些框, sw_channel那些线, connection就是把线的那头连 到框的那头。

##### 实验任务

1. 修改example1，使其输出3次方数

2. 修改example2，让3个square模块变成2个

##### 实验结果
1. 修改example1

修改example1代码如下：
<img src="http://wx4.sinaimg.cn/mw690/d6c2dee9ly1fbzoiljsycj20lc0gj0yu.jpg" width="300" alt="configure"/>

结果：

<img src="http://wx2.sinaimg.cn/mw690/d6c2dee9ly1fbzoio3hh0j20ow0qvat4.jpg" width="400" alt="configure"/>

可以看到，修改前example1输出的结果是2次方数，修改后变为输出3次方数。
<br />
2. 修改example2
为了让squsre模块由三个变为两个，需要修改iterator，所以将variable的值由3改为2

修改example2代码如下：
<img src="http://wx1.sinaimg.cn/mw690/d6c2dee9ly1fbzoihk90bj20n80giwpu.jpg" width="300" alt="configure"/>

dot 图：

<img src="http://wx4.sinaimg.cn/mw690/d6c2dee9ly1fbzoijgrr4j216d0wvmze.jpg" width="600" alt="configure"/>

可见square由三个变为两个。


##### 实验感想

总的来说，这次实验的内容很好理解，工作量不大，主要是通过 2 个example 来熟悉 dol 的代码和结构。每个 dol 实例包括三个部分，生产者、平方模块、消费者，模块间通过通道连接，使用 iterator 来控制平方模块个数。每个 example 的 xml 文件里定义模块与模块之间的连接。

实验过程中被卡住的地方就是重新编译、运行的那个过程了，刚开始直接调用语句来编译、运行，输出的结果是未修改代码前的。通过对比其他的 example ，发现 example 运行过后会生成一些文件，把这些文件删除以后，再编译、运行就可以看到修改代码以后的效果了。
