# MarkDown语法简明版

## 标题
	# Header 1
	## Header 2
	### Header 3

## 强调

	*文本*   **文本**
	_文本_   __文本__

## 链接

	An [example](http://url.com/)

## 插入图片

	![alt text](/path/img.jpg)

但在FarBox中，你只需要把图片拖入文本区域就可以了。

## 列表

有序列表, 无段落阻隔:

	1.  Foo
	2.  Bar

无序列表:  

	*   A list item.
	    With multiple paragraphs.
	*   Bar

## 嵌入代码

每行的缩进（相对于上一行）在4个空格或1个Tab时，

这是一行正常的文本.

    这是一行已经预先格式了的
    代码块.

或者你可以另起一行，以3个反引号为开始:

\`\`\`python  
import this  
print 'something'  
\`\`\`

## 水平分割线
3个（或以上）连续的`-`:

	-----------

## 表格
一个表格看起来会如下所示:

    First Header | Second Header | Third Header
    ------------ | ------------- | ------------
    Content Cell | Content Cell  | Content Cell
    Content Cell | Content Cell  | Content Cell

## TOC
`TOC`可以根据文章标题自动索引. 仅需将`[TOC]`放入单独的一行中.  

## 更多  

请参阅[《Markdown 语法说明 (简体中文版)》](http://wowubuntu.com/markdown/)