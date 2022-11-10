# 《手写Spring：渐进式源码实践》 —— 书籍源码库

**这本书最大的价值是带着想学spring源码的读者，能有个门进去。避免像以前一样，东一榔头西一棒子没有体系化的学。**

**📝目录**

1. 内容介绍
2. [书籍购买](https://u.jd.com/4LapTH4)
3. 勘误记录 —— `非常感谢，读者提交阅读中发现的错字和问题。`

---

## 1. 内容介绍

`IOC`、`AOP`、`SPI`，Spring 给你的不只是一个开发框架，还包括它的设计思想。它通过解耦 Bean 对象的实例化过程，管理 Bean 的生命周期，来维护你在程序开发中所需对象使用过程。让你不需要刀耕火种般 new 一个对象，也不需要如 EJB 一样笨重臃肿的开发维护，而像春风一样润物(`万物皆可Bean`)细无声的使用。因此可以说它完全担得起 **Java 技术设计的顶峰**。

除了运用以外，Spring 框架也是众多码农，最能最先接触到的一个**源码级复杂项目**。任何初出新手村蜕变的码农，寻觅苦找的锻炼项目，都不如学习 Spring 源码来的痛快。从架构设计的复杂、从分治抽象的运用、从设计模式的驾驭，Spring 框架都是顶级的，也是最能给你带来丰富收获的。

但学习 Spring 源码难吗？难，难到编程个1-2年的研发，也不知道从哪下手学习。看到大部分资料和书籍也都是从一个知识点直接透析到骨头。没有阅读源码经验的小白，根本没法如编写者感同身受般学习，云里雾里一样的看，过眼云烟一样的忘。

为啥会这样，因为 Spring 发展太久了，源码太大了，主干核心源码外的繁枝末节有太多太多。就像沙发🛋左移套个套，套上盖罩，罩上铺块小布料。但除了沙发以外的套、罩、布料对初学源码的研发来说，并没有那么重要。我要的就是最初的沙发，最开始的木板，看看它的结构，闻闻它的味道。

**所以**，如果你想真的把 Spring 这个源码级复杂框架的设计和实现精髓吸收喽，就应该像开发一个项目一样，跟着小傅哥写一遍。只有这个项目是你写的，你才能知道哪些细节是如何处理的，那些设计是如何驾驭的。

## 2. 书籍购买

- 扫码下单，扫码下面👇🏻的二维码进行下单
- 链接下单：[https://u.jd.com/4LapTH4](https://u.jd.com/4LapTH4)

<div align="center">
    <img src="https://bugstack.cn/images/article/product/book/spring-t-04.png?raw=true" width="350px">
</div>

本书共21章；
- 第1 - 10章：主要介绍IOC 容器，逐步完善一个简单的Spring Bean 容器的相关功能，引入实例化策略、注入属性和依赖、设计应用上下文、处理Bean 对象的生命周期，以及实现感知容器对象的监听等。
- 第11 - 12章：主要介绍AOP 切面，基于JDK、Cglib 的动态代理、方法拦截、切点表达式等技术，将代理与Spring Bean 容器整合，提供AOP 切面功能。
- 第13 - 17章：扩展简单版Spring 框架的自动化功能，完成自动扫描注册、注解和代理注入，以及通过三级缓存处理对象的循环依赖等功能。
- 第18 - 21章：基于简单实现的Spring 框架整合JDBC、事务的功能，开发一个简单版的ORM 框架，并将ORM 框架整合到Spring Bean 容器中，介绍自定义代理对象的扫描和注册过程。

本书主要通过渐进式开发功能模块，以实现开发整个Spring 框架的核心源码。首先，每章开头都会列出难度和重点；然后，正文中会介绍要处理的问题、具体设计和实现代码；最后，给出测试验证和本章总结。

## 3. 勘误记录

### 1. 第3页，Spring 框架地图

- 错误：`BeanPostProcessor 前置处理 | postProcessAfterInitializtion` 
- 修改：`BeanPostProcessor 后置处理 | postProcessAfterInitializtion` 

### 2. 第17页，图 2-2 类图错误

- 错误：图 2-2 DefaultSingletonBeanRegistry #addSingleton 类图与代码不符
- 修改：图 2-2 DefaultSingletonBeanRegistry #registerSingleton
