# TCP & UDP

- [TCP的三次握手与四次挥手理解及面试题（很全面](https://blog.csdn.net/qq_38950316/article/details/81087809)

- [DNS递归查询与迭代查询](https://www.cnblogs.com/qingdaofu/p/7399670.html)

#### tcp拔掉网线之后发生了什么？     
- [TCP socket拔网线判断](https://www.cnblogs.com/mayingkun/p/8076045.html)
- [TCP连接拔掉网线后会发生什么](https://blog.csdn.net/larry_zeng1/article/details/78437050?utm_source=blogxgwz9)
- [TCP长连接和短连接的区别](https://blog.csdn.net/yanglianzhuang/article/details/87966866)

#### 理解rpc
- [从 0 到 1：全面理解 RPC 远程调用！](https://baijiahao.baidu.com/s?id=1637758852641939872&wfr=spider&for=pc)
- [花了一个星期，我终于把RPC框架整明白了！](https://developer.51cto.com/art/201906/597963.htm)

# HTTP & HTTPS
- [https 建立连接过程](https://www.cnblogs.com/felixzh/p/8316710.html)

- [Https 建立安全连接的过程（SSL原理)](https://blog.csdn.net/xiaopang_yan/article/details/78709574)

- [HTTPS 建立连接的详细过程](https://www.cnblogs.com/liyuhui-Z/p/7844880.html)

- [SSL/TLS 双向认证(一) – SSL/TLS工作原理](https://blog.csdn.net/ustccw/article/details/76691248)

- [HTTP请求返回状态码整理](https://blog.csdn.net/hualf/article/details/78989618)

#### 什么是短链接
- [短网址(short URL)系统的原理及其实现](https://segmentfault.com/a/1190000012088345?utm_source=tag-newest)

# RSA加密算法
- [RSA加密算法(一)-阮一峰](http://www.ruanyifeng.com/blog/2013/06/rsa_algorithm_part_one.html)

- [RSA加密算法(二)-阮一峰](http://www.ruanyifeng.com/blog/2013/07/rsa_algorithm_part_two.html)

<details>
    <summary>RSA算法小结</summary>

公私钥选择:
```shell
1). 选取质数p, q, 得到 n = p * q
2). 欧拉函数 &(n) = (p - 1)(q - 1)
3). 选e, 1 < e < &(n), 且e, &(n)互质
4). 选d, ed % &(n) = 1
``` 

加密过程:
```shell
加密: c = m^e % n
解密: m = c^d % n
```
</details>
