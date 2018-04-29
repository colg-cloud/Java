# java-juc 多线程集合

## 1、Java JUC简介
- 在Java5.0提供了java.util.concurrent(简称JUC)包，在此包中增加了在并发编程中很常用的实用工具类，用于定义类似于线程的自定义子系统，包括线程池、异步IO和轻量级任务框架。提供可调的、灵活的线程池。还提供了设计用于多线程上下文中的Collection实现等。

## 2、volatile 关键字-内存可见性
### 1. 内存可见性
- 内存可见性（Memory Vislbility）是指当某个线程正在使用对象状态而另一个线程在同时修改该状态，需要确保当一个线程修改了对象状态后，其他线程能够看到发生的状态变化。

- 可见性错误是指当读操作与写操作在不同的线程中执行时，我们无法确保执行读操作的线程能适时的看到其他线程写入的值，有时甚至是根本不可能的事情。

- 我们可以通过同步来保证对象被安全的发布。除此之外我们也可以使用一种更加轻量级的volatile变量。

### 2. volatile 关键字
- Java提供了一种稍弱的同步机制，即volatile变量，用来确保将变量的更新操作通知到其他线程。可以将volatile看作一个轻量级的锁，但是又与锁有些不同：

	对于多线程，不是一种互斥关系
	不能保证变量状态的"原子性操作"

## 3、源自变量-CAS算法