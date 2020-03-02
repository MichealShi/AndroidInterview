一、java

熟练掌握java是很关键的，大公司不仅仅要求你会使用几个api，更多的是要你熟悉源码实现原理，甚至要你知道有哪些不足，怎么改进，还有一些java有关的一些算法，设计模式等等。

（一）java基础面试知识点

1)  java中==和equals和hashCode的区别

== 在用关系操作符 == 比较的是值本身；equals 比较两个对象的引用是否相等,即 是否指向同一个对象；hashCode 用来鉴定两个对象是否相等，Object类中的hashCode方法返回对象在内存中地址转换成的一个int值，所以如果没有重写hashCode方法，任何对象的hashCode方法是不相等的。

2) int、char、long各占多少字节数

4、1或2或4、8

3) int与integer的区别

int 是我们常说的整形数字，是 Java 的 8 个原始数据类型之一。Integer 是 int 对应的包装类，它有一个 int 类型的字段存储数据，并且提供了基本操作，比如数学运算、int 和字符串之间转换等。

4) 谈谈对java多态的理解

所谓多态就是指程序中定义的引用变量所指向的具体类型和通过该引用变量发出的方法调用在编程时并不确定，而是在程序运行期间才确定，即一个引用变量到底会指向哪个类的实例对象，该引用变量发出的方法调用到底是哪个类中实现的方法，必须在由程序运行期间才能决定。因为在程序运行时才确定具体的类，这样，不用修改源程序代码，就可以让引用变量绑定到各种不同的类实现上，从而导致该引用变量调用的具体方法随之改变，即不修改程序代码就可以改变程序运行时所绑定的具体代码，让程序可以选择多个运行状态，这就是多态性。实现形式 在Java中有两种形式可以实现多态。继承和接口。

5) String、StringBuffer、StringBuilder区别

String 是 Java 语言非常基础和重要的类，提供了构造和管理字符串的各种基本逻辑。它是典型的 Immutable 类，被声明成为 final class，所有属性也都是 final 的。也由于它的不可变性，类似拼接、裁剪字符串等动作，都会产生新的 String 对象。由于字符串操作的普遍性，所以相关操作的效率往往对应用性能有明显影响。StringBuffer 是为解决上面提到拼接产生太多中间对象的问题而提供的一个类，我们可以用 append 或者 add 方法，把字符串添加到已有序列的末尾或者指定位置。StringBuffer 本质是一个线程安全的可修改字符序列，它保证了线程安全，也随之带来了额外的性能开销，所以除非有线程安全的需要，不然还是推荐使用它的后继者，也就是 StringBuilder。StringBuilder 是 Java 1.5 中新增的，在能力上和 StringBuffer 没有本质区别，但是它去掉了线程安全的部分，有效减小了开销，是绝大部分情况下进行字符串拼接的首选。

6) 什是内部类？内部类的作用

- 定义在类中的类
- 内部类方法可以访问该类定义所在作用域中的数据，包括被 private 修饰的私有数据
- 内部类可以对同一包中的其他类隐藏起来
- 内部类可以解决 java 单继承的缺陷
- 当我们想要定义一个回调函数却不想写大量代码的时候我们可以选择使用匿名内部类来实现
- 但是容易内存泄露，因为持有外部对象。
- 7) 抽象类和接口区别

接口是对行为的抽象，他是抽象方法的集合，利用接口可以达到API定义和实现分离的目的。接口，不能实例化；不能包含任何非常量成员，任何field都是隐含着public static final的意义；同时没有非静态方法实现，也就是说要么是抽象方法，要么是静态方法。

抽象类是不能实例化的类，有abstract关键字修饰class，其目的主要是代码重用。除了不能实例化，形式上和一般的Java类并没有太大区别，可以有一个和多个抽象方法，也可以没有抽象方法。抽象类大多用于抽取相关Java类的共用方法实现或者是共同成员变量，然后通过继承的方式达到代码重用的目的。

8) 泛型中extends和super的区别

泛型中extends的主要作用是设定类型通配符的上限，<? extends Fruit>代表的是上界通配符，也就是说这个List中存放的对象都是Fruit以及其子类的对象，这样我们就不用因为输入的List中类型的不同而改变代码了。

super与extends是完全相反的，其定义的是下界通配符。List<? super Fruit>也就是说List中存放的都是Fruit和它的父类的对象

9) 父类的静态方法能否被子类重写

不能，父类的静态方法能够被子类继承，但是不能够被子类重写，即使子类中的静态方法与父类中的静态方法完全一样，也是两个完全不同的方法。

10) 进程和线程的区别

- 进程是资源分配的最小单位，线程是资源调度的最小单位。
- 进程有自己的独立地址空间，每启动一个进程，系统就会为它分配地址空间，建立数据表来维护代码段、堆栈段和数据段，这种操作非常昂贵。
- 而线程是共享进程中的数据的，使用相同的地址空间，因此CPU切换一个线程的花费远比进程要小很多，同时创建一个线程的开销也比进程要小很多。
- 线程之间的通信更方便，同一进程下的线程共享全局变量、静态变量等数据，而进程之间的通信需要以通信的方式（IPC)进行。

11) final，finally，finalize的区别

final 可以用来修饰类、方法、变量，分别有不同的意义，final 修饰的 class 代表不可以继承扩展，final 的变量是不可以修改的，而 final 的方法也是不可以重写的（override）。finally 则是 Java 保证重点代码一定要被执行的一种机制。我们可以使用 try-finally 或者 try-catch-finally 来进行类似关闭 JDBC 连接、保证 unlock 锁等动作。finalize 是基础类 java.lang.Object 的一个方法，它的设计目的是保证对象在被垃圾收集前完成特定资源的回收。

12) 序列化的方式

- 实现Serializable接口(隐式序列化)
- 实现Externalizable接口(显示序列化)
- 实现Serializable接口+添加writeObject和readObject方法(显+隐序列化)

13) Serializable 和Parcelable 的区别

Serializable的作用是为了保存对象的属性到本地文件、数据库、网络流等以方便数据传输，Android的Parcelable的设计初衷是因为Serializable效率过慢。

内存间数据传输时推荐使用Parcelable，如activity间传输数据，而Serializable可将数据持久化方便保存，因为android不同版本Parcelable可能不同，所以不推荐使用Parcelable进行数据持久化。

14) 静态属性和静态方法是否可以被继承？是否可以被重写？以及原因？

父类的静态属性和方法可以被子类继承

不可以被子类重写

因为静态方法从程序开始运行后就已经分配了内存，也就是说已经写死了。所有引用到该方法的对象（父类的对象也好子类的对象也好）所指向的都是同一块内存中的数据，也就是该静态方法。子类中如果定义了相同名称的静态方法，并不会重写，而应该是在内存中又分配了一块给子类的静态方法，没有重写这一说。

15) 静态内部类的设计意图

非静态内部类在编译完成之后会隐含地保存着一个引用，该引用是指向创建它的外围类，但是静态内部类却没有。没有这个引用就意味着：它的创建是不需要依赖于外围类的。它不能使用任何外围类的非static成员变量和方法。

16) 成员内部类、静态内部类、局部内部类和匿名内部类的理解，以及项目中的应用

https://www.cnblogs.com/ldl326308/p/9477566.html

https://blog.csdn.net/nobody_1/article/details/90886330

17) string 转换成 integer的方式及原理

默认转成十进制

（二）java深入源码级的面试题（有难度）

1) 哪些情况下的对象会被垃圾回收机制处理掉？

2) 讲一下常见编码方式？

- ASCII编码：用来表示英文，它使用1个字节表示，其中第一位规定为0，其他7位存储数据，一共可以表示128个字符。
- 拓展ASCII编码：用于表示更多的欧洲文字，用8个位存储数据，一共可以表示256个字符
- GBK/GB2312/GB18030：表示汉字。GBK/GB2312表示简体中文，GB18030表示繁体中文。
- Unicode编码：包含世界上所有的字符，是一个字符集。
- UTF-8：是Unicode字符的实现方式之一，它使用1-4个字符表示一个符号，根据不同的符号而变化字节长度。

