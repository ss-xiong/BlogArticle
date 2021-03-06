## Cgroup和Namespace了解一下

Docker的实现，主要基于Cgroup和Namespace这两个内核特性。

### Cgroup

Cgroup是control group简称，名为控制组，主要作用是资源控制。原理是将一组进程放在一个控制组里面，并通过给这个控制组分配指定的可用资源，达到控制这一组进程可用资源的目的。

### Namespace

Namespace又称为命名空间，主要作用是访问隔离。它的原理是针对一类资源进行抽象，并将其封装在一起提供给一个容器使用，对于这类资源，因为每个容器都有自己的抽象，而他们彼此之间是不可见的，所以就可以做到访问隔离。

对于Linux容器的最小组成，除了上面两个抽象的技术概念还不够，完整的容器可以用以下公示描述： 
容器 = Cgroup + Namespace +rootfs + 容器引擎（用户态工具）。 
其中各项功能分别为： 

+ Cgroup：资源控制； 
+ Namespace：访问隔离； 
+ rootfs：文件系统隔离； 

