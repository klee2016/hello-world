# hello-world
test
看见了看见就看了

1.极客时间上的课程  (八门课)
   1.数据结构（80讲）  
     
   2.linux性能优化实践 65 []
   
   3.C++ 30 []
   
   4.网络协议 51 []  
   
   5.RPC 29 []  
   
   6.架构 60 []
   
   7.mysql 49 []  
   
   8.检索  29 []
   
 2.ACE
  文档  
   ACE程序员指南-网络与系统编程的实用设计模式[1].pdf
       [8-26 8-27]    
		 第2章  怎样构建ACE并在你的程序中使用它 
		 第3章  使用ACE日志设施 
		 
  上 上篇：ACE技术论文集.pdf
  
  中  中篇：ACE程序员教程.pdf  
  [9-9] 分层体系接口 三个基本的层 
	  一    1.操作系统适配层 
	          屏蔽平台差异
			2.C++ 包装层 
				并发同步、IPC、内存管理组件、定时器类、容器类、信号处理、文件系统组件、线程管理
			3.框架和模式层
                特定通信领域的设计模式 [事件处理、连接和初始化组件、组件流、服务配置组件]
      二  IPC SAP 进程间通信服务访问点包装
	         ACE_IPC_SAP[ACE_SOCK]  [ACE_TLI] [ACE_SPIPE] [ACE_FIFO]
		  2 socket类 ACE_SOCK
		       Dgram UDP 
			   Stream  TCP 
			   Acceptor Connector Stream 
			   ACE_SOCK_Acceptor [被动建立连接]
			   ACE_SOCK_Connector [主动建立连接]
			   ACE_SOCK_Dgram [UDP]
			   ACE_SOCK_IO []
			   ACE_SOCK_Stream []
			   ACE_SOCK_CODgram []
			   ACE_SOCK_Dgram_Mcase [多点传送]
			   ACE_SOCK_Dgram_Bcast [广播]
			   多点传送
		  3.ACE内存管理   ACE_Allocator  ACE_Malloc
		       a
			   ACE_Alloctor ACE_Static_Allocator ACE_Cached_ALlocator ACE_New_Allocator
			   a.1
			   
			   
			   
		  6. 反应器Reactor 用于事件多路分离和分派的体系结构模式
   下 下篇：ACE应用实例.pdf

3.操作系统(现代操作系统  深入理解操作系统)
    现代操作系统
	
	深入理解操作系统
	
	