3) utf-8编码中的中文占几个字节；int型几个字节？

数字占1个字节，英文字母占1个字节，少数是汉字每个占用3个字节，多数占用4个字节。

4) 静态代理和动态代理的区别，什么场景使用？

动态代理是一种方便运行时动态构建代理、动态处理代理方法调用的机制，很多场景都是利用类似机制做到的，比如用来包装 RPC 调用、面向切面的编程（AOP）。实现动态代理的方式很多，比如 JDK 自身提供的动态代理，就是主要利用了上面提到的反射机制。还有其他的实现方式，比如利用传说中更高性能的字节码操作机制，类似 ASM、cglib（基于 ASM）、Javassist 等。通过代理可以让调用者与实现者之间解耦。

5) Java的异常体系

Exception 和 Error 都是继承了 Throwable 类，在 Java 中只有 Throwable 类型的实例才可以被抛出（throw）或者捕获（catch），它是异常处理机制的基本组成类型。Exception 和 Error 体现了 Java 平台设计者对不同异常情况的分类。Exception 是程序正常运行中，可以预料的意外情况，可能并且应该被捕获，进行相应处理。Error 是指在正常情况下，不大可能出现的情况，绝大部分的 Error 都会导致程序（比如 JVM 自身）处于非正常的、不可恢复状态。既然是非正常情况，所以不便于也不需要捕获，常见的比如 OutOfMemoryError 之类，都是 Error 的子类。Exception 又分为可检查（checked）异常和不检查（unchecked）异常，可检查异常在源代码里必须显式地进行捕获处理，这是编译期检查的一部分。前面我介绍的不可查的 Error，是 Throwable 不是 Exception。不检查异常就是所谓的运行时异常，类似 NullPointerException、ArrayIndexOutOfBoundsException 之类，通常是可以编码避免的逻辑错误，具体根据需要来判断是否需要捕获，并不会在编译期强制要求。

6) 谈谈你对解析与分派的认识。

7) 修改对象A的equals方法的签名，那么使用HashMap存放这个对象实例的时候，会调用哪个equals方法？

8) Java中实现多态的机制是什么？

9) 如何将一个Java对象序列化到文件里？

10) 说说你对Java反射的理解

反射机制是 Java 语言提供的一种基础功能，赋予程序在运行时自省（introspect，官方用语）的能力。通过反射我们可以直接操作类或者对象，比如获取某个对象的类定义，获取类声明的属性和方法，调用方法或者构造对象，甚至可以运行时修改类定义。

11) 说说你对Java注解的理解

注解，也叫元数据。一种代码级别的说明，在JDK1.5之后引入的特性，与类、接口、枚举同一层次。可以声明在包、类、字段、方法、局部变量、方法参数等前面，来对这些元素进行说明，注释等。

作用分类：

- 1）编写文档：通过代码里的标识的元数据生成文档【生成文档doc文档】
- 2）代码分析：通过代码里的标识的元数据对代码进行分析【使用反射】
- 3）编译检查：通过代码里的标识的元数据让编译器能过实现基本的编译检查【Override】

12) 说说你对依赖注入的理解

依赖注入设计原则允许我们移除硬编码依赖和让我们的应用低耦合，可扩展和可维护。我们可以通过在Java中实现依赖注入将依赖关系从编译时移到运行时来解析。

13) 说一下泛型原理，并举例说明

类型安全， 泛型的主要目标是实现java的类型安全。 泛型可以使编译器知道一个对象的限定类型是什么，这样编译器就可以在一个高的程度上验证这个类型

消除了强制类型转换， 使得代码可读性好，减少了很多出错的机会

Java语言引入泛型的好处是安全简单。泛型的好处是在编译的时候检查类型安全，并且所有的强制转换都是自动和隐式的，提高代码的重用率。

泛型的实现是靠类型擦除技术， 类型擦除是在编译期完成的， 也就是在编译期， 编译器会将泛型的类型参数都擦除成它的限定类型，如果没有则擦除为object类型之后在获取的时候再强制类型转换为对应的类型。 在运行期间并没有泛型的任何信息，因此也没有优化。

14) String为什么要设计成不可变的？

字符串常量池(String pool, String intern pool, String保留池) 是Java堆内存中一个特殊的存储区域, 当创建一个String对象时,假如此字符串值已经存在于常量池中,则不会创建一个新的对象,而是引用已经存在的对象。假若字符串对象允许改变,那么将会导致各种逻辑错误,比如改变一个对象会影响到另一个独立对象. 严格来说，这种常量池的思想,是一种优化手段.

15) Object类的equal和hashCode方法重写，为什么？

16)Java8新特性

- Java 8允许我们给接口添加一个非抽象的方法实现，只需要使用 default关键字即可
- Labmbda表达式
- 在Java 8中支持多重注解了

（三） 数据结构

1) 常用数据结构简介

2) 并发集合了解哪些？

3) 列举java的集合以及集合之间的继承关系

4) 集合类以及集合框架

5) 容器类介绍以及之间的区别（容器类估计很多人没听这个词，Java容器主要可以划分为4个部分：List列表、Set集合、Map映射、工具类（Iterator迭代器、Enumeration枚举类、Arrays和Collections），具体的可以看看这篇博文 Java容器类）

6) List,Set,Map的区别

7) List和Map的实现方式以及存储方式

8) HashMap的实现原理

9) HashMap数据结构？

10) HashMap源码理解

11) HashMap如何put数据（从HashMap源码角度讲解）？

12) HashMap怎么手写实现？

13) ConcurrentHashMap的实现原理

14) ArrayMap和HashMap的对比

15) HashTable实现原理

16) TreeMap、HashMap和HashTable的区别

Hashtable、HashMap、TreeMap 都是最常见的一些 Map 实现，是以键值对的形式存储和操作数据的容器类型。Hashtable 是早期 Java 类库提供的一个哈希表实现，本身是同步的，不支持 null 键和值，由于同步导致的性能开销，所以已经很少被推荐使用。HashMap 是应用更加广泛的哈希表实现，行为上大致上与 HashTable 一致，主要区别在于 HashMap 不是同步的，支持 null 键和值等。通常情况下，HashMap 进行 put 或者 get 操作，可以达到常数时间的性能，所以它是绝大部分利用键值对存取场景的首选，比如，实现一个用户 ID 和用户信息对应的运行时存储结构。TreeMap 则是基于红黑树的一种提供顺序访问的 Map，和 HashMap 不同，它的 get、put、remove 之类操作都是 O（log(n)）的时间复杂度，具体顺序可以由指定的 Comparator 来决定，或者根据键的自然顺序来判断

17) HashMap与HashSet的区别

18) HashSet与HashMap怎么判断集合元素重复？

19) 集合Set实现Hash怎么防止碰撞

20) Vector、ArrayList和LinkedList的区别，以及应用场景

这三者都是实现集合框架中的 List，也就是所谓的有序集合，因此具体功能也比较近似，比如都提供按照位置进行定位、添加或者删除的操作，都提供迭代器以遍历其内容等。但因为具体的设计区别，在行为、性能、线程安全等方面，表现又有很大不同。Vector 是 Java 早期提供的线程安全的动态数组，如果不需要线程安全，并不建议选择，毕竟同步是有额外开销的。Vector 内部是使用对象数组来保存数据，可以根据需要自动的增加容量，当数组已满时，会创建新的数组，并拷贝原有数组数据。ArrayList 是应用更加广泛的动态数组实现，它本身不是线程安全的，所以性能要好很多。与 Vector 近似，ArrayList 也是可以根据需要调整容量，不过两者的调整逻辑有所区别，Vector 在扩容时会提高 1 倍，而 ArrayList 则是增加 50%。LinkedList 顾名思义是 Java 提供的双向链表，所以它不需要像上面两种那样调整容量，它也不是线程安全的。

