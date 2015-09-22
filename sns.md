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
#设置头像
android设置头像
```js
//setheadpicture为android的接口名称
//参数传空即可
window.local_obj.startPage('setheadpicture', '', '');
```
ios设置头像
```js
//setheadpicture为ios的接口名称
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('setheadpicture', {});
});
```
#系统设置
android系统设置
```js
//systemsetting为android的接口名称
//参数传空即可
window.local_obj.startPage('systemsetting', '', '');
```
ios系统设置
```js
//defaultsetting为ios的接口名称
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('defaultsetting', {});
});
```
#打开贴子详情页
android打开贴子详情页
```js
//notedetail为android的接口名称
//params参数传帖子id
window.local_obj.startPage('notedetail', params, '');
```
ios打开贴子详情页
```js
//notedetail为ios的接口名称
//postid参数，params的值传帖子id
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('notedetail', {
         'postid': params
    });
});
```
#打开好货详情页
android打开好货详情页
```js
//goodsdetail为android的接口名称
//params参数传好货id
window.local_obj.startPage('goodsdetail', params, '');
```
ios打开好货详情页
```js
//fondgoodsdetail为ios的接口名称
//postid参数名，params的值传好货id
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('fondgoodsdetail', {
        'postid': params
    });
});
```
#打开圈子详情页
android打开圈子详情页
```js
//circledetail为android的接口名称
//params参数传圈子id
window.local_obj.startPage('circledetail', params, '');
```
ios打开圈子详情页
```js
//circleDetail为ios的接口名称
//postid参数名，params的值传圈子id
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('circleDetail', {
        'postid': params
    });
});
```
#打开圈子中写帖子页面
android打开圈子中写帖子页面
```js
//writenote为android的接口名称
//params参数传圈子id
 window.local_obj.startPage('writenote', params, '');
```
ios打开圈子中写帖子页面
```js
//sentNote为ios的接口名称
//circleid参数名，params的值传圈子id
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('sentNote', {
        'circleid': params
    });
});
```
#打开对话页
android打开对话页
```js
//sendpersonalmessage为android的接口名称
//params参数传用户id
 window.local_obj.startPage('sendpersonalmessage', params, '');
```
ios打开对话页
```js
//openMessageChatView为ios的接口名称
//userid参数名，params的值传用户id
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('openMessageChatView', {
        'userid': params
    });
});
```
#分享接口
android分享接口
```js
//shareContent分享接口
//@param share_title  分享的标题
//@param share_content  分享的的内容
//@param imgUrl    图片url
//@param share_url  目标url
//@param isShow 是否显示分享弹窗, "true" 为显示， "false" 为不显示
window.local_obj.shareContent(share_title,share_content, imgUrl,share_url, isShow);
```
ios分享接口
```js
//share_native为ios的接口名称
//sharedata参数名，shareData的值传分享信息的对象信息
shareData = {
    shareTitle: '下载辣妈汇APP，享新人好礼',
    shareTent: '辣妈正品1折起，更懂辣妈的特卖网站',
    imgUrl:'http://img.lamahui.com/app/logo.png',
    shareURL:'http://wap.lamahui.com/inv/f26970'
};
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('share_native', {
        'sharedata': shareData
    });
});
```
