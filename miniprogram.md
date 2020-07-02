### mp项目最佳实践小结

```js
toTCaptcha: function () {
    wx.navigateToMiniProgram({
      appId: 'wx5a3a7366fd07e119',
      path: '/pages/captcha/index',
      extraData: {
        appId: 'appId'//您申请的验证码的 appId
      }
    })
  }
```

#### 小程序总结

//[小程序登录状态流程](https://juejin.im/entry/589944da570c3500624e4554)
