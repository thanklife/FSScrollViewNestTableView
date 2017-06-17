# FSScrollViewNestTableView
## 这是一个`scrollView`嵌套`tableView`的手势冲突解决方案,详细文档查看[iOS scrollView嵌套tableView的手势冲突解决方案](http://www.jianshu.com/p/8bf6c2953da3)
demo中还用到了本人封装的框架[FSLoopScrollView](https://github.com/shunFSKi/FSLoopScrollView)和[FSScrollViewNestTableView](https://github.com/shunFSKi/FSScrollViewNestTableView)

demo下载下来运行出错后 执行 pod install,再出错执行 pod setup

![效果图](https://github.com/shunFSKi/ImageResources/blob/master/FSScrollViewNestTableView.gif)


代码学习分析：
1，项目中使用的FSBaseViewController 的父类是UIViewController，该控制器的view添加addSubview了FSBaseTableView，FSBaseTableView继承自UITableView 遵循UIGestureRecognizerDelegate代理协议。

FSBaseViewController作为最基本的一层；

这里实现把FSBaseViewController 和 FSBaseTableView，作为相应的视图和控制器，他们的视图就是tableview；
该tableview实现分为2节 section，第0节的第0个row的cell是FSBaseTopTableViewCell，后面的row的cell是FSBaselineTableViewCell， 第1节只有
一个FSBottomTableViewCell；


2，