21) 数组和链表的区别

数组是一种线性表数据结构。它用一组连续的内存空间,来存储一组具有相同类型的数据。最大的特点就是支持随机访问,但插入、删除操作也因此变得比较低效,平均情况时间复杂度为O(n)。

链表它并不需要一块连续的内存空间,它通过“指针”将一组零散的内存,空间可扩容,比较常用的是单链表,双链表和循环链表。和数组相比,链表更适合插入、删除操作频繁的场景,查询的时间复杂度较高。

22) 二叉树的深度优先遍历和广度优先遍历的具体实现

23) 堆的结构

24) 堆和树的区别

25) 堆和栈在内存中的区别是什么(解答提示：可以从数据结构方面以及实际实现方面两个方面去回答)？

26) 什么是深拷贝和浅拷贝

27) 手写链表逆序代码

28) 讲一下对树，B+树的理解

29) 讲一下对图的理解

30) 判断单链表成环与否？

31) 链表翻转（即：翻转一个单项链表）

32) 合并多个单有序链表（假设都是递增的）

（四） 线程、多线程和线程池

1) 开启线程的三种方式？

继承Thread类、实现Runnable接口、实现Callable接口

2) run()和start()方法区别

start()方法来启动线程,真正实现了多线程运行,这时无需等待。run()方法当作普通方法的方式调用,程序还是要顺序执行,还是要等待run方法体执行完毕。

3) 在Java中wait和seelp方法的不同；

sleep()方法是属于Thread类中的。而wait()方法，则是属于Object类中的。

sleep()方法导致了程序暂停执行指定的时间，让出cpu给其他线程，线程不会释放对象锁。而当调用wait()方法的时候，但是他的监控状态依然保持者，当指定的时间到了又会自动恢复运行状态。线程会放弃对象锁，进入等待此对象的等待锁定池，只有针对此对象调用notify()方法后本线程才进入对象锁定池准备获取对象锁进入运行状态。

4) 谈谈wait/notify关键字的理解

基类 Object 提供了一些基础的 wait/notify/notifyAll 方法。如果我们持有某个对象的 Monitor 锁，调用 wait 会让当前线程处于等待状态，直到其他线程 notify 或者 notifyAll。

5) 什么导致线程阻塞？

- 线程执行了Thread.sleep
- 线程执行一段同步代码，但是尚且无法获得相关的同步锁，只能进入阻塞状态，等到获取了同步锁，才能回复执行。
- 线程执行了一个对象的wait()方法，直接进入阻塞状态，等待其他线程执行notify()或者notifyAll()方法。
- 线程执行某些IO操作，因为等待相关的资源而进入了阻塞状态。

6) 线程如何关闭？

- 使用退出标志，使线程正常退出，也就是当run方法完成后线程终止
- 使用stop方法强行终止线程（这个方法不推荐使用，因为stop和suspend、resume一样，可能发生不可预料的结果
- 使用interrupt方法中断线程。

7) 讲一下java中的同步的方法

8) 数据一致性如何保证？

9) 如何保证线程安全？

10) 如何实现线程同步？

11) 两个进程同时要求写或者读，能不能实现？如何防止进程的同步？

12) 线程间操作List

13) Java中对象的生命周期

14) Synchronized用法

15) synchronize的原理

synchronized 代码块是由一对儿 monitorenter/monitorexit 指令实现的，Monitor 对象是同步的基本实现单元。

三种不同的锁：偏斜锁（Biased Locking）、轻量级锁和重量级锁。

所谓锁的升级、降级，就是 JVM 优化 synchronized 运行的机制，当 JVM 检测到不同的竞争状况时，会自动切换到适合的锁实现，这种切换就是锁的升级、降级。当没有竞争出现时，默认会使用偏斜锁。

16) 谈谈对Synchronized关键字，类锁，方法锁，重入锁的理解

17) static synchronized 方法的多线程访问和作用

18) 同一个类里面两个synchronized方法，两个线程同时访问的问题

多个线程访问同一个类的synchronized方法时, 都是串行执行的 ! 就算有多个cpu也不例外 ! synchronized方法使用了类java的内置锁, 即锁住的是方法所属对象本身. 同一个锁某个时刻只能被一个执行线程所获取, 因此其他线程都得等待锁的释放. 因此就算你有多余的cpu可以执行, 但是你没有锁, 所以你还是不能进入synchronized方法执行

19) volatile的原理

轻量级的synchronized，只能用来修饰变量

保证了可见性和有序性（不保证原子性），如果一个共享变量被volatile关键字修饰，那么如果一个线程修改了这个共享变量后，其他线程是立马可知的。

当对volatile变量进行写操作的时候，JVM会向处理器发送一条lock前缀的指令，将这个缓存中的变量回写到系统主存中。用到了缓存一致性协议。

20) 谈谈volatile关键字的用法

21) 谈谈volatile关键字的作用

22) synchronized 和volatile 关键字的区别

synchronized提供了同步锁的概念，被synchronized修饰的代码段可以防止被多个线程同时执行，必须一个线程把synchronized修饰的代码段都执行完毕了，其他的线程才能开始执行这段代码。因为synchronized保证了在同一时刻，只能有一个线程执行同步代码块，所以执行同步代码块的时候相当于是单线程操作了，那么线程的可见性、原子性、有序性（线程之间的执行顺序）它都能保证了。

区别：

- volatile只能作用于变量，使用范围较小。synchronized可以用在变量、方法、类、同步代码块等，使用范围比较广。
- volatile只能保证可见性和有序性，不能保证原子性。而可见性、有序性、原子性synchronized都可以包证。
- volatile不会造成线程阻塞。synchronized可能会造成线程阻塞。
- 23) synchronized与Lock的区别
- lock是一个接口，而synchronized是java的一个关键字
- synchronized在发生异常时候会自动释放占有的锁，因此不会出现死锁；而lock发生异常时候，不会主动释放占有的锁
- Lock可以通过trylock来知道有没有获取锁，而synchronized不能；
- synchronized原始采用的是CPU悲观锁机制，即线程获得的是独占锁。而Lock用的是乐观锁方式。所谓乐观锁就是，每次不加锁而是假设没有冲突而去完成某项操作，如果因为冲突失败就重试，直到成功为止。

24) ReentrantLock 、synchronized和volatile比较

25) ReentrantLock的内部实现

26) lock原理

27) 死锁的四个必要条件？

- 互斥条件：一个资源每次只能被一个进程使用，即在一段时间内某 资源仅为一个进程所占有。此时若有其他进程请求该资源，则请求进程只能等待。
- 请求与保持条件：进程已经保持了至少一个资源，但又提出了新的资源请求，而该资源 已被其他进程占有，此时请求进程被阻塞，但对自己已获得的资源保持不放。
- 不可剥夺条件:进程所获得的资源在未使用完毕之前，不能被其他进程强行夺走，即只能 由获得该资源的进程自己来释放（只能是主动释放)。
- 循环等待条件: 若干进程间形成首尾相接循环等待资源的关系

28) 怎么避免死锁？

29) 对象锁和类锁是否会互相影响？

类锁和对象锁不是同1个东西，一个是类的Class对象的锁，一个是类的实例的锁。也就是说：1个线程访问静态synchronized的时候，允许另一个线程访问对象的实例synchronized方法。反过来也是成立的，因为他们需要的锁是不同的。

30) 什么是线程池，如何使用?

一个线程池包括以下四个基本组成部分：

1、线程池管理器（ThreadPool）：用于创建并管理线程池，包括 创建线程池，销毁线程池，添加新任务；

