# javascript和app交互指南


##javascript调用App方法
安卓的webview会在页面上设置一个全局的对象window.local_obj, js调用此方法即可。
```js
window.local_obj.somefunction(...);
```
苹果的webview会在页面设置JavascriptBridge，并返回一个bridge
```js
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler(args);
});
```

[社区JS与APP交互接口文档](sns.md)



