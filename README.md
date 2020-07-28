# Singleton-demo
6种单例模式的写法

  /**
     * 单例模式（Singleton Pattern）属于创建型模式，它提供了一种创建对象的最佳方式。
     *
     * 这种模式涉及到一个单一的类，该类负责创建自己的对象。这个类提供了一种访问其唯一的对象方式，可以直接访问，不需要实例化该类的对象
     * 特点：保证一个类仅有一个实例，并提供一个访问它的全局访问点
     *
     * 作用：一个全局使用的类频繁地创建与销毁
     * 实现：判断系统是否已经有这个单例，如果有则返回，如果没有则创建
     *****************************************************
     *演示demo1:
     *    SluggardUnsafeSingleton
     * 1，非线程安全的懒汉式
     *    a.私有化一个类变量
     *    b.私有化构造方法
     *    c.判断是否为空，为空则 new ，否则就直接返回
     ****************************************************
     *演示demo2:
     *   SluggardsafeSingleton
     * 2.线程安全懒汉式
     *   a.私有化一个类变量
     *   b.私有化构造方法
     *   c.通过synchronized对方法进行加锁，判断是否为空，为空就new ，否则就直接返回
     *****************************************************
     * 演示demo3
     *      HungrySingleton
     * 3.饿汉式
     *   a.私有化一个类变量，并直接初始化
     *   b.私有化构造方法
     *   c.直接返回初始化的类变量
     *****************************************************
     * 演示demo4
     * 4.双重校验锁🔒(DCL)
     *    DoubleCheckLocksSingleton
     *   a.使用volatile修饰类变量
     *   b.私有化构造方法
     *   c.先判断类变量是否为空，不为空直接返回，如果为空，则用synchronized进行枷锁，然后实例化
     *
     * 演示demo5
     * 5.静态内部类
     *    InnerClassSingleton
     *   a.在类里面创建一个静态内部类
     *   b.私有化一个构造方法
     *   c.静态内部类初始化一个外部类的变量，并用static final修饰
     *   d.外部类的方法可以直接返回静态内部的该变量，使用静态内部类的延迟加载
     *
     * 6.枚举
     *    直接创建枚举，通过枚举类实现
     *    EnumSingleton
     */