2、工作线程（PoolWorker）：线程池中线程，在没有任务时处于等待状态，可以循环的执行任务；

3、任务接口（Task）：每个任务必须实现的接口，以供工作线程调度任务的执行，它主要规定了任务的入口，任务执行完后的收尾工作，任务的执行状态等；

4、任务队列（taskQueue）：用于存放没有处理的任务。提供一种缓冲机制。

常见线程池有：newSingleThreadExecutor(单线程串行)、newFixedThreadExecutor(固定数量)、newCacheThreadExecutor(可缓存、推荐)、newScheduleThreadExecutor(大小无限制)

31) Java的并发、多线程、线程模型

32) 谈谈对多线程的理解

线程是由一个主线程和很多个子线程组成的，主线程消失，子线程也会消失，但是子线程消失其中一个主线程不会消失

线程的生命周期分为5个步骤像人的一生一样，这5个步骤分别对应了5个方法

新生-->启动-->运行-->阻塞-->销毁

33) 多线程有什么要注意的问题？

线程之间共用进程所有资源，当多线程操作同一个变量的时候，可能会使得结果不正确。

因此要特别注意线程安全的问题。

通常保证线程安全有很多种方式

- 使用线程锁
- 使用串行队列
- 使用线程安全的类
- 使用信号量或runloop使异步看起来像同步在执行
- 注意任务可能本身就是异步的

34) 谈谈你对多线程同步机制的理解？

线程同步是为了确保线程安全，所谓线程安全指的是多个线程对同一资源进行访问时，有可能产生数据不一致问题，导致线程访问的资源并不是安全的。如果多线程程序运行结果和单线程运行的结果是一样的，且相关变量的值与预期值一样，则是线程安全的。

35) 如何保证多线程读写文件的安全？

36) 多线程断点续传原理

多线程下载文件时，文件是被分成多个部分，是被不同的线程同时下载的，此时就需要每一条线程都分别需要一个记录点，和每个线程完成状态的记录。只有将所有线程的下载状态都处于完成状态时，才能表示文件下载完成。

1、首先获取要下载文件的长度，用来设置RomdomAccessFile(本地文件)的长度

2、实时保存文件的下载进度(此功能可以用数据库来实现)

3、中断后再次下载，读取进度，再从上次的下载进度继续下载，并在本地的文件续续写如。

   获取文件长度：fileLength = HttpUrlConnection.getContentLength()

   每条线程需要下载的大小 = fileLength / Thread_Num

37) 断点续传的实现

二、Android

Android面试题包括Android基础，还有一些源码级别的、原理这些等。所以想去大公司面试，一定要多看看源码和实现方式，常用框架可以试试自己能不能手写实现一下，锻炼一下自己。

（一）Android基础知识点

1) 四大组件是什么

Activity/Service/BroadCast Recevicer/Content provider

2) 四大组件的生命周期和简单用法



3) Activity之间的通信方式

- 在Intent跳转时携带数据
- 借助类的静态变量
- 借助全局变量 Application
- 借助Service服务
- 借助外部存储来实现通讯
- 借助 SharedPreference
- 使用Android数据库 SQLite
- 使用 File本地文件

4) 横竖屏切换的时候，Activity 各种情况下的生命周期

Activity未配置configChanges属性，切到横屏后，再切回竖屏时，会走两遍onPause——onSaveInstanceState——onStop——onDestroy——onCreate——onStart——onRestoreInstanceState——onResume 生命周期方法

只要随意配置了configChanges属性，切到横屏和再切到竖屏，生命周期调用顺序都表现为onConfigurationChanged

5) Activity与Fragment之间生命周期比较

6) Activity上有Dialog的时候按Home键时的生命周期

 onPause() -> onStop() 

对话框的出现并没有使Activity进入后台。而是点击Home键才使Activity进入后台工作

7) 两个Activity 之间跳转时必然会执行的是哪几个方法？

当在A 里面激活B 组件的时候, A会调用onPause()方法,然后B调用onCreate() ,onStart(), onResume()。

这个时候B覆盖了A的窗体, A会调用onStop()方法。

如果B是个透明的窗口,或者是对话框的样式, 就不会调用A的onStop()方法。

如果B已经存在于Activity栈中，B就不会调用onCreate()方法。

8) Activity的四种启动模式对比

- 标准模式（standard）每次启动一个标准模式的Activity都会重新创建一个新的实例，不管这个Activity之前是否已经存在实例
- 栈顶复用模式（singleTop）新启动的Activity已经位于任务战的栈顶，那么此Activity不会被重新创建，只会重新调用 onNewIntent 方法，这个Activity的onCreate、onStart都不会被系统调用。如果新Activity实例已经存在但不在栈顶，那么重新创建 Activity 并放入栈顶
- 栈内复用模式（singleTask）一个栈中同一个Activity只存在唯一一个实例，无论是否在栈顶，只要存在实例，都不会重新创建，和 singleTop 一样会重新调用 onNewIntent 方法。需要注意的是：如果一个Activity被设置为singleTask模式，那么当栈内已经存在该Activity实例时，再启动该Activity，会让该Activity实例之上的Activity被出栈
- 单例模式（singleInstance）这是一种加强的singleTask模式，它除了具有singleTask模式的所有特性外，还加强了一点，那就是此种模式的Activity只能单独地位于一个任务栈中，不同的应用去打开这个activity 共享公用的同一个activity。他会运行在自己单独，独立的任务栈里面，并且任务栈里面只有他一个实例存在。应用场景：呼叫来电界面。

9) Activity状态保存与恢复

临时性数据

onSaveInstanceState调用的原则是系统有未经你的许可销毁Activity的可能。那么onSaveInstanceState有下面几种情况会调用：

按下HOME键、长按HOME键切换到了其他APP、横竖屏切换、Activity的导航、锁定屏幕

onRestoreInstanceState被调用的原则是Activity被销毁了，而不是可能被销毁了。

持久性数据

在onResume和onPause方法中做，可以把数据保存在数据库或者SharedPreference中。然而在生命周期函数中不适合做耗时的操作

10) 如何实现Fragment的滑动？ViewPager+Fragment

11) fragment之间传递数据的方式？

定义数据接口，在Activity中实现该接口，并实现接口中定义的方法，在Fragment A中声明接口对象,并调用接口中的方法，Activity中的接口回调中，向Fragment B传递数据

EventBus传值

12) Activity 怎么和Service 绑定？

Activity 通过 bindService(Intent service, ServiceConnection conn, int flags) 跟服务 进行绑定, 当绑定成功的时候服务会将代理对象通过 onBind() 方法传给 conn, 这样我们就拿到了服务提供的服务代理对象

13) 怎么在Activity 中启动自己对应的Service？

14) service和activity怎么进行数据交互？

Activity和Service的交互方式主要有以下几种：通过广播进行交互、通过共享文件、Messenger、AIDL

15) Service的开启方式

16) 请描述一下Service 的生命周期

- onCreate(): 首次创建服务时，系统将调用此方法。如果服务已在运行，则不会调用此方法，该方法只调用一次。
- onStartCommand(): 当另一个组件通过调用startService()请求启动服务时，系统将调用此方法。
- onDestroy(): 当服务不再使用且将被销毁时，系统将调用此方法。
- onBind(): 当另一个组件通过调用bindService()与服务绑定时，系统将调用此方法。
- onUnbind(): 当另一个组件通过调用unbindService()与服务解绑时，系统将调用此方法。
- onRebind(): 当旧的组件与服务解绑后，另一个新的组件与服务绑定，onUnbind()返回true时，系统将调用此方法。

17) 请描述一下广播BroadcastReceiver的理解

18) 广播的分类

19) 广播使用的方式和场景

20) BroadcastReceiver，LocalBroadcastReceiver 区别

