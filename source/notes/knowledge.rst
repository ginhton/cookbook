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


another item
