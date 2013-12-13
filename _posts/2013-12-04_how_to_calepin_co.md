Title: 简单Calepin教程
Date: 2013-12-04
Category:StaticSite
Tag:Calepin, Blog, DropBox

首先进入*http://calepin.co/*，根据引导完成三个步骤。

* step 1:登陆DropBox
* step 2:配置页面的Title
* step 3:发布

然后在DropBox的应用下，就能找到calepin文件夹。
里面都是你要发布的文章。以md格式保存。

每个文件代表一页发布的页面。

------------------
###元数据

必须: **Title*** 和 **Date**。

calepin能够识别的Date格式有:

- 13.12.2011
- 2011/12/13
- 2011-12-13
- 2011-12-13 12:30
- 2011-12-13 12:30:10

###可选:

- **Slug**:可选自定义Url。
- **Tag & Category**:标签
- **Author**:只在Atom feed中显示，不设置的话将显示settings.json中的author字段
- **Status**:如果被设置为draft，那该页将不在主页中显示

------------------
######代码高亮:
calepin支持代码高亮。代码行将以四空格缩进。在代码的第一行以 :::C# 这样的格式标记。
支持的语言请参考 http://pygments.org/languages/

######摘要:
如果你想要一个摘要，那么在元数据中追加
Abstract:在很久很久很久以前，有一个...

######文章排序:
calepin以时间排序。如果你两个页面是同一天发布的，那么请在Date中添加更小的时间单位

######管理markdown文件:
calepin不关心文件名，所以根据你的喜好去组织吧。

######标签:
如果你觉得你需要使用分类和标签的话，在元数据中添加他们。

######追加图片到页面中:
先把照片拷贝到Public文件夹中，然后点右键从DropBox的菜单中拷贝Public Url。
然后在编辑器中，将图片链接贴到markdown标签中。
比如说:

![Teapot](http://dl.dropbox.com/u/153068/12036372529.gif)

######页面链接:
通常来书哦，calepin会把Title转换成URL。比如说，**Title**是"Hello World"，会被转成hello-world，然后加上html。
当然你也可以自定义，使用Slug标签，
**Slug**:hey-world

######RSS/Atom Feeds:
calepin支持RSS和Atom Feeds。用 http://username.calepin.co 这种格式会自动获取到。

######settings.json
当然还可以用settings.json来定义页面的更多属性。如下:

- **author** - 作为Atom feed的作者属性使用
- **default_date_format** - Python 的 strftime 格式字符串用来格式化Date的显示输出。
- **google_analytics** - 会在每页渲染谷歌的 Analytics ID .
- **default_pagination** - 每页的默认分页条数。
- **with_future_dates** - 定义文章可以定时发布。
- **clean_urls** - 如果设置为 true， 那么caleping回味每个post生成一个文件夹，这样就不会在url里面显示.html这样的后缀了。
- **output_source** - 将页面转化为文本文档，比如说 article.html, 用 article.txt 时，将会以纯文本显示内容。默认是 true.

一个例子:

settings.json:

        {
          "author": "Jökull Sólberg",
          "default_date_format": "%B %e, %Y",
          "with_future_dates": false,
          "google_analytics": "UA-12230384-12"
        }