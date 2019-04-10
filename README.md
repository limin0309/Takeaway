## 具体了解rem。可以在慕课的免费课 移动端web开发rem适配方案

###移动端touch时事件
- touchstart 当手指接触屏幕时触发
- touchmove 当已经接触屏幕的手指开始移动后触发
- touchend 当手指离开屏幕时触发
- touchcancel 当某种touch事件非正常结束时触发

- touches:绑定了多少个手指
- targetTouches：我给谁绑定了事件
- changeTouches：改变触发事件的手指，第一个点击的是1，所以应该是2，3


300ms点击延迟
手机双击显示的文案就会增大。因为浏览器会有300ms去判断是否有下一次的点击事件，所以就会存在300ms延迟的问题

避免300ms点击延迟？
1.在safari和ios 移动webview是不管用的 在chrome是可以的
        <meta name="viewport" content="width=device-width, initial-scale=1.0",maximum-scale=1,minimum-scale=1,user-scalable=no>

2.Tap组件(FastClick,react-tap)
Tap组件的实现原理是touchstart和touchclick。
对移动端来说触发touchstart是没有延迟的，touchClick是有延迟的，在start判断是否有真正的延迟，判断touchmove还是touchclick事件。

点击穿透？
touch-->click
touch事件的target消失，触发底部click
01：44
