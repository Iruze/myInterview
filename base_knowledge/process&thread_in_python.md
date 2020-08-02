# python中的多线程，多进程，协程

- [Python多进程、多线程和协程简介](https://www.cnblogs.com/dogecheng/p/11439912.html)

- [Python进程、线程、协程详解](https://www.cnblogs.com/zhangliang91/p/10547551.html)


# python中的协程
#### 什么是协成
<details>
  <summary>展开</summary>
  协程是一种用户态的轻量级线程，协程的调度完全由用户控制。协程拥有自己的寄存器上下文和栈。协程调度切换时，将寄存器上下文和栈保存到其他地方，在切回来的时候，恢复先前保存的寄存器上下文和栈，直接操作栈则基本没有内核切换的开销，可以不加锁的访问全局变量，所以上下文的切换非常快。
</details>

#### 协成与线程比较
<details>
  <summary>展开</summary>
1). 一个线程可以拥有多个协程，一个进程也可以单独拥有多个协程，这样python中则能使用多核CPU。

2). 线程进程都是同步机制，而协程则是异步

3). 协程能保留上一次调用时的状态，每次过程重入时，就相当于进入上一次调用的状态

</details>

#### python协成实现 生产者－消费者
参考：　https://www.cnblogs.com/fcyworld/p/6275563.html

协程的实现为协作式而非抢占式的，这是和进程线程的最大区别。在Python中，利用yield和send可以很容易实现协程。
<details>
  <summary>首先复习下生成器</summary>
  
如果一个函数使用了 `yield` 语句，那么它就是一个生成器函数。当调用这个函数时，它返回一个迭代器。当第一次调用 `__next__()` 时候，生成器函数主体开始执行，遇到 `yield` 表达式时候终止。

当使用`__next__()`方法时候，`yield value`语句返回`None`；当使用`send(v)`方法时候，yield value返回v。也就是说，`__next__()`方法相当于`send(None)`方法
</details>

```python3
def consumer()
    while True:
        line = yield                            #line接收的是yield这个表达式的返回值！
        print(line.upper())


def productor():
    with open('text.txt') as file:
        for i, line in enumerate(file):
            yield line
            print("{0} lines".format(i))


c = consumer()
c.__next__()                                   #手动启动生成器，注意在Python3.X中不是c.next()
for i in productor():
    c.send(i)
```
