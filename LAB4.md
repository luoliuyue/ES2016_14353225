#### Lab4 Deadlock
##### 代码分析
关键字 synchronized:

当它用来修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多只有一个线程执行该段代码。

<img src="http://wx4.sinaimg.cn/mw690/d6c2dee9ly1fbzp0idk97j216p0wptka.jpg" width="300" alt="configure"/>

当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞。 

当t.start(),之后，线程t就被插入到调度队列里，当调度到他的时候，就跑run()里面的代码：

<img src="http://wx2.sinaimg.cn/mw690/d6c2dee9ly1fbzp0nghnvj20pb0vg1kx.jpg" width="200" alt="configure"/>

##### 死锁分析
一个线程在执行了一段时间之后，自己的时间片耗尽了的话，就会将CPU资源给到另一个线程继续执行。 

当我们调大count的值，在while循环里消耗的时间也会变大，所以methodA得到的时间就会越少。 

出现的情况就是在执行methodA的时候，还没有执行完成时间片就已经被耗尽了。此时主线程占有了A的信号量却没有执行下一步。跳转到执行线程t，t线程获得B方法的信号量调用methodB,但这是A信号量已经被占用，所以t线程被阻塞，回到主线程，所以就有了循环等待，形成死锁。

##### 实验结果
形成了死锁的结果：

<img src="http://wx1.sinaimg.cn/mw690/d6c2dee9ly1fbzp0q6qvxj20t00sstfc.jpg" width="300" alt="configure"/>
##### 实验感想
死锁的概念在操作系统已经学习过了，并且也做过了详细的实验，所以这次实验很容易就做完了。前几次没有产生死锁以为写错了，跑多几次就可以了。 
