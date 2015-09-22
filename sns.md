#打开webview方法


```js
android打开webview接口
//startPage为android的接口名称
//'webview'第一个参数为startPage内需要调用的打开webview方法
//@param params 第二个参数即要打开的页面地址
//@param “”  第三个参数传空即可
window.local_obj.startPage('webview', params, '');
```

```js
ios打开webview接口
//openMessageChatView为ios的接口名称
//'url'参数名
//@param params 参数值即要打开的页面地址
connectWebViewJavascriptBridge(function (bridge) {
  bridge.callHandler('openwebview', {
    'url': params
  });
});
```
