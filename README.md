# SimpleThreadPool

</br>
<p><strong>简介</strong></p>
<p>简单线程池。当空闲线程太少时会自动扩容，当空闲线程太多时，会自动缩小线程数</p>

</br>

<p><strong>三种主要结构：</strong></p>
<p>&nbsp; &nbsp; &nbsp;--空闲线程链表，采用堆栈思想设计，底层std::list</p>
<p>&nbsp; &nbsp; &nbsp;--活动线程链表，采用队列思想设计，底层std::list</p>
<p>&nbsp; &nbsp; &nbsp;--任务链表，采用队列思想设计，底层std::list</p>

</br>

<p><strong>两种主要线程：</strong></p>
<p>&nbsp; &nbsp; &nbsp;--管理线程：当任务链表不为空时，给空闲线程链表里的线程分配任务，将它们加入活动线程链表，</p>
<p>&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp;然后通知活动的线程执行任务;检查查空闲链表数，过多则减少线程，过少则增加线程</p>
<p>&nbsp; &nbsp; &nbsp;--管理任务：当收到任务到来的信号时会通知管理线程</p>

</br>
<p><strong>搭建方法：</strong>在终端中运行make</p>