BroadcastReceiver用于应用之间的传递消息；而LocalBroadcastManager用于应用内部传递消息，比broadcastReceiver更加高效。

BroadcastReceiver使用的Content API，所以本质上它是跨应用的，所以在使用它时必须要考虑到不要被别的应用滥用；LocalBroadcastManager不需要考虑安全问题，因为它只在应用内部有效。

21) AlertDialog,popupWindow,Activity区别

AlertDialog 是非阻塞式对话框；而PopupWindow 是阻塞式对话框。

两者最根本的区别在于有没有新建一个 window，PopupWindow 没有新建，而是通过 WMS 将 View 加到 DecorView；Dialog 是新建了一个 window (PhoneWindow)，相当于走了一遍 Activity 中创建 window 的流程。

22) Application 和 Activity 的 Context 对象的区别

Acitiivity 继承自ContextThemeWrapper--->再继承ContextWrapper--->Context。

Appliction 、Service继承自ContextWrapper--->再继承Context。

Application、Service 和 Activity 最终都是继承自Context，所以它们是同一个上下文。

23) Android属性动画特性

属性动画可以对任何对象的属性做动画而不仅仅是View，甚至可以没有对象。除了作用对象进行扩展外，属性动画的效果也加强了，不仅能实现View动画的4中效果，还能实现其它多种效果，这些效果都是通过ValuAnimator或ObjectAnimator、AnimatorSet等来实现的。

24) 如何导入外部数据库?

25) LinearLayout、RelativeLayout、FrameLayout的特性及对比，并介绍使用场景。

26) 谈谈对接口与回调的理解

27) 回调的原理

回调是一段可执行的代码通过参数传递给别一段代码，以期望在一个合适的时间调用这个参数

28) 写一个回调demo

    Callback.java
    public interface Callback {
        void printFinished(String msg);
    }
    Printer.java
    public class Printer {
        public void print(Callback callback) {
            System.out.println("正在打印 . . . ");
            try {
                Thread.currentThread();
                Thread.sleep(3000);// 毫秒
            } catch (Exception e) {
                e.printStackTrace();
            }
            callback.printFinished("打印完成");
        }
    }
    People.java
    public class People {
        Printer printer = new Printer();
        // 同步回调
        public void goToPrintSyn(Callback callback) {
            printer.print(callback);
        }
        // 异步回调
        public void goToPrintASyn(Callback callback) {
            new Thread(new Runnable() {
                public void run() {
                    printer.print(callback);
                }
            }).start();
        }
    }

29) 介绍下SurfView

30) RecycleView的使用

31) 序列化的作用，以及Android两种序列化的区别

32) 差值器

Interpolator设置 属性值 从初始值过渡到结束值 的变化规律的一个接口，如匀速、加速 & 减速 等等,即确定了 动画效果变化的模式，如匀速变化、加速变化 等等

应用场景：实现非线性运动的动画效果

33) 估值器

TypeEvaluator设置 属性值 从初始值过渡到结束值 的变化具体数值的接口

插值器（Interpolator）决定 值 的变化规律（匀速、加速blabla），即决定的是变化趋势；而接下来的具体变化数值则交给估值器

属性动画特有的属性，协助插值器 实现非线性运动的动画效果

34) Android中数据存储方式

五种数据存储 ：SharePreferences、SQLite、Contert Provider、File、网络存储

（二）Android源码相关分析

1) Android动画框架实现原理

Android 动画就是通过 ParentView 来不断调整 ChildView 的画布坐标系来实现的

这其中又涉及到两个重要的类型，Animation 和 Transformation，这两个类是实现动画的主要的类，Animation 中主要定义了动画的一些属性比如开始时间、持续时间、是否重复播放等，这个类主要有两个重要的函数：getTransformation 和 applyTransformation，在 getTransformation 中 Animation 会根据动画的属性来产生一系列的差值点，然后将这些差值点传给 applyTransformation，这个函数将根据这些点来生成不同的 Transformation，Transformation 中包含一个矩阵和 alpha 值

2) Android各个版本API的区别

    //V9.0：刘海屏的适配、电源管理、开发的应用默认不支持Http
    //V8.0：通知栏适配（Notifcation）、广播限制、后台服务限制 8.0以上创建的前台Service需要发送一个Notification,否则Service会Anr
    //V7.0：多窗口支持、文件读写权限适配、引入一项新的应用签名方案 :APK Signature Scheme v2、需要适配FileProvider,否则应用会崩溃。app之间的私有文件共享只能用FileProvider这种方式.
    //V6.0：Android 动态权限申请、指纹识别、移除HttpClient库
    //V5.0：虚拟机由Dalvik替换为Art虚拟机，Dalvik 使用JIT编译器，Art是AOT编译器、Materil Design设计规范、WebView cookie 存储问题
    //V4.0：沉浸式状态栏、WebView webview调试功能、WebView 增加对 https请求限制需要去验证https证书

3) Requestlayout，onlayout，onDraw，DrawChild区别与联系

requestLayout()方法对View树进行重新布局，过程包括了measure()和layout()过程，但不会调用draw()过程，即不会发生重新绘制视图过程。

onLayout()的调用时机是：View需要给自己设置大小和位置了或者ViewGroup需要给子View和ViewGroup自身时调用。

View的绘制流程一共包括三步：①测量measure；②布局layout；③绘制draw；onDraw()方法就是在第三布绘制时发生，开发者已经测量好View的大小，设置好View的布局，剩下最后一步就是，具体画出这个布局。画的方法就是onDraw()，每个View都需要利用这个方法画出自己，ViewGroup除非设置了背景，否则不用调用该方法。

drawChild()去重新回调每个子视图的draw()方法

4) invalidate和postInvalidate的区别及使用

当Invalidate()被调用的时候，View的OnDraw()就会被调用；Invalidate()是刷新UI，UI更新必须在主线程，所以invalidate必须在UI线程中被调用，如果在子线程中更新视图的就调用postInvalidate()。

postInvalidate()实际调用的方法，mHandler.sendMessageDelayed，在子线程中用handler发送消息，所以才能在子线程中使用。

5) Activity-Window-View三者的差别

Activity 是四大组件之一，也是我们的界面载体，可以展示页面；而 View 实际上就是一个一个的视图，这些视图可以搭载在一个 Layout 文件上，通过 Activity 的 setContentView() 方法传递给 Activity；Window 是一个窗体，每个 Activity 对应一个 Window，通常我们在代码中用 getWindow() 来获取它。

每个 Activity 包含了一个 Window 对象，这个对象是由 PhoneWindow 做的实现。而 PhoneWindow 将 DecorView 作为了一个应用窗口的根 View，这个 DecorView 又把屏幕划分为了两个区域：一个是 TitleView，一个是 ContentView，而我们平时在 Xml 文件中写的布局正好是展示在 ContentView 中的。



6) 谈谈对Volley的理解

7) 如何优化自定义View

8) 低版本SDK如何实现高版本api？

9) 描述一次网络请求的流程

10) HttpUrlConnection 和 okhttp关系

11) Bitmap对象的理解

12) looper架构

13) ActivityThread，AMS，WMS的工作原理

14) 自定义View如何考虑机型适配

15) 自定义View的事件

16) AstncTask+HttpClient 与 AsyncHttpClient有什么区别？

17) LaunchMode应用场景

18) AsyncTask 如何使用?

19) SpareArray原理

20) 请介绍下ContentProvider 是如何实现数据共享的？

21) AndroidService与Activity之间通信的几种方式

22) IntentService原理及作用是什么？

23) 说说Activity、Intent、Service 是什么关系

24) ApplicationContext和ActivityContext的区别

25) SP是进程同步的吗?有什么方法做到同步？

26) 谈谈多线程在Android中的使用

27) 进程和 Application 的生命周期

28) 封装View的时候怎么知道view的大小

29) RecycleView原理

30) AndroidManifest的作用与理解

