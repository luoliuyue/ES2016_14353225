#### Lab3 DOL实例分析&编程
ROS（Robot operation system）是一套框架，底层提供硬件驱动，软件层面支持通用的文件 格式。我们主要用它的仿真功能
##### ROS配置
根据网上的教程输入命令对ROS进行安装

*添加source,list： `sudo sh -c 'echo "deb` 
`http://packages.ros.org/ros/ubuntu $(lsb_release -sc)main" >`
`/etc/apt/sources.list.d/ros-latest.list' `

*添加keys： `sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116 `

*确保虚拟机的软件包索引是最新的 `sudo apt-get update `

*桌面完整版安装 `sudo apt-get install ros-jade-desktop-full `

*初始化rosdep： `sudo rosdep init`   `rosdep update `

*环境配置 `echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc source ~/.bashrc` 

*安装rosinatall  `sudo apt-get install python-rosinstall`
##### 测试使用ROS
新开一个终端，输入指令： `roscore `
再打开第二个新终端，输入指令： `rosrun turtlesim turtlesim_node` 然后会得到一个乌龟的界面,如下图所示：
<img src="http://wx4.sinaimg.cn/mw690/d6c2dee9ly1fbzrt1jey3j20g40fu74w.jpg" width="200" alt="configure"/>
打开第三个终端，输入指令 `rosrun turtlesim` `turtle_teleop_key`
由键盘控制小乌龟移动
<img src="http://wx2.sinaimg.cn/mw690/d6c2dee9ly1fbzriylb2xj20q10ic4ax.jpg" width="300" alt="configure"/>
<img src="http://wx2.sinaimg.cn/mw690/d6c2dee9ly1fbzrj5kqwsj20xn0j3tva.jpg" width="300" alt="configure"/>
可见小乌龟已经多次碰壁了，可以确定ROS已经配置完成可以正常使用了
##### 实验体会
这次配置ROS照着教程输入命令就可以了，也没有遇到什么问题。
