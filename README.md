# Garena
Projects in Garena
Unity支持版本：Unity 2017.2.1及以后
Unity制作版本：Unity 2019.3.4f1，导入Device Simulator包，在Unity Editor下也可以看到适配效果。
Screen.safeArea会返回移动平台安全区的Rect。例如，iPhoneX（2436x1125px）横屏时，Screen.safeArea返回的值为Rect（132，63，2172，1062）。

适配思路：以界面为单位，打开界面时，获取当前设备的safeArea，调整界面的锚点，进行适配。以下利用SafeArea.cs脚本，对当前window进行适配。主要考虑三种情况：

情况1：UI中没有全屏背景
解决思路：直接调整当前window的锚点，进行适配。

情况2：UI中有全屏背景
解决思路：把背景分离到window之外，只对当前window进行适配，对背景不做处理。为了方便适配，我们可以把背景单独做成window，在UI框架中对window和背景进行分开管理。上图中，蓝色为背景图片，红色为适配的window。

情况3：适配需要靠边的UI
解决思路：把需要靠边的按钮拉伸到屏幕之外，达到适配效果。

详细请看工程。
