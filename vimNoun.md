## 	This is a markdown to learn noun of vim
理解vim 的一些名词对学习vim是很有必要的
缓冲区(Buffer) 窗口(Window) 标签(Tab) 标记(Tab) 寄存器(Register) 插件(Plugin) vim脚本(VimScript)

### vim缓冲区
	什么是vim缓冲区
		我们打开多个文件的时候比如vim test1 test2 test3 但是这个
		但是这个界面只会展示test1 的相关内容
		但是vim其实是把这三个文件全部都缓存起来了，只是在页面上只展示了一个文件而已
	vim关于缓冲区的解释
	A buffer is an area of Vim’s memory used to hold text read from a file. In addition, an empty buffer with no associated file can be created to allow the entry of text.
	vim 打开文件的时候就会创建缓冲区，打开几个就创建几个缓冲区，默认加载第一个缓冲区，显示第一个文件的内容。vim 的官方解释：缓冲区是一个文件的内容占用的那部分vim内存。
	
	怎么样使用缓冲区
		:ls 列出所有在缓冲区里面的文件
		:bn 切换到下一个缓冲区展示下一个文件的内容
		:bp 切换到上一个缓冲区展示上一个文件的内容
		:b number 切换到指定数字编号的缓冲区
		:b filename 这里的filename 可以是文件名称也可以是相应的正则表达式，也可以是文件名中的个别字母，一旦匹配成功就会加载该缓冲区，显示该文件
### 窗口
	什么是vim 窗口
		vim 的窗口是用来展示 vim缓冲区里面的内容的，可以使用多个窗口展示同一个缓冲区里面的内容，也可以使用多个窗口查看不同的缓冲区

### 标签
	什么是Tab(标签)
		通过浏览器打开网页的时候，打开不同的网页的时候，网页上面通常都会有一个网页标签，这样我们就可以快速的切换不同的网页，vim 也有类似的概念
	
	怎么创建tab标签
		:tabnew tab1 （创建了一个名叫tab1的tab标签）
	
	怎么切换标签
		:tabn (切换到下一个标签)next
		:tabp （切换到上一个标签prev
		gt: 在normal模式下按下gt 自动切换tab
		ngt: 在normal 模式下按住数字键（1，2.3...）然后再按gt 就会切换到对应的tab
	
	怎么关闭标签
		:tabc 关闭当前标签
	
	查看总共有多少个标签
		:tabs

### 标记（mark)

	什么是标记
		我们通常在读一本的时候，通常会加上一个书签，来记录我们当前阅读的进度，在vim当中也有类似的一个概念，在使用vim处理我们的文件的时候也可以通过打标签的方式来快速跳转到当前位置
	
	如何使用
		在键盘上按下m，紧接着再按下任意一个大写或者是小写的字母作为当前标记的书签，例如ma 这样我们就建立了一个叫a的标签
		然后在键盘上按下‘ （单引号）或者是<Esc> 下面那个键然后输入之前标记的书签名称就可以跳转到当初标记的那个位置
	’a和`a的区别
		‘a跳转到之前标记那行的行首，而`a则是跳转到当初标记的那个准确位置
	ma 和 mA的区别
		ma 作为单个文件的标记使用 mA 作为跨文件的标记使用，如果我在文件1里面定义了A这个标记，然后我在文件2里面快捷跳转也是可以的
	列出当前所有的mark标记
		:marks
	清除标记a 
		:delmarks a
	清除所有的标记
		:delmarks!

### 寄存器（register）
	什么是寄存器
		顾名思义，vim的寄存器就是一个存东西的地方,在我们剪切或者是复制东西的时候，这些复制来的东西就被暂时存到了寄存器里面了
		
		在使用不同的操作系统的时候我们,我们经常会用到复制粘贴的功能，当我们复制内容的时候，系统就把内容复制到了剪切板，当我们黏贴使用的时候我们就可以快速的从剪切板里面获取内容
	
		vim也有类似的逻辑，当我们使用y复制内容的时候，vim会默认把内容寄存到一个无名的寄存器，当使用黏贴功能p的时候，就会默认从无名的寄存器里面取出内容
	
	vim如何定义一个有名字的寄存器
		vim的默认使用的是无名寄存器，通常情况下使用是没有问题的，但是我就想把文本复制到一个有名字的地方
		vim 可以使用"(双引号）加上a-z的字母来定义一个有名字的寄存器
		例如：
		
		定义一个寄存器:"ayy 我们把当前的内容复制到了一个名为a的寄存器里面
		使用一个定义好了的有名寄存器: "ap 
		
		无名寄存器的定义
		"" 

### vim插件
	什么是插件
	vim 插件就是扩展vim的功能的东西，比如说想在vim里面拥有一些类似IDE上面的好用的功能，这就需要插件来实现了
	
	怎么使用插件
		可以通过插件管理器，把插件绑定到茨木编辑器上面，然后我们就可以在使用vim 的时候使用插件提供的功能了（vim-plug）

### vim的脚本
	什么是VimScript
		VimScript是一个专注于做vim的编程语言，vim插件很多都是使用VimScript去实现的

分享一个 很好用的屏幕按键显示插件
​		https://github.com/Code52/carnac/releases/tag/2.3.13
		找到下面的setup.exe 下载就行