31) Canvas save restore

（三）常见的一些原理性问题

1) Handler机制和底层实现

2) Handler、Thread和HandlerThread的差别

3) handler发消息给子线程，looper怎么启动？

4) 关于Handler，在任何地方new Handler 都是什么线程下?

5) ThreadLocal原理，实现及如何保证Local属性？

6) 请解释下在单线程模型中Message、Handler、Message Queue、Looper之间的关系

7) 请描述一下View事件传递分发机制

8) Touch事件传递流程

9) 事件分发中的onTouch 和onTouchEvent 有什么区别，又该如何使用？

10) View和ViewGroup分别有哪些事件分发相关的回调方法

11) View刷新机制

在Android的View刷新机制中，父View负责刷新（invalidateChild）、布局（layoutChild）显示子View。而当子View需要刷新时，则是通知父View刷新子view来完成。

12) View绘制流程

View的绘制基本分为measure、layout、draw 过程

测量一个比较重要的概念是，MeasureSpec一共有三种模式

- UPSPECIFIED : 父容器对于子容器没有任何限制,子容器想要多大就多大
- EXACTLY: 父容器已经为子容器设置了尺寸,子容器应当服从这些边界,不论子容器想要多大的空间。
- AT_MOST：子容器可以是声明大小内的任意大小

https://www.jianshu.com/p/5a71014e7b1b

13) 自定义控件原理

14) 自定义View如何提供获取View属性的接口？

15) Android代码中实现WAP方式联网

16) AsyncTask机制

17) AsyncTask原理及不足

18) 如何取消AsyncTask？

19) 为什么不能在子线程更新UI？

20) ANR产生的原因是什么？

在Android里，应用程序的响应性是由Activity Manager和WindowManager系统服务监视的 。当它监测到以下情况中的一个时，Android就会针对特定的应用程序显示ANR：

- 1.在5秒内没有响应输入的事件（例如，按键按下，屏幕触摸）
- 2.BroadcastReceiver在10秒内没有执行完毕
- 3.service是20

造成以上两点的原因有很多，比如在主线程中做了非常耗时的操作，比如说是下载，io异常等。

21) ANR定位和修正

22) oom是什么？

23) 什么情况导致oom？

24) 有什么解决方法可以避免OOM？

25) Oom 是否可以try catch？为什么？

26) 内存泄漏是什么？

27) 什么情况导致内存泄漏？

- 资源性对象未关闭(比如Cursor、File等)
- 注册对象未注销，一般发生在广播接收器、注册观察者等。
- 类的静态变量持有大数据对象，如Bitmap等
- 非静态内部类的静态实例，静态内部类会维持一个外部类实例的引用，阻止被系统回收。
- Handler临时性内存泄漏
- 容器中的对象没清理，在不需要该对象时，应该及时从集合中清理出去。
- WebView

28) 如何防止线程的内存泄漏？

检查、监控、优化

- 对象引用-根据业务需求合理的使用强弱软虚引用。
- 减少不必要的内存开销-内存复用
  有效利用系统自带的资源，比如一些通用的字符串、颜色定义、常用Icon图标，还有些样式和简单布局。
  视图复用-adapter里ViewHolder的运用
  使用对象池减少内存的分配和回收
  Bitmap对象的复用-inBitmap属性可以告知Bitmap解码器尝试使用已经存在的内存区域。
- 使用最优的数据类型
  HashMap与ArrayMap，Android提供的ArrayMap更节省内存。
  尽量避免使用枚举类型-枚举类型的最大优点是类型安全，但在Android平台上内存开销是直接定义常量的三倍以上
  LruCache-推荐做图片内存缓存，既不要太大(会造成其他可用内存太小)，也不要太小，具体要综合考虑。
- 图片内存优化
  设置位图规格、isSampleSize、inScaled/inDensity/inTargetDensity、inBitmap(decode方法会尝试重用一个已经存在的位图)
  

29) 内存泄露场景的解决方法

30) 内存泄漏和内存溢出区别？

31) LruCache默认缓存大小。基本上设置为手机内存的1/8

32) ContentProvider的权限管理(解答：读写分离，权限控制-精确到表级，URL控制)

33) 如何通过广播拦截和abort一条短信？

在清单文件中注册广播接收器，设置该广播接收器优先级,尽量设高一点

创建一个BroadcastReceiver来实现广播的处理，并设置拦截器abortBroadcast();

34) 广播是否可以请求网络？**子线程可以**

35) 广播引起anr的时间限制是多少？**10s**

36) 计算一个view的嵌套层级

    while(view.getParent() != null) {
      count++;
      View = view.getParents();
    }

37) Activity栈

38) Android线程有没有上限？

39) 线程池有没有上限？

40) ListView重用的是什么？

41) Android为什么引入Parcelable？

Serializable 会使用反射，序列化和反序列化过程需要大量 I/O 操作， Parcelable 自已实现封送和解封（marshalled &unmarshalled）操作不需要用反射，数据也存放在 Native 内存中，效率要快很多。

42) 有没有尝试简化Parcelable的使用？

（四）开发中常见的一些问题

1) ListView 中图片错位的问题是如何产生的?

2) 混合开发有了解吗？

3) 知道哪些混合开发的方式？说出它们的优缺点和各自使用场景？（解答：比如:RN，weex，H5，小程序，WPA等。做Android的了解一些前- 端js等还是很有好处的)；

4) 屏幕适配的处理技巧都有哪些?

5) 服务器只提供数据接收接口，在多线程或多进程条件下，如何保证数据的有序到达？

6) 动态布局的理解

7) 怎么去除重复代码？

8) 画出 Android 的大体架构图



- 应用层：用Java语言编写的运行在虚拟机上的程序，如电子邮件、短信、日历、浏览器和联系人等
- 应用框架层：系统组件API（Content Provicers、Views、Manager(Activity、Notification、Resource、Telephony、Window)）
- 系统运行库(原生C/C++库及Android运行库)：当使用Android应用框架时，Android系统会通过一些C/C++库来支持我们使用的各个组件，使其更好的为我们服务，比如SQLite、Webkit。
- Linux内核：Android核心系统服务，如安全性、内存管理、进程管理、网络协议栈和驱动模型都依赖于该内核。Linux内核也是作为硬件与软件栈的抽象层。

9) Recycleview和ListView的区别

RecyclerView比ListView多两级缓存，支持多个离ItemView缓存，支持开发者自定义缓存处理逻辑，支持所有RecyclerView共用同一个RecyclerViewPool(缓存池)。

RecyclerView更大的亮点在于提供了局部刷新的接口，通过局部刷新，就能避免调用许多无用的bindView。ListView和RecyclerView最大的区别在于数据源改变时的缓存的处理逻辑，ListView是"一锅端"，将所有的mActiveViews都移入了二级缓存mScrapViews，而RecyclerView则是更加灵活地对每个View修改标志位，区分是否重新bindView.

https://www.jianshu.com/p/257c279a3493

10) ListView图片加载错乱的原理和解决方案

1>：某一个位置的元素刚进入屏幕开始请求图片，图片没有下载完成，就被移出屏幕，根据ListView工作原理可知，被移出屏幕的控件会很快的被重复利用起来，如果在这个时候之前发起图片的请求有了响应，会将刚才位置的图片显示到当前位置，虽然他们位置不同，却共用着同一个ImageView实例，这个时候会出现图片乱序；

2>：新进入屏幕的元素也会去请求图片，等图片下载完的时候会设置到同样的ImageView，因此就出现先显示一张图片，然后又变为另一张图片，就造成图片变来变去；

解决方案：

1>：在getView()方法中用url地址给ImageView设置tag标记；

2>：在onPostExecute()方法中调用 mListView.findViewWithTag(imageUrl) 获取ImageView实例，然后判断如果不为null，就把drawable图片设置到该ImageView控件上即可；

