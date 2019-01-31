
### BeanFactory与FactoryBean的区别

  

##### BeanFactory为spring IOC容器的接口

XmlBeanFactory是BeanFactory接口的实现类，主要负责bean的管理。

  

```

BeanFactory，以Factory结尾，表示它是一个工厂类(接口)，用于管理Bean的一个工厂。在Spring中，BeanFactory是IOC容器的核心接口，它的职责包括：实例化、定位、配置应用程序中的对象及建立这些对象间的依赖。

  

　　Spring为我们提供了许多易用的BeanFactory实现，XmlBeanFactory就是常用的一个，该实现将以XML方式描述组成应用的对象及对象间的依赖关系。XmlBeanFactory类将持有此XML配置元数据，并用它来构建一个完全可配置的系统或应用。

```

  
  
  

![s](../diagram/BeanFactory&FactoryBean.png)

  

##### FactoryBean一种特殊的bean

spring提供了FactoryBean<T>，用于特殊需求的bean管理

```

以Bean结尾，表示它是一个Bean，不同于普通Bean的是：它是实现了FactoryBean<T>接口的Bean，根据该Bean的ID从BeanFactory中获取的实际上是FactoryBean的getObject()返回的对象，而不是FactoryBean本身，如果要获取FactoryBean对象，请在id前面加一个&符号来获取。

  

　　例如自己实现一个FactoryBean，功能：用来代理一个对象，对该对象的所有方法做一个拦截，在调用前后都输出一行LOG，模仿ProxyFactoryBean的功能。

```

  

普通bean通过id获取到的是该bean本身，而FactoryBean是通过自己实现的getObject() 方法返回一个对象，交给ioc容器。

  

[博客](https://chenzehe.iteye.com/blog/1481476)

  

##### 区别

  

[区别](https://www.cnblogs.com/redcool/p/6413461.html)

  

##### 总结

BeanFactory是ioc容器需要实现的接口，

FactoryBean是自定义的特殊bean需要实现的接口。
