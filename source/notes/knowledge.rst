Knowledge
==========

encoding
  - en_US.UTF-8：你说英语，你在美国，字符集是utf-8
  - zh_CN.UTF-8：你说中文，你在中国，字符集是utf-8
  - 如果你的LANG环境变量是en_US.UTF-8，那么系统的菜单、程序的工具栏语言、输入法默认语言就都是英文的。
  - 如果你的LANG环境变量是zh_CN.UTF-8，那么系统的菜单、程序的工具栏语言、输入法默认语言就都是中文的。


python -m argument
  - https://www.cnblogs.com/maoguy/p/6670988.html
  - run library module as a script
  - example: python -m SimpleHTTPServer


git submodule
  - git submodule init
  - git submodule update
  - git submodule update --init --recursive
  - GOOD example: http://blog.jqian.net/post/git-submodule.html


non-root access ttyUSB0
  - The currently logged user should have read and write access the serial port over USB. On most Linux distributions, this is done by adding the user to dialout group with the following command:
  - ``sudo usermod -a -G dialout $USER``
  - on Arch Linux this is done by adding the user to uucp group with the following command:
  - ``sudo usermod -a -G uucp $USER``


crypt tar
  - ``tar -zcvf - stuff|openssl des3 -salt -k secretpassword | dd of=stuff.des3``
  - ``dd if=stuff.des3 |openssl des3 -d -k secretpassword|tar zxf -``
  - link: https://blog.csdn.net/guolb57/article/details/6697812

curl post
  - ``curl --request POST --data '{"user":"xxx", "password":123}'``
  - link: https://superuser.com/questions/149329/what-is-the-curl-command-line-syntax-to-do-a-post-request


redirect one ip(A) to another ip(B)
  - mitmproxy https://www.cnblogs.com/grandlulu/p/9525417.html
  - assign network interface(B) another ip(A)
 

linux connect projector
  - ``xrandr``
  - ``xrandr --output HDMI1 --auto``
  - ``xrandr --output VGA1 --mode 1366x768``
  - https://wiki.archlinux.org/index.php/Xrandr\_
  - https://www.ebugg-i.com/forums/linux/ubuntustudio-warning-output-vga1-not-found-ignoring.html


how to stop tracking and ignore changes to a file in git?
  - ``git rm --cached file``
  - ``git update-index --assumen-unchanged [path]``
  - https://stackoverflow.com/questions/936249/how-to-stop-tracking-and-ignore-changes-to-a-file-in-git


assign mutiple ip addresses to single network card
  - https://www.ostechnix.com/how-to-assign-multiple-ip-addresses-to-single-network-card-in-linux/
  - sudo ip addr add 192.168.x.y/24 dev enp0s3


ssh port forwarding
  - https://linuxhint.com/ssh-port-forwarding-linux/

 
git describe
  - https://git-scm.com/docs/git-describe



chinese search
  - algolia

    - expert in search
    - has free plan for personal use

  - hugo
  - hexo

    - next theme: no default search

      - https://yashuning.github.io/2018/06/29/hexo-Next-%E4%B8%BB%E9%A2%98%E6%B7%BB%E5%8A%A0%E6%90%9C%E7%B4%A2%E5%8A%9F%E8%83%BD/

    - hexo-theme-doc主题实现中文搜索

      - https://tonyrenhk.github.io/2018/11/27/2018-11-27-hexo-theme-doc-SupportCN/

  - sphinx

    - online compile works. It can search chinese word
    - https://solos.im/2015/05/22/Sphinx%E4%B8%AD%E6%96%87%E6%90%9C%E7%B4%A2/


Kalman Filter
  - Kalman Filter 学习笔记 [good]

    - https://www.jianshu.com/p/2768642e3abf

  - Kalman Filter 通俗讲解

    - https://blog.csdn.net/u010665216/article/details/80556000

  - (code) Kalman python 1-dimensional data

    - https://scipy-cookbook.readthedocs.io/items/KalmanFiltering.html

  - (code) python track mousemove

    - https://blog.csdn.net/zuliang001/article/details/80912910


freertos
  - xQueueCreate: 创建新队列。为新队列分配指定的存储空间并返回队列句柄

  - xQueueSend: (call xQueueGenericSend()) 向队列尾部投递一个队列项。项目以拷贝的形式入队，而不是引用形式入队。绝不可以在中断服务例程中调用这个宏，使用带有中断保护的版本xQueueSendFromISR()来完成相同的功能。队列项入队成功返回pdTRUE，否则返回errQUEUE_FULL

  - xQueueSendFromISR:  在中断服务例程中向队列尾部投递一个队列项。

  - xQueueReceive: 这个宏从队列中读取一个队列项并把该队列项从队列中删除。读取队列项是以拷贝的形式完成，而不是以引用的形式，因此必须提供足够大的缓冲区以便容纳队列项。参数pvBuffer指向这个缓冲区。 绝不可以在中断服务例程中调用这个宏，可以使用使用带有中断保护的版本xQueueReceiveFromISR来完成相同功能

  - xQueueReceiveFromISR: 从队列中读取一个队列项并把该队列项从队列中删除。功能与xQueueReceive()相同，用于中断服务函数。