11) 动态权限适配方案，权限组的概念

12) Android系统为什么会设计ContentProvider？谈谈你对ContentProvider的理解

ContentProvider应用程序间非常通用的共享数据的一种方式，也是Android官方推荐的方式。Android中许多系统应用都使用该方式实现数据共享，比如通讯录、短信等。

设计用意在于：

封装。对数据进行封装，提供统一的接口，使用者完全不必关心这些数据是在DB，XML、Preferences或者网络请求来的。当项目需求要改变数据来源时，使用我们的地方完全不需要修改。

提供一种跨进程数据共享的方式。

就是数据更新通知机制了。因为数据是在多个应用程序中共享的，当其中一个应用程序改变了这些共享数据的时候，它有责任通知其它应用程序，让它们知道共享数据被修改了，这样它们就可以作相应的处理。

ContentResolver接口的notifyChange函数来通知那些注册了监控特定URI的ContentObserver对象，使得它们可以相应地执行一些处理。ContentObserver可以通过registerContentObserver进行注册。

ContentProvider和调用者在同一个进程，ContentProvider的方法（query/insert/update/delete等）和调用者在同一线程中；

ContentProvider和调用者在不同的进程，ContentProvider的方法会运行在它自身所在进程的一个Binder线程中。

13) 说说ContentProvider、ContentResolver、ContentObserver 之间的关系

- ContentProvider——内容提供者， 在android中的作用是对外共享数据，也就是说你可以通过ContentProvider把应用中的数据共享给其他应用访问，其他应用可以通过ContentProvider 对你应用中的数据进行添删改查。
- ContentResolver——内容解析者， 其作用是按照一定规则访问内容提供者的数据（其实就是调用内容提供者自定义的接口来操作它的数据）。
- ContentObserver——内容观察者，目的是观察(捕捉)特定Uri引起的数据库的变化，继而做一些相应的处理，它类似于数据库技术中的触发器(Trigger)，当ContentObserver所观察的Uri发生变化时，便会触发它。

14) 下拉状态栏是不是影响activity的生命周期

不会

15) 如果在onStop的时候做了网络请求，onResume的时候怎么恢复？

16) Bitmap 使用时候注意什么？

- 要选择合适的图片规格(ALPHA_8、ARGB_4444、ARGB_8888、RGB_565)分别占用1、2、4、2byte,Alpha_8主要用于Alpha通道模板，相当于做一个染色。图像要渲染两次，虽然减少内存，但是增加绘制的开销。头像一般使用ARGB_444
- 减低采样率。BitmapFactory.Options  inSampleSize inJustDecodeBounds
- 复用内存。通过软引用复用内存块
- 及时回收。即，recycle
- 压缩图片。compress
- 尽量不要使用setImageBitmap或setImageResource或BitmapFactory.decodeResource来设置一张大图，因为这些函数在完成decode后，最终都是通过java层的createBitmap来完成的，需要消耗更多内存，可以通过BitmapFactory.decodeStream方法

17) Bitmap的recycler()

18) Android中开启摄像头的主要步骤

19) ViewPager使用细节，如何设置成每次只初始化当前的Fragment，其他的不初始化？

20) 点击事件被拦截，但是想传到下面的View，如何操作？

21) 微信主页面的实现方式

22) 微信上消息小红点的原理

三、高级开发技术面试题

这里讲的是大公司需要用到的一些高端Android技术，这里专门整理了一个文档，希望大家都可以看看。这些题目有点技术含量，需要好点时间去研究一下的。

（一）图片

1) 图片库对比

2) 图片库的源码分析

3) 图片框架缓存实现

4) LRUCache原理

5) 图片加载原理

6) 自己去实现图片库，怎么做？

7) Glide源码解析

8) Glide使用什么缓存？

9) Glide内存缓存如何控制大小？

（二）网络和安全机制

1) 网络框架对比和源码分析

2) 自己去设计网络请求框架，怎么做？

3) okhttp源码



4) 网络请求缓存处理，okhttp如何处理网络缓存的



5) 从网络加载一个10M的图片，说下注意事项

6) TCP的3次握手和四次挥手

- 请求 -> 应答 -> 应答之应答,例：A：您好，我是 A。B：您好 A，我是 B。A：您好 B。
- 挥手：A：B 啊，我不想玩了。B：哦，你不想玩了啊，我知道了。B：A 啊，好吧，我也不玩了，拜拜。A：好的，拜拜。

7) TCP与UDP的区别

- TCP 是面向连接的，UDP 是面向无连接的。TCP 会三次握手，而 UDP 不会。
- TCP 提供可靠交付。通过 TCP 连接传输的数据，无差错、不丢失、不重复、并且按序到达。UDP 继承了 IP 包的特性，不保证不丢失，不保证按顺序到达。
- TCP 是面向字节流的。发送的时候发的是一个流，没头没尾。而 UDP 继承了 IP 的特性，基于数据报的，一个一个地发，一个一个地收。
- TCP 是可以有拥塞控制的。它意识到包丢弃了或者网络的环境不好了，就会根据情况调整自己的行为，看看是不是发快了，要不要发慢点。UDP 就不会，应用让我发，我就发，管它洪水滔天。
- 因而 TCP 其实是一个有状态服务，通俗地讲就是有脑子的，里面精确地记着发送了没有，接收到没有，发送到哪个了，应该接收哪个了，错一点儿都不行。而 UDP 则是无状态服务。通俗地说是没脑子的，天真无邪的，发出去就发出去了。

8) TCP与UDP的应用

UDP使用场景：需要资源少，在网络情况比较好的内网，或者对于丢包不敏感的应用。不需要一对一沟通，建立连接，而是可以广播的应用。需要处理速度快，时延低，可以容忍少数丢包，但是要求即便网络拥塞，也毫不退缩，一往无前的时候。

9) HTTP协议

10) HTTP1.0与2.0的区别

- HTTP1.x的解析是基于文本。HTTP2.0的协议解析决定采用二进制格式，实现方便且健壮。
- HTTP2.0多路复用，即链接共享
- HTTP1.x的header带有大量信息，而且每次都要重复发送，
- HTTP2.0使用encoder来减少需要传输的header大小，通讯双方各自cache一份header fields表，既避免了重复header的传输，又减小了需要传输的大小。
- HTTP2.0也具有server push功能。

11) HTTP报文结构



HTTP 的报文大概分为三大部分。第一部分是请求行，第二部分是请求的首部，第三部分才是请求的正文实体。

12) HTTP与HTTPS的区别以及如何实现安全性

13) 如何验证证书的合法性?

14) https中哪里用了对称加密，哪里用了非对称加密，对加密算法（如RSA）等是否有了解?



15) client如何确定自己发送的消息被server收到?

16) 谈谈你对WebSocket的理解

17) WebSocket与socket的区别

18) 谈谈你对安卓签名的理解。

19) 请解释安卓为啥要加签名机制?

20) 视频加密传输

21) App 是如何沙箱化，为什么要这么做？

22) 权限管理系统（底层的权限是如何进行 grant 的）？

（三）数据库

1) sqlite升级，增加字段的语句

2) 数据库框架对比和源码分析

3) 数据库的优化

4) 数据库数据迁移问题

（四）插件化、模块化、组件化、热修复、增量更新、Gradle

1) 对热修复和插件化的理解

2) 插件化原理分析

3) 模块化实现（好处，原因）

4) 热修复,插件化

5) 项目组件化的理解

6) 描述清点击 Android Studio 的 build 按钮后发生了什么

（五）架构设计和设计模式

1) 谈谈你对Android设计模式的理解**

2) MVC MVP MVVM原理和区别

3) 你所知道的设计模式有哪些？

4) 项目中常用的设计模式

5) 手写生产者/消费者模式

6) 写出观察者模式的代码

7) 适配器模式，装饰者模式，外观模式的异同？

