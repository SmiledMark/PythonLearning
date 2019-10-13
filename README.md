# PythonLearning
* [IOC 和 DI 的概述](#ioc-%E5%92%8C-di-%E7%9A%84%E6%A6%82%E8%BF%B0)
  * [IOC(Inversion of Controll)](#iocinversion-of-controll)
  * [DI(Dependency Injection)](#didependency-injection)
* [Spring配置](#spring%E9%85%8D%E7%BD%AE)
  * [ApplicationContext](#applicationcontext)
  * [Bean的相关配置](#bean%E7%9A%84%E7%9B%B8%E5%85%B3%E9%85%8D%E7%BD%AE)
    * [bean标签的id和name的配置](#bean%E6%A0%87%E7%AD%BE%E7%9A%84id%E5%92%8Cname%E7%9A%84%E9%85%8D%E7%BD%AE)
    * [bean的生命周期的配置](#bean%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E7%9A%84%E9%85%8D%E7%BD%AE)
    * [bean的作用范围的配置](#bean%E7%9A%84%E4%BD%9C%E7%94%A8%E8%8C%83%E5%9B%B4%E7%9A%84%E9%85%8D%E7%BD%AE)
  * [Spring的Bean管理配置](#spring%E7%9A%84bean%E7%AE%A1%E7%90%86%E9%85%8D%E7%BD%AE)
    * [Spring的Bean的实例化方式](#spring%E7%9A%84bean%E7%9A%84%E5%AE%9E%E4%BE%8B%E5%8C%96%E6%96%B9%E5%BC%8F)
      * [无参构造方式（默认）](#%E6%97%A0%E5%8F%82%E6%9E%84%E9%80%A0%E6%96%B9%E5%BC%8F%E9%BB%98%E8%AE%A4)
      * [静态工厂实例化方式](#%E9%9D%99%E6%80%81%E5%B7%A5%E5%8E%82%E5%AE%9E%E4%BE%8B%E5%8C%96%E6%96%B9%E5%BC%8F)
      * [实例工厂实例化方式](#%E5%AE%9E%E4%BE%8B%E5%B7%A5%E5%8E%82%E5%AE%9E%E4%BE%8B%E5%8C%96%E6%96%B9%E5%BC%8F)
    * [Spring的属性注入方式](#spring%E7%9A%84%E5%B1%9E%E6%80%A7%E6%B3%A8%E5%85%A5%E6%96%B9%E5%BC%8F)
      * [构造方法方式的属性注入](#%E6%9E%84%E9%80%A0%E6%96%B9%E6%B3%95%E6%96%B9%E5%BC%8F%E7%9A%84%E5%B1%9E%E6%80%A7%E6%B3%A8%E5%85%A5)
      * [Set方法方式的属性注入](#set%E6%96%B9%E6%B3%95%E6%96%B9%E5%BC%8F%E7%9A%84%E5%B1%9E%E6%80%A7%E6%B3%A8%E5%85%A5)
      * [为Bean注入引用类型的数据](#%E4%B8%BAbean%E6%B3%A8%E5%85%A5%E5%BC%95%E7%94%A8%E7%B1%BB%E5%9E%8B%E7%9A%84%E6%95%B0%E6%8D%AE)
      * [P名称空间的属性注入（Spring2\.5）](#p%E5%90%8D%E7%A7%B0%E7%A9%BA%E9%97%B4%E7%9A%84%E5%B1%9E%E6%80%A7%E6%B3%A8%E5%85%A5spring25)
      * [SpEL方式的属性注入（Spring3）](#spel%E6%96%B9%E5%BC%8F%E7%9A%84%E5%B1%9E%E6%80%A7%E6%B3%A8%E5%85%A5spring3)
    * [注入集合类型的数据](#%E6%B3%A8%E5%85%A5%E9%9B%86%E5%90%88%E7%B1%BB%E5%9E%8B%E7%9A%84%E6%95%B0%E6%8D%AE)
    * [Spring分模块开发的配置](#spring%E5%88%86%E6%A8%A1%E5%9D%97%E5%BC%80%E5%8F%91%E7%9A%84%E9%85%8D%E7%BD%AE)
* [Spring开发中的常用注解](#spring%E5%BC%80%E5%8F%91%E4%B8%AD%E7%9A%84%E5%B8%B8%E7%94%A8%E6%B3%A8%E8%A7%A3)
  * [@Component](#component)
  * [@Value](#value)
  * [@Autowired](#autowired)
  * [@Resource](#resource)
  * [@PostConstruct 和 @PreDestroy](#postconstruct-%E5%92%8C-predestroy)
  * [@Scope](#scope)
  * [基于XML配置和基于注解配置的对比](#%E5%9F%BA%E4%BA%8Exml%E9%85%8D%E7%BD%AE%E5%92%8C%E5%9F%BA%E4%BA%8E%E6%B3%A8%E8%A7%A3%E9%85%8D%E7%BD%AE%E7%9A%84%E5%AF%B9%E6%AF%94)
* [Spring AOP](#spring-aop)
  * [AOP的概述](#aop%E7%9A%84%E6%A6%82%E8%BF%B0)
  * [AOP的案例（应用场景）](#aop%E7%9A%84%E6%A1%88%E4%BE%8B%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)
  * [AOP底层实现原理](#aop%E5%BA%95%E5%B1%82%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86)
    * [JDK动态代理](#jdk%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86)
      * [JDK动态代理案例](#jdk%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86%E6%A1%88%E4%BE%8B)
    * [Cglib动态代理](#cglib%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86)
      * [Cglib动态代理案例](#cglib%E5%8A%A8%E6%80%81%E4%BB%A3%E7%90%86%E6%A1%88%E4%BE%8B)
  * [Spring中的AOP实现——AspectJ](#spring%E4%B8%AD%E7%9A%84aop%E5%AE%9E%E7%8E%B0aspectj)
    * [AOP开发中的相关术语](#aop%E5%BC%80%E5%8F%91%E4%B8%AD%E7%9A%84%E7%9B%B8%E5%85%B3%E6%9C%AF%E8%AF%AD)
    * [AspectJ的XML配置案例](#aspectj%E7%9A%84xml%E9%85%8D%E7%BD%AE%E6%A1%88%E4%BE%8B)
    * [Spring中常用的增强类型](#spring%E4%B8%AD%E5%B8%B8%E7%94%A8%E7%9A%84%E5%A2%9E%E5%BC%BA%E7%B1%BB%E5%9E%8B)
      * [前置增强](#%E5%89%8D%E7%BD%AE%E5%A2%9E%E5%BC%BA)
      * [后置增强](#%E5%90%8E%E7%BD%AE%E5%A2%9E%E5%BC%BA)
      * [环绕增强](#%E7%8E%AF%E7%BB%95%E5%A2%9E%E5%BC%BA)
      * [异常抛出增强](#%E5%BC%82%E5%B8%B8%E6%8A%9B%E5%87%BA%E5%A2%9E%E5%BC%BA)
      * [最终增强](#%E6%9C%80%E7%BB%88%E5%A2%9E%E5%BC%BA)
    * [AOP切入点表达式语法](#aop%E5%88%87%E5%85%A5%E7%82%B9%E8%A1%A8%E8%BE%BE%E5%BC%8F%E8%AF%AD%E6%B3%95)
    * [AspectJ的注解配置案例](#aspectj%E7%9A%84%E6%B3%A8%E8%A7%A3%E9%85%8D%E7%BD%AE%E6%A1%88%E4%BE%8B)
* [Spring JDBC Template](#spring-jdbc-template)
  * [JDBC Template的入门](#jdbc-template%E7%9A%84%E5%85%A5%E9%97%A8)
    * [基本使用](#%E5%9F%BA%E6%9C%AC%E4%BD%BF%E7%94%A8)
    * [数据库连接池](#%E6%95%B0%E6%8D%AE%E5%BA%93%E8%BF%9E%E6%8E%A5%E6%B1%A0)
      * [DBCP连接池的配置](#dbcp%E8%BF%9E%E6%8E%A5%E6%B1%A0%E7%9A%84%E9%85%8D%E7%BD%AE)
      * [C3P0连接池配置](#c3p0%E8%BF%9E%E6%8E%A5%E6%B1%A0%E9%85%8D%E7%BD%AE)
    * [完成基本的CRUD操作](#%E5%AE%8C%E6%88%90%E5%9F%BA%E6%9C%AC%E7%9A%84crud%E6%93%8D%E4%BD%9C)
      * [插入操作](#%E6%8F%92%E5%85%A5%E6%93%8D%E4%BD%9C)
      * [修改操作](#%E4%BF%AE%E6%94%B9%E6%93%8D%E4%BD%9C)
      * [删除操作](#%E5%88%A0%E9%99%A4%E6%93%8D%E4%BD%9C)
      * [查询操作](#%E6%9F%A5%E8%AF%A2%E6%93%8D%E4%BD%9C)
        * [查询某个属性](#%E6%9F%A5%E8%AF%A2%E6%9F%90%E4%B8%AA%E5%B1%9E%E6%80%A7)
        * [查询返回单个对象](#%E6%9F%A5%E8%AF%A2%E8%BF%94%E5%9B%9E%E5%8D%95%E4%B8%AA%E5%AF%B9%E8%B1%A1)
        * [查询返回对象集合](#%E6%9F%A5%E8%AF%A2%E8%BF%94%E5%9B%9E%E5%AF%B9%E8%B1%A1%E9%9B%86%E5%90%88)
* [Spring事务管理](#spring%E4%BA%8B%E5%8A%A1%E7%AE%A1%E7%90%86)
  * [什么是事务](#%E4%BB%80%E4%B9%88%E6%98%AF%E4%BA%8B%E5%8A%A1)
  * [事务的特性](#%E4%BA%8B%E5%8A%A1%E7%9A%84%E7%89%B9%E6%80%A7)
  * [不考虑隔离性引发的安全性问题](#%E4%B8%8D%E8%80%83%E8%99%91%E9%9A%94%E7%A6%BB%E6%80%A7%E5%BC%95%E5%8F%91%E7%9A%84%E5%AE%89%E5%85%A8%E6%80%A7%E9%97%AE%E9%A2%98)
  * [解决读问题](#%E8%A7%A3%E5%86%B3%E8%AF%BB%E9%97%AE%E9%A2%98)
  * [Spring事务管理API](#spring%E4%BA%8B%E5%8A%A1%E7%AE%A1%E7%90%86api)
  * [Spring事务的传播行为](#spring%E4%BA%8B%E5%8A%A1%E7%9A%84%E4%BC%A0%E6%92%AD%E8%A1%8C%E4%B8%BA)
  * [Spring事务管理案例——转账情景](#spring%E4%BA%8B%E5%8A%A1%E7%AE%A1%E7%90%86%E6%A1%88%E4%BE%8B%E8%BD%AC%E8%B4%A6%E6%83%85%E6%99%AF)
    * [转账情景实现](#%E8%BD%AC%E8%B4%A6%E6%83%85%E6%99%AF%E5%AE%9E%E7%8E%B0)
    * [编程式事务](#%E7%BC%96%E7%A8%8B%E5%BC%8F%E4%BA%8B%E5%8A%A1)
    * [声明式事务](#%E5%A3%B0%E6%98%8E%E5%BC%8F%E4%BA%8B%E5%8A%A1)
      * [XML配置方式](#xml%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F)
      * [注解配置方式](#%E6%B3%A8%E8%A7%A3%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F)

# IOC 和 DI 的概述

## IOC(Inversion of Controll)

**思想是反转资源获取的方向**，传统的资源查找方式要求组件向容器发起请求查找资源。作为回应，容器适时的返回资源。而应用了IOC之后，则是**容器主动的将资源推送给它所管理的组件，组件所要做的仅是选择一种合适的方式来接收资源**

## DI(Dependency Injection)

是IOC的另一种表述方式，即**组件以一些预先定义好的方式(如：getter方法)来接收来自容器的资源注入**

<!-- more -->

# Spring配置

在SpringIOC容器读取bean配置创建bean实例之前，必须对它进行实例化。只有在容器实例化后，才可以从IOC容器里获取bean实例并使用

Spring提供了两种类型的IOC容器实现

+ **BeanFactory：IOC容器的基本实现，在调用getBean()方法时才会实例化对象**
+ **ApplicationContext：提供了更多的高级特性，在加载配置文件后就会实例化对象。是BeanFactory的子接口**

`BeanFactory`是Spring框架的基础设施，面向Spring本身

`ApplicationContext`面向使用Spring框架的开发者，几乎所有的应用场合都直接使用`ApplicationContext`而非底层的`BeanFactory`

**无论使用何种方式，配置文件时都是相同的**
