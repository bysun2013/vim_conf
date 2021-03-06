Vim 配置
=============================

代码折叠
------------------------
	za 打开/关闭当前折叠
	zo 打开当前折叠
	zc 关闭当前折叠
	zM 关闭所有折叠
	zR 打开所有折叠

ctags
----------------------
 ctags -R

看代码时的快捷键：
	C-] 跳转到函数定义
	C-T 返回到原来的位置
cscope
----------------------
 cscope -Rbq

下表中列出了cscope的常用选项,如下：

	-R: 在生成索引文件时，搜索子目录树中的代码
	-b: 只生成索引文件，不进入cscope的界面
	-q: 生成cscope.in.out和cscope.po.out文件，加快cscope的索引速度
	-k: 在生成索引文件时，不搜索/usr/include目录
	-i: 如果保存文件列表的文件名不是cscope.files时，需要加此选项告诉cscope到哪儿去找源文件列表。可以使用”-“，表示由标准输入获得文件列表。
	-Idir: 在-I选项指出的目录中查找头文件
	-u: 扫描所有文件，重新生成交叉索引文件
	-C: 在搜索时忽略大小写
	-Ppath: 在以相对路径表示的文件前加上的path，这样，你不用切换到你数据库文件所在的目录也可以使用它了

vim支持8种cscope的查询功能，如下：

	s: 查找C语言符号，即查找函数名、宏、枚举值等出现的地方
	g: 查找函数、宏、枚举等定义的位置，类似ctags所提供的功能
	d: 查找本函数调用的函数
	c: 查找调用本函数的函数
	t: 查找指定的字符串
	e: 查找egrep模式，相当于egrep功能，但查找速度快多了
	f: 查找并打开文件，类似vim的find功能
	i: 查找包含本文件的文件
	:cw 打开quickfix窗口，在查找多个调用本函数的函数时有用！

TagList
------------------------
	:TlistToggle 打开Tlist
	:TlistOpen“打开taglist窗口
	:TlistClose“关闭taglist窗口

在taglist窗口中，可以使用下面的快捷键：

	<CR>          跳到光标下tag所定义的位置，用鼠标双击此tag功能也一样
	o             在一个新打开的窗口中显示光标下tag
	<Space>       显示光标下tag的原型定义
	u             更新taglist窗口中的tag
	s             更改排序方式，在按名字排序和按出现顺序排序间切换
	x             taglist窗口放大和缩小，方便查看较长的tag
	+             打开一个折叠，同zo
	-             将tag折叠起来，同zc
	*             打开所有的折叠，同zR
	=             将所有tag折叠起来，同zM
	[[            跳到前一个文件
	]]            跳到后一个文件
	q             关闭taglist窗口

代码补全
--------------------------
进入Insert模式,将光标放在"->"后面,然后按下"Ctrl+X Ctrl+O";

	Ctrl+P	向前切换成员
	Ctrl+N	向后切换成员
	Ctrl+E	表示退出下拉窗口,并退回到原来录入的文字
	Ctrl+Y	表示退出下拉窗口,并接受当前选项

quickfix
--------------------------
在quickfix模式里经常用到的命令有：

	:cc                显示详细错误信息 (:cc)
	:cp                跳到上一个错误 (:cp)
	:cn                跳到下一个错误 (:cn)
	:cl                列出所有错误 (:cl)
	:cw                如果有错误列表，则打开quickfix窗口 (:cw)
	:col               到前一个旧的错误列表 (:col)
	:cnew              到后一个较新的错误列表 (:cnew)


文件浏览器命令（在文件浏览器窗口中使用）
---------------------------------
	<enter>或双击  如果光标下是目录, 则进入该目录; 如果光标下文件, 则打开该文件
	<tab>   如果光标下是目录, 则进入该目录; 如果光标下文件, 则在新窗口打开该文件
	<F5> 刷新列表
	-  返回上一层目录
	c  使浏览目录成为vim当前工作目录
	d  创建目录
	D  删除当前光标下的目录或文件
	i  切换显示方式
	R  文件或目录重命名
	s  选择排序方式
	r  反向排序列表
	x  定制浏览方式, 使用你指定的程序打开该文件

文件之间切换
----------------------------------

###文件间切换###
	Ctrl+6	下一个文件
	:bn	下一个文件
	:bp	上一个文件

对于用(v)split在多个窗格中打开的文件，这种方法只会在当前窗格中切换不同的文件

###在窗格间切换的方法###
	Ctrl+w+方向键	——切换到前／下／上／后一个窗格
	Ctrl+w+h/j/k/l 	——同上
	Ctrl+ww		——依次向后切换到下一个窗格中

标签
----------------------------------

	ma 在当前位置标记一个书签，书签名为a
	‘a 回到书签a处
	’. 回到你上次编辑的地方

查找单词
----------------------------------

	* 向后找光标所在的关键词
	# 向前找光标所在的关键词

附录
=========================

##vim配置文件中的nnoremap和inoremap有什么区别？##
前者是在普通模式(normal mode)下生效的映射，后者是在插入模式(insert mode)下生效;这样可以在不同模式下使用同一个按键产生不同的效果。

noremap和map的区别是，被映射的序列不会再被递归映射。

