# javascript和app交互指南


##javascript调用App方法
安卓的webview会在页面上设置一个全局的对象window.local_obj.callHandler, js调用此方法即可。
```js
window.local_obj.callHandler(args);
```
苹果的webview会在页面设置JavascriptBridge，并返回一个bridge
```js
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler(args);
});
```

##方法传参约定
安卓和苹果统一约定只传两个参数, commond, options两个参数。
```js
//以打开贴子详情页为例

//安卓
window.local_obj.callHandler('open_post_detail', {
    post_id : 100
});

//苹果
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('open_post_detail', {
        post_id : 100
    });
});
```

##分享交互的实现

####思路：
- 首先在html上埋好需要分享的内容
- 当用户点击分享的时候，原生分享插件去html上获取相应内容，并分享。
- 埋信息，我们则采用自定义meta来解决

####设置分享内容
通常分享一个网页的时候，需要分享以下4项内容。
```html
<meta name="app_share_title" content="分享的标题" />
<meta name="app_share_description" content="分享的内容" />
<meta name="app_share_url" content="分享的链接" />
<meta name="app_share_image" content="分享的图片" />
```

##社区接口约定
####返回，退出当前webview
```js
//安卓
window.local_obj.callHandler('exit_current_page', {});

//苹果
bridge.callHandler('exit_current_page', {});
```