8) 用到的一些开源框架，介绍一个看过源码的，内部实现过程。

9) 谈谈对RxJava的理解

10) RxJava的功能与原理实现

11) RxJava的作用，与平时使用的异步操作来比的优缺点

12) 说说EventBus作用，实现方式，代替EventBus的方式

13) 从0设计一款App整体架构，如何去做？

14) 说一款你认为当前比较火的应用并设计(比如：直播APP，P2P金融，小视频等)

15) 谈谈对java状态机理解

16) Fragment如果在Adapter中使用应该如何解耦？

17) Binder机制及底层实现

18) 对于应用更新这块是如何做的？(解答：灰度，强制更新，分区域更新)？

19) 实现一个Json解析器(可以通过正则提高速度)

20) 统计启动时长,标准

（六）性能优化

1) 如何对Android 应用进行性能分析以及优化?

2) ddms 和 traceView

3) 性能优化如何分析systrace？

4) 用IDE如何分析内存泄漏？

5) Java多线程引发的性能问题，怎么解决？

6) 启动页白屏及黑屏解决？

7) 启动太慢怎么解决？

8) 怎么保证应用启动不卡顿？

9) App启动崩溃异常捕捉

10) 自定义View注意事项

11) 现在下载速度很慢,试从网络协议的角度分析原因,并优化(提示：网络的5层都可以涉及)。

12) Https请求慢的解决办法（提示：DNS，携带数据，直接访问IP）

13) 如何保持应用的稳定性

- 提高代码质量
  - 代码审查
    - 何时代码审查？底层公共模块、重大特性业务、与其他模块有耦合、新手、应用即将发布前
    - 谁来审查？团队审查、模块负责人审查、结对审查
    - 代码审查内容
      - 设计思路与设计思想(单一职责原则、开闭原则)
      - 代码设计(代码复用、更合理的代码、潜在的缺陷、错误处理、效率)
      - 设计逻辑
      - 代码风格(命名、方法长度、函数参数个数)
      - 需求理解是否到位
  - 代码静态扫描工具
    - CheckStyle：检查代码规范和风格
    - FindBugs：可视化UI
    - PMD：主要潜在的Bug、未使用的代码、重复代码、循环体创建新对象
    - Android Lint：代码+布局
- Crash监控
  - Java层Crash监控 实现UncaughtExceptionHandler接口
  - Native层Crash监控，不能通过UncaughtExceptionHandler捕获
  - Crash上报 
- ANR剖析
  - ANR类型：(KeyDispatchTimeout输入5s无响应、BroadcastTimeout 10s、ServiceTimeout 20s)
  - ANR分析
    - ANR IN：发生在ANR的具体类
    - PID：发生ANR的进程
    - Reason：当前ANR类型以及导致ANR的原因
    - CPU usage：CPU的使用情况，ANR前后两个时间点的CPU使用情况
  - ANR监控
- 提高后台进程存活率

14) RecyclerView和ListView的性能对比

15) ListView的优化

16) RecycleView优化

17) View渲染

18) Bitmap如何处理大图，如一张30M的大图，如何预防OOM

19) java中的四种引用的区别以及使用场景

20) 强引用置为null，会不会被回收？

（七）NDK、jni、Binder、AIDL、进程通信有关

1) 请介绍一下NDK

2) 什么是NDK库?

3) jni用过吗？

4) 如何在jni中注册native函数，有几种注册方式?

5) Java如何调用c、c++语言？

6) jni如何调用java层代码？

7) 进程间通信的方式？

8) Binder机制

9) 简述IPC？

10) 什么是AIDL？

11) AIDL解决了什么问题？

12) AIDL如何使用？

13) Android 上的 Inter-Process-Communication 跨进程通信时如何工作的？

14) 多进程场景遇见过么？

15) Android进程分类？

16) 进程和 Application 的生命周期？

17) 进程调度

18) 谈谈对进程共享和线程安全的认识

19) 谈谈对多进程开发的理解以及多进程应用场景

20) 什么是协程？

（八）framework层、ROM定制、Ubuntu、Linux之类的问题

1) java虚拟机的特性

2) 谈谈对jvm的理解

3) JVM内存区域，开线程影响哪块内存

4) 对Dalvik、ART虚拟机有什么了解？

5) Art和Dalvik对比

6) 虚拟机原理，如何自己设计一个虚拟机(内存管理，类加载，双亲委派)

7) 谈谈你对双亲委派模型理解

8) JVM内存模型，内存区域

9) 类加载机制

10) 谈谈对ClassLoader(类加载器)的理解

11) 谈谈对动态加载（OSGI）的理解

12) 内存对象的循环引用及避免

13) 内存回收机制、GC回收策略、GC原理时机以及GC对象

14) 垃圾回收机制与调用System.gc()区别

15) Ubuntu编译安卓系统

16) 系统启动流程是什么？（提示：Zygote进程 –> SystemServer进程 –> 各种系统服务 –> 应用进程）

17) 大体说清一个应用程序安装到手机上时发生了什么

18) 简述Activity启动全部过程

19) App启动流程，从点击桌面开始

20) 逻辑地址与物理地址，为什么使用逻辑地址？

21) Android为每个应用程序分配的内存大小是多少？

22) Android中进程内存的分配，能不能自己分配定额内存？

23) 进程保活的方式

24) 如何保证一个后台服务不被杀死？（相同问题：如何保证service在后台不被kill？）比较省电的方式是什么？

25) App中唤醒其他进程的实现方式

（九）算法

1) 排序算法有哪些？

2) 最快的排序算法是哪个？

3) 手写一个冒泡排序

4) 手写快速排序代码

5) 快速排序的过程、时间复杂度、空间复杂度

6) 手写堆排序

7) 堆排序过程、时间复杂度及空间复杂度

8) 写出你所知道的排序算法及时空复杂度，稳定性

9) 二叉树给出根节点和目标节点，找出从根节点到目标节点的路径

10) 给阿里2万多名员工按年龄排序应该选择哪个算法？

11) GC算法(各种算法的优缺点以及应用场景)

12) 蚁群算法与蒙特卡洛算法

13) 子串包含问题(KMP 算法)写代码实现

14) 一个无序，不重复数组，输出N个元素，使得N个元素的和相加为M，给出时间复杂度、空间复杂度。手写算法

15) 万亿级别的两个URL文件A和B，如何求出A和B的差集C(提示：Bit映射->hash分组->多文件读写效率->磁盘寻址以及应用层面对寻址的优化)

16) 百度POI中如何试下查找最近的商家功能(提示：坐标镜像+R树)。

17) 两个不重复的数组集合中，求共同的元素。

18) 两个不重复的数组集合中，这两个集合都是海量数据，内存中放不下，怎么求共同的元素？

19) 一个文件中有100万个整数，由空格分开，在程序中判断用户输入的整数是否在此文件中。说出最优的方法

20) 一张Bitmap所占内存以及内存占用的计算

21) 2000万个整数，找出第五十大的数字？

22) 烧一根不均匀的绳，从头烧到尾总共需要1个小时。现在有若干条材质相同的绳子，问如何用烧绳的方法来计时一个小时十五分钟呢？

23) 求1000以内的水仙花数以及40亿以内的水仙花数

24) 5枚硬币，2正3反如何划分为两堆然后通过翻转让两堆中正面向上的硬8币和反面向上的硬币个数相同

25) 时针走一圈，时针分针重合几次

26) N*N的方格纸,里面有多少个正方形

27) x个苹果，一天只能吃一个、两个、或者三个，问多少天可以吃完？

（十）其他

1) 在上家公司的技术成长？

2) 做过最有成就感？有技术难度的点？

3) 项目架构是怎么设计的？

4) Glide原理

5) OkHttp原理

6) 热修复原理

7) 日志回捞原理

8) HttpDNS原理

9) AOP
