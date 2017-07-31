# vue-source
![](https://github.com/jackfxq/vue-source/raw/master/images/1.png)
vue构造函数调用了this._init(options)方法，这个方法在initMixin中，如上图所示，进入initMixin
![](https://github.com/jackfxq/vue-source/raw/master/images/2.png)
initMixin主要完成数据的初始化和视图的初始化：<br> 
1.数据初始化主要是数据的observe，在上图的initState中进行；<br> 
2.视图的初始化在vm.$mount(vm.$options.el),其中vm为Vue的实例，watcher的设置也是在vm.$mount(vm.$options.el）中完成的；<br> 
##数据初始化
接着上面我们看看数据初始化都做了什么，进入initState
![](https://github.com/jackfxq/vue-source/raw/master/images/3.png)
这里我们主要对数据进行操作的是initData，传入的是vm，我们来具体看看initData：
![](https://github.com/jackfxq/vue-source/raw/master/images/4.png)
我们先忽略前面的一些逻辑判断，主要看两个地方：<br>
1.数据代理，主要是将_data的数据代理到vm上，这样的话可以直接对vm上的数据进行修改;<br>
2.数据observe，传入data<br>
我们先看看vue怎么对数据进行observe的
![](https://github.com/jackfxq/vue-source/raw/master/images/5.png)
