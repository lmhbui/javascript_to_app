#打开webview方法

android打开webview方法
```js
//startPage为android的接口名称
//'webview'第一个参数为startPage内需要调用的打开webview方法
//@param params 第二个参数即要打开的页面地址
//@param “”  第三个参数传空即可
window.local_obj.startPage('webview', params, '');
```
ios打开webview方法
```js
//openMessageChatView为ios的接口名称
//'url'参数名
//@param params 参数值即要打开的页面地址
connectWebViewJavascriptBridge(function (bridge) {
  bridge.callHandler('openwebview', {
    'url': params
  });
});
```
#关闭webview方法

android关闭webview方法
```js
//exitCurrentPage为android的接口名称
window.local_obj.exitCurrentPage();
```
ios关闭webview方法
```js
//oexitCurrentPage为ios的接口名称
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('exitCurrentPage', {});
});
```
