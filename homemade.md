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
 
 日程更新
