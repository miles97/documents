#### sharp 

* doing about future

* 小程序渲染的默认wx:for-item="item"，需要嵌套循环的时候使用wx:for-item="name"重命名,相当于vue中的 name,index in Array

* 使用web-view

小程序使用webview

直接新建一个components,js中配置，wxml写
```js
 <web-view  src="{{url}}?openId={{openId}}&uid={{uid}}&hash=1"></web-view>
 ```
 
 vue中使用webview(实际上并不叫webview)
 ```
 window.location.href =
  "https://baidu.com/html/dd.html?id=" +
  item.1d +
  "&sourceType=1&deviceType=1";
  ```
 
 ### 使用WS的场景
 所用的技术都是 Ajax 轮询。轮询是在特定的的时间间隔（如每1秒），由浏览器对服务器发出HTTP请求，然后由服务器返回最新的数据给客户端的浏览器。这种传统的模式带来很明显的缺点，即浏览器需要不断的向服务器发出请求，然而HTTP请求可能包含较长的头部，其中真正有效的数据可能只是很小的一部分，显然这样会浪费很多的带宽等资源。

HTML5 定义的 WebSocket 协议，能更好的节省服务器资源和带宽，并且能够更实时地进行通讯。
WebSocket 事件
以下是 WebSocket 对象的相关事件。假定我们使用了以上代码创建了 Socket 对象：

open	Socket.onopen	连接建立时触发
message	Socket.onmessage	客户端接收服务端数据时触发
error	Socket.onerror	通信发生错误时触发
close	Socket.onclose	连接关闭时触发
```js
        var socket;
        if (!window.WebSocket) {
            window.WebSocket = window.MozWebSocket;
        }
        if (window.WebSocket) {
            socket = new WebSocket("ws://101.222.210.73:12/ws");//使用字符串拼接${this.requestUrl}
            socket.onmessage = function(event) {
                console.log(event.data);
                pollingFun();
            };
            socket.onopen = function(event) {
                var msg = {
                    type : '001',
                    ad : ad
                };
                socket.send(JSON.stringify(msg));
                console.log("连接开启!");
                pollingFun();
            };
            socket.onclose = function(event) {
                console.log("连接被关闭");
                setInterval(pollingFun,1500);
            };
        } else {
            alert("你的浏览器不支持 WebSocket！");
            setInterval(pollingFun,1500);
        }
```

属性	描述
Socket.readyState	
只读属性 readyState 表示连接状态，可以是以下值：

0 - 表示连接尚未建立。

1 - 表示连接已建立，可以进行通信。

2 - 表示连接正在进行关闭。

3 - 表示连接已经关闭或者连接不能打开。

Socket.bufferedAmount	
只读属性 bufferedAmount 已被 send() 放入正在队列中等待传输，但是还没有发出的 UTF-8 文本字节数。