ISR
  - 中断服务例程

  - 中断服务子程序
  

中断向量：
  - 中断服务程序的入口地址。


请求中断
  - 当某一中断源需要CPU为其进行中断服务时，就输出中断请求信号，使中断控制系统的中断请求触发器置位，向CPU请求中断。系统要求中断请求信号一直保持到CPU对其进行中断响应为止。


中断响应
  - CPU对系统内部中断源提出的中断请求必须响应，而且自动取得中断服务子程序的入口地址，执行中断 服务子程序。对于外部中断，CPU在执行当前指令的最后一个时钟周期去查询INTR引脚，若查询到中断请求信号有效，同时在系统开中断（即IF=1）的情 况下，CPU向发出中断请求的外设回送一个低电平有效的中断应答信号，作为对中断请求INTR的应答，系统自动进入中断响应周期。


保护现场
  - 主程序和中断服务子程序都要使用CPU内部寄存器等资源，为使中断处理程序不破坏主程序中寄存器的内容，应先将断点处各寄存器的内容压入堆栈保护起来，再进入的中断处理。现场保护是由用户使用PUSH指令来实现的。


中断服务
  - 中断服务是执行中断的主体部分，不同的中断请求，有各自不同的中断服务内容，需要根据中断源所要完成的功能，事先编写相应的中断服务子程序存入内存，等待中断请求响应后调用执行。


恢复现场
  - 当中断处理完毕后，用户通过POP指令将保存在堆栈中的各个寄存器的内容弹出，即恢复主程序断点处寄存器的原值。


中断返回
  - 在中断服务子程序的最后要安排一条中断返回指令IRET，执行该指令，系统自动将堆栈内保存的 IP/EIP和CS值弹出，从而恢复主程序断点处的地址值，同时还自动恢复标志寄存器FR或EFR的内容，使CPU转到被中断的程序中继续执行


中断嵌套
  - 是指中断系统正在执行一个中断服务时，有另一个优先级更高的中断提出中断请求，这时会暂时终止当前正在执行的级别较低的中断源的服务程序，去处理级别更高的中断源，待处理完毕，再返回到被中断了的中断服务程序继续执行，这个过程就是中断嵌套。


多任务系统 https://blog.csdn.net/Zach_z/article/details/77620708
  - 未加操作系统时，单片机跑裸板程序，一般是在main函数中用以个While(1)的大循环来完成所有操作。即应用程序是一个无限的循环，循环中调用相应的函数完成所需的操作。有时也需要中断中完成一些操作。

  - 相对于多任务系统，这样的while(1)做一个大循环完成所有操作称为前后台系统(单任务系统)，中断服务函数作为前台程序，大循环while(1)作为后台程序。

  - 前后台系统实时性差。各个任务排队等待着轮流执行，但是前后台系统简单。消耗资源少，但在稍微大一些的嵌入式应用中前后台系统显得力不从心

  - 多任务系统把一个大问题，划分成许多小问题，这些小问题单独作为一个小任务来处理。这些小任务是并发处理的，但并不是同一时刻一起执行很多任务，而是由于每个任务执行的时间很短，导致看起来同一时刻执行了很多任务。

  - 多任务系统中的任务调度器，使操作系统永远执行高优先级的任务，高优先级的任务可以打断低优先级任务而取得CPU的使用权，高优先级的任务执行完成以后重新把CPU的使用权还给低优先级的任务。


python 命名规范（建议）

  - 项目名：　首字母大写，其余小写字母，若多个单词组合可以添加 ``_`` 增加可读性。 ``Ui_test``

  - 包名，模块名：　全部小写字母,尽量不要用下划线(除非多个单词，且数量不多的情况)


  - 类名: 首字母大写. ``KalmanFilter, TaskQueue``

  - 全局变量名：　大写字母，单词之间用 ``_`` 分割. ``NUMBER, COLOR_WRITE``

  - 普通变量：　小写字母，单词之间用 ``_`` 分割. 单下划线结尾一般只是为了避免和关键字冲突. ``this_is_a_var``

  - 实例变量：　以 ``_`` 开头，其他和普通变量一样. ``_kalman_filter, _price``

  - 私有变量：　以 ``__`` 开头，其他和普通变量一样. ``__private_var``

  - 专有变量：　以 ``__`` 开头， ``__`` 结尾，一般为 python 的自有变量. ``__class__, __doc__``

  - 函数：　和普通变量一样. ``get_name(), count_number(), ad_stat()``

  - 私有函数：　以 ``__`` 开头，　其他和普通函数一样. ``__get_name()``


