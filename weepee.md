####我爱peewee

一直想写一篇关于peewee的文章，深度的分析下这个软件，这都是因为爱啊
我们使用peewee的时候首先要定义model，peewee的Model使用的是和django等类似的语法，所谓声明式语法。定义表结构的时候是非常直观的，你说是啥就是啥你说有啥就有啥。

我们看peewee的源码，关于model的定义有三个相关的类，


1 ModelAlias
2 ModelOptions
3 BaseModel
4 Model

哦，是4个，好吧，那就4个吧。
我们从Model开始看吧，

     class Model(with_metaclass(BaseModel))
     def with_metaclass(meta, base=object):
 	 	return meta("NewBase", (base,), {})
Model有一个父类，