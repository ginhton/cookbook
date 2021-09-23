Tool
=====

pdf download
  - http://pdf.018zy.com
  - https://sobooks.cc
  - https://www.daocaorenshuwu.com/


browser extension 
  - gooreplacer https://github.com/jiacai2050/gooreplacer
  - dada huaci fanyi
  - SwithyOmega
  - vimium
  - ublock origin


file share
  - https://datash.co/
  - transfer.sh

    - encrypt & upload: ``cat /tmp/hello.txt|gpg -ac -o-|curl -X PUT --upload-file "-" https://transfer.sh/test.txt``
    - download & decrypt: ``curl https://transfer.sh/1lDau/test.txt|gpg -o- > /tmp/hello.txt``
    - delete: ``curl -X DELETE <X-Url-Delete Response Header URL>``

   
UI
  - colorSpace

    - 一个网页工具，可以去除图像里面的用户指定的颜色，对去除背景很有用。
    - https://color.4ty2.fun/


relax
  - noisli
  - mynoise


js
  - rrweb

    - https://github.com/rrweb-io/rrweb
    - 一个可以录制网页操作的 JS 库，不是录制成视频，而是将用户的每一个操作，录制成可复现的脚本。

  - Fuse.js

    - https://fusejs.io/
    - Lightweight fuzzy-search library.


tutorial
  - linear algo

    - http://joshua.smcvt.edu/linearalgebra/#current_version
    - 美国本科生的线性代数教材，免费下载。

  - computer self-taught

    - https://functionalcs.github.io/curriculum/
    - 本文对于计算机科学各门课程的自学，给出了一个完整的方案。

  - shuangpin

    - https://linci.co/sp/ -> this link is outdated

    - emacs-rime: https://manateelazycat.github.io/emacs/2020/03/22/emacs-rime.html

    - emacs-rime: https://hsingko.github.io/p/%E5%9C%A8doom-emacs%E4%B8%AD%E5%AE%89%E8%A3%85emacs-rime/

    - emacs-rime: https://blindwith.science/2019/07/445.html/

    - doom emacs

      1. add (package! rime) in the packages.el and then sync to download packages.

      2. install librime and capnproto in arch linux

      3. in emacs, select rime input method and edit configuration file.

        a. in `rime/default.custom.yaml`:

          .. code-block:: text

            patch:
              schema_list:
                - schema: double_pinyin_mspy
                - schema: luna_pinyin

        b. in `rime/double_pinyin_mspy.custom.yaml`:

          .. code-block:: text

            patch:
              switches:                   # 注意缩进
                - name: ascii_mode
                  reset: 0                # reset 0 的作用是当从其他输入法切换到本输入法重设为指定状态
                  states: [ 中文, 西文 ]   # 选择输入方案后通常需要立即输入中文，故重设 ascii_mode = 0
                - name: full_shape
                  states: [ 半角, 全角 ]   # 而全／半角则可沿用之前方案的用法。
                - name: simplification
                  reset: 1                # 增加这一行：默认启用「繁→簡」转换。
                  states: [ 漢字, 汉字 ]


      4. run commands: rime-compile-module, rime-deploy, rime-sync

      5. now, it may work
  
  - data-science-probability

    - https://luminousmen.com/post/data-science-probability

watch video
  - movie

    - https://www.imeiju.cc

  - download youtube

    - https://www.onlinevideoconverter.com/youtube-converter

  - anime

    - http://www.imomoe.jp/
    - yhdm


paper
  - zetero

    - document manager. open source. cross-platform.

reader
  - zathura

  - mupdf

  - apvlv

algorithm
  - algo visuallizer online

    - https://algorithm-visualizer.org/backtracking/n-queens-problem

search
  - google.com

  - bing.com

  - gugeji.com


wiki
  - moegirl.org

  - wikipedia.org


elgoog replacement
  - search

    - https://gugejiji.com

  - scholar

    - 4243.net
    - c.glgoo.top

  - play shop (for apk download)

    - https://apk.support/apk-downloader

other
  - img compress   

    - https://squoosh.app/


knowledge management
  - target

    - good structure
    - easy to add infomation
    - easy to search

  - github wiki [give up]

    - gollum

      - ruby
      - user is little

  - emacs-wiki [give up]

    - too old

  - penlican [give up]

    - update frequently
    - static site generator
    - similar to hugo, but I think the latter is better

  - evernote [giveup]

    - good but not free

  - wri.pe [give up]

    - evaluation

      - good feel website, simple
      - easy to use
      - but webpage says its 2013
      - cannot find its app

  - readthedocs + Shpinx [preferred]
    - readthedocs: https://github.com/readthedocs/readthedocs.org
    - restructuredText: http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html
    - establish

      - https://www.xncoding.com/2017/01/22/fullstack/readthedoc.html [good]
      - https://www.jianshu.com/p/78e9e1b8553a

    - example

      - https://wtf.readthedocs.io/en/latest/index.html

  - org mode wiki [give up]

    - https://github.com/caiorss/org-wiki

      - seems ugly
      - good search and arrangement
      - update 2 years ago
      - https://caiorss.github.io/org-wiki/

  - vimwiki [delay]

    - tutorial

      - [detail] https://www.cnblogs.com/taosim/articles/3373670.html
      - [good to read] https://blog.csdn.net/yhm07/article/details/41788289
      - [official installation] http://vimwiki.github.io/

    - evaluation
      - look pretty good
      - repo is update frequently


editor
  - gvim (not vim, vim is always no system clipboard support)

  - spacemacs

  - overleaf latex online


jrnl
  - simple journal cmd tool


shell
  - fish


terminal for windows
  - http://www.sunyouqun.com/2019/04/command-line-tools-summary/


graph
  - uml: plantuml
  - flowchart: zenflowchart web


input method

  - rime

    - install ``fcitx-rime``
    - install plum ``curl -fsSL https://git.io/rime-install | bash``
    - ``rime_dir="$HOME/.config/fcitx/rime" bash rime-install``
    - ``rime_dir="$HOME/.config/fcitx/rime" bash rime-install double-pinyin``
    - edit ``$HOME/.config/fcitx/rime/default.yaml``, add double-pinyin-mspy
    - edit ``$HOME/.config/fcitx/rime/double-pinyin-mspy.yaml``, change default to simplification Chinese

  - sougou-pinyin


security
  - kali
  - virtualbox
  - nmap
  - sqlmap
  - archivarix

    - https://en.archivarix.com/
    - 该工具可以用来从 Achive.org 的 Wayback Machine 里面，下载某个网站在指定日期的所有网页。

  - NFC卡模拟


programming language
  - nodejs

    - cnpm

  - python
  - racket


typing exercies
  - keybr.com
  - typingclub.com


media
  - anoise
  - mpv player


game
	- lutris


online storage
  - yunshushu

end of items

