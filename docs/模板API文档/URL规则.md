
[TOC]

# URL规则  
> FarBox引擎上的页面，首先会遵循系统默认的URL规则；其次会根据使用者的模板页面，自动创建出自定义的URL映射。  

## 默认URL规则

### URL与模板文件
*`模板文件`是指`/template/`目录下的文件*

| 页面名 | url | 使用的模板| 补充说明 |
| ----- | --- | --- |
| 首页 | / | index.html |如果根目录放置index.html文件，则会显示index.html的内容|
| 文章详细页|/post/`<path>` | post.html  |
| 文章分类页 | /category/`<path>` | category.html | path是对应的文件夹路径，显示该文件夹的所有文章 |
| 标签匹配页 | /tags/`<tags>` | tags.html |单标签`/tags/tag1`; 多标签`/tags/tag1+tag2` |
| 博客归档页 | /archive | archive.html|
| 文件目录 |/folder/ & /folder/`<path>` | folder.html| 现仅支持图片 |
| 单文件详细 | /file/`<path>` | file.html | 现仅支持图片 |
| RSS订阅页 | /feed | feed.html | 默认全文输出，可自定义 |
| MarkDown文档页 | /`<path>`| markdown.html| 对普通文章类文件(markdown为主)进行HTML渲染|
| 静态文件 | /`<path>` | 无 | 不要忘记有个`/`开头 |
| 404页面 | 无 | errors/404.html | 当文章、文件找不到时候的页面 |

- - - - - - - - - -	

### 举例说明

	|-- site-folder@yourdomain.com --> http://yourdomain.com/会是首页
		|-- your-article.txt(.txt .md .markdown .docx格式结尾的文件会被视为日志)
			 ---> http://yourdomain.com/post/your-article可以访问文章详细页面
		|-- folder-1
			-- your-article-in-folder.txt
			   ---> http://yourdomain.com/post/your-article-in-folder 可访问
		|-- file.jpg (可以随便什么后缀，这表示非日志的文件)
		     --->  http://yourdomain.com/file.jpg 可访问
		|-- another-folder
			-- file-in-folder.jpg
				--->  http://yourdomain.com/another-folder/file.jpg 可访问
		|-- this-is-md-file.md (MarkDown文档)
	        ---> http://yourdomain.com/this-is-md-file.md
								
- - - - - - - - - -	
		
## 自定义URL规则

### 实现逻辑

FarBox会根据你自己模板目录下的文件，自动对应自定义URL。  

比如`/template/you.html`，这个模板文件如果存在，那么，访问`http://yoursite.domain.com/you`就会自动对应到这个模板。

- - - - - - - - 

### 注意事项
-	自定义url不能以`/`结尾，这是JSON API显示目录用的，会无法匹配自定义URL。
-	不要使用中文来命名模板文件，比如`/template/你好.html`是无效的。
-	模板文件必须保证`.html`的后缀，`.htm`也是无效的。  
-   也不要跟系统默认的url产生冲突，否则会无效；自定义url优先级低于系统url。
