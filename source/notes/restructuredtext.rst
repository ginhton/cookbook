reStructuredText
=================


reStructuredText是拓展名为.rst的纯文本文件，含义为“重新构建的文本”，也被简称为RST或reST;是python编程语言的docutils项目中的一部分，Python Doc-SIG(Document Special Interest Group）。该项目类似于JAVADoc或Perl的POD项目。Docutils能够从python程序中提取注释和信息，格式化成程序文档。


online tool

	this `site <http://rst.ninjs.org/>`_


bold

  this is **bold**

  :code:`this is **bold**`


italic

	this is *italic*

	:code:`this is *italic*`


monospaced 等宽

  ``行内文本(inline literal)通常显示为等宽文本，空格可以保留，但是换行不行``
  
  double back-quote around text


chapter title

	章节头部由下线（也可有上线）和包含标点的标题组合创建，其中下线要至少等于标题文本的长度。

	可以表示标题的符号有，=,-,`,:,',",~,^,_,*,+,#,<,>

	标题最多分为6级，可以自由组合使用


paragraph

  段落是被空行分割的文字片段，左侧必须对齐（没有空格，或者有相同的空格）。

  缩进的段落被视为引文


列表符号

  列表符号可以使用-,+,*来表示。

  不同符号结尾需要加上空行，下级列表需要有空格缩进。


枚举列表

  枚举列表即顺序（序号）列表，可以使用不同的枚举序号来表示列表。

  可以使用的枚举有123,A-Z,a-z,I-II-III-X,i-ii-iii-x

  可以为序号添加前缀和后缀，.作为后缀，()包起来，）作为后缀

	枚举列表可以结合#自动生成枚举序号


定义列表

  定义列表可以理解为解释列表，即名词解释。

  条目占一行，解释文本要有缩进；多层可以根据缩进实现。


超链接

	welcome to my `blog <https://ginhton.github.io>`_


内部超链接 锚点 internal hyperlink

  for more information, please refer this_

	some text

	.. _this:

	more information

	