4.编程
  a.高编
    
  
  b.effcitve C++ 
   [8-26] 1.视C++是一个语言联邦   C++四个次语言 [  C    Object-oriented C++  Template C++  STL ]  C++高效编程守则视状况而变化，取决于使用C++的那一部分 
                 C++高效编程守则视状况而变化，取决于使用C++的那一部分
          2.尽量以const enum inline 替换#define  [ 1.const 替换 2.emum hack 3.macro inline ]  
		      符号表 作用域 函数调用 宏的副作用
   [8-27] 3.尽可能使用const   
		        const 在星号左边 表示被指物是常量 如果在右侧表示本身
				const 形参 返回值
				const 成员函数  
				      const成员函数不可以改变对象内的任何non-static成员变量
					  bitwis constness  physical constness          logical constness  mutable
		  4.确定对象在使用前已被初始化
                1.赋值 初始化 的区别
				2.
				3.static对象 [gobal 对象 定义于namespce作用域内的对象 class内  函数内 file作用域]定义为static的对象 函数内的local staic 其他的non-local static
				    编译单元
	[8-31] 
	     5.了解C++默默编写并调用了那些函数 [空类 default构造函数 copy构造函数 析构 copy assignment] 函数被需要编译器会创建他们
	[9-1]
	     6.若不想使用编译器自动生成的函数，就该明确拒绝
		   为驳回编译器自动提供的机能，可将相应的成员函数声明为private并且不予实现。upcopyable base class
		 7.为多态基类声明virtual析构函数
		 8.别让异常逃离析构函数 
	[9-2] 
	     9.绝不在构造和析构过程中调用virtual函数   
	       基类和子类在构造期间呈现不同的类型
		 10.令operator = 返回一个reference to *this
		 11.在operator=中处理自我赋值   
		    证同测试
            copy and swap	 
    [9-7]			
		 12.赋值对象时勿忘其中的每一个成分  copying函数 [拷贝构造 赋值运算符重载]
             copying函数应该确保赋值对象内的所有成员变量及所有base中的变量
          	 不要尝试以一个copying函数调用另个一copying函数，应该将功能部分抽取出来，共同调用。
		 13.以对象管理资源    share_ptr[normal] auto_ptr[after copy is null]
    [9-8]
	     14.在资源管理中小心copying行为 
		 15.在资源管理类中提供对原始资源的访问   share_ptr  auto_ptr get()方法
		 16.成对使用new和delete时 要采用相同的形式
		 17.以独立的语句将newed对象置入智能指针   
	[9-9] 设计与说明 
		 18.让接口容易被使用，不易被误用 
      	 19.设计class 犹如这几 type [1.新的对象应该如何被创建和销毁 2.对象的初始化和赋值 3.对象被以值传递时 copy构造函数 4.合法值  5.继承 6.新的对象要什么转换        7.可以操作这个对象的函数 8.什么函数应该被隐藏 9.成员权限合理分配 10.新的class是否是必须的] 
         20.以pass-by-reference-to-const替换pass-by-value		
         21.必须返回对象时，别返回引用
		 22.将成员变量声明为private  其实只有两种访问控制权限 提供封装和不提供封装
		 23.宁以non-member  non-friend member 替换member函数
         24.若所有参数皆需要类型转换，请为此采用non_member函数     member的反面是no member不是friend
         25.写一个不抛出异常的swap函数   		 




		 
  c.more effectivate C++  
     [8-27] 
	      1.指针和引用的区别 
		  2.尽量使用C++类型风格的转换
		  3.
   
  
  d.leetcode  100道题   
      递归  
	      剑指offer 28
          17   
		  48	
          46
          322  
          101 ok
          91  ok
          108 ok	  

		  
		  
   e. effective STL
    [9-7]
     1.仔细选择容器   [标准 非标准  序列 关联] 
	 2.
	 

5.项目经验
  软件管理
    netconf协议
    corba
	
  微服务
     杨波的微服务
   
  项目中的进程管理机制
    
	
  任务式升级
  
  
  防火墙  
    nefilter  
	  五个HOOK函数 
	  四张表
	内核模块
      
  极速交易平台
   
  
  
6.设计模式
   [9-8]
       1.开始   
	        分类
			  创建型模式 
			      这些设计模式提供了一种在创建对象的同时隐藏创建逻辑的方式，而不是使用 new 运算符直接实例化对象。这使得程序在判断针对某个给定实例需要创建哪些对象时更加灵活。
				  工厂模式、抽象工厂模式、单例模式、建造者模式、原型模式
			  结构型模式  
			      这些设计模式关注类和对象的组合。继承的概念被用来组合接口和定义组合对象获得新功能的方式。
				  适配器模式、桥接模式、过滤器模式、组合模式、装饰器模式、外观模式、享元模式、代理模式、				  
			  行为型模式
			      这些设计模式特别关注对象之间的通信。	
				  责任链模式、解释器模式、迭代器模式、中介者模式、备忘录模式、观察者模式、状态模式、空对象模式、策略模式、访问者模式     
			  J2EE 设计模式
			      这些设计模式特别关注表示层。这些模式是由 Sun Java Center 鉴定的。
				  MVC 模式、业务代表模式、组合实体模式、数据访问对象模式、前端控制器模式、拦截过滤器模式、服务定位器模式、传输对象模式
			设计模式的六大原则
			  1、开闭原则       对扩展开放，对修改关闭 
			  2、里氏代换原则   任何基类可以出现的地方，子类一定可以出现
			  3、依赖倒转原则   针对接口编程，依赖于抽象而不依赖于具体。
			  4、接口隔离原则   使用多个隔离的接口，比使用单个接口要好。它还有另外一个意思是：降低类之间的耦合度。
			  5、迪米特法则，又称最少知道原则  一个实体应当尽量少地与其他实体之间发生相互作用，使得系统功能模块相对独立。
			  6、合成复用原则 尽量使用合成/聚合的方式，而不是使用继承
			  

7.常识学习
  分布式事务

  分布式锁			
  
8.深度探索C++对象模型
     软件组件三大规格  

				
				