Mutex 一句话：保护共享资源


semaphore 一句话：调度线程
  - 调度线程就是，一些线程生产（increase），一些线程消费(decrease)，semaphore可以让生产和消费保持合乎逻辑的执行顺序


线程池是通过用固定数量的线程去执行任务队列里的任务来达到避免反复创建和销毁线程而造成的资源浪费；而semaphore并没有直接提供这种机制


条件锁，是为了避免绝大多数情况下都是lock ---> 判断条件 ----> unlock的这种很占资源但又不干什么事情的线程。


锁是服务于共享资源的；而semaphore是服务于多个线程间的执行的逻辑顺序的。


bash脚本，等号左右不能有空格


shell脚本中，文件名包含的空格会导致命令运行出错。此时需要设置IFS
::

   MY_SAVEIFS=$IFS
   IFS=$'\n'

   # balalallal

   IFS=$MY_SAVEIFS

adb pull /storage/emulated/0/1.txt ~/my/temp


adb push ~/my/temp/1.txt /storage/emulated/0/


CONTAINER_OF在Linux内核中是一个常用的宏，用于从包含在某个结构中的指针获得结构本身的指针，通俗地讲就是通过结构体变量中某个成员的首地址进而获得整个结构体变量的首地址。


container_of(ptr, type, member) 
  -	ptr:表示结构体中member的地址
  -	type:表示结构体类型
  -	member:表示结构体中的成员
  - 通过ptr的地址可以返回结构体的首地址


container_of的实现::

  #define container_of(ptr, type, member) ({ \ 
  const typeof( ((type *)0)->member ) *__mptr = (ptr);  \
  (type *)( (char *)__mptr - offsetof(type,member) );})

  /* 第一步，首先定义一个临时的数据类型（通过typeof( ((type *)0)->member )获得）与ptr相同的指针变量__mptr，然后用它来保存ptr的值。 */
  /* 第二步，用(char *)__mptr减去member在结构体中的偏移量，得到的值就是整个结构体变量的首地址（整个宏的返回值就是这个首地址） */


offset_of::

   #define offsetof(type, member) (size_t)&(((type*)0)->member)


diff three type

  - normal diff (diff f1 f2) (c -> change, a -> add, d -> delete)
    ::

      4c4
      < a
      ---
      > b


  - context diff (diff -c f1 f2)
    ::

      *** f1	2012-08-29 16:45:41.000000000 +0800
      --- f2	2012-08-29 16:45:51.000000000 +0800
      ***************
      *** 1,7 ****
      a
      a
      a
      !a
      a
      a
      a
      --- 1,7 ----
      a
      a
      a
      !b
      a
      a
      a


  - unified diff (diff -u f1 f2)
    ::

      --- f1	2012-08-29 16:45:41.000000000 +0800
      +++ f2	2012-08-29 16:45:51.000000000 +0800
      @@ -1,7 +1,7 @@
      a
      a
      a
      -a
      +b
      a
      a
      a


this is an inline code :code:`a = b + c`


manjaro-i3 change desktop wallpaper: :code:`nitrogen --set-zoom path-to-picture`


manjaro 更新后中文变方块
  - sudo pacman -S wqy-bitmapfont
  - sudo pacman -S wqy-microhei
  - sudo pacman -S wqy-zenhei


如何处理与女友吵架的情绪：
  ①，避免正面冲突和理论。女生是情绪动物，情绪被放大时是缺乏理智的，谈恋爱不是谈生意，女朋友也不是客户。
  ②，及时认错。这并不是没有骨气的纵容和示弱，这是让女生熄火的最简单，最直接，最有效的话语。大丈夫能屈能伸，对一个小女子何必那么较真？
  ③，温柔应对。她越是生气，越是无理取闹，你则越是要稳住自己，与她大吵一番只会两败俱伤，如果你想跟她和好，就最好不要采取硬碰硬的方式解决问题。
  ④，淳淳引导。告诉她自己如此做是因为爱她，在她情绪平复下来把下一次出现矛盾和问题时能够告诉你而不是生闷气或者发脾气的期许告诉她，慢慢的，一次又一次的加深她的印象和观念，这是杜绝让步和示弱会让女朋友有恃无恐的有效办法。

another item
