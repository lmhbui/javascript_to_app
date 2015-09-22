#社区与app交互接口
- [打开一个webview](#打开webview方法)     
- [返回/退出当前页](#关闭webview方法)     
- [设置头像](#设置头像) 
- [系统设置](#系统设置) 
- [打开贴子详情页](#打开贴子详情页) 
- [打开好货详情页](#打开好货详情页) 
- [打开圈子详情页](#打开圈子详情页) 
- [打开圈子中写帖子页面](#打开圈子中写帖子页面) 
- [打开私信页](#打开私信页) 
- [分享接口](#设置分享信息接口) 
- [调用示例](#调用示例) 

#打开webview方法
android打开webview方法
```js
/**
*startPage为android的接口名称
*'webview'第一个参数为startPage内需要调用的打开webview方法
* url 即要打开的页面地址
* ''  第三个参数传空即可
*/
window.local_obj.startPage('webview', url, '');
```
ios打开webview方法
```js
/**
 *openMessageChatView为ios的接口名称
 *'url'参数名
 * params 参数值即要打开的页面地址
*/
connectWebViewJavascriptBridge(function (bridge) {
  bridge.callHandler('openwebview', {
    'url': params
  });
});
```
#关闭webview方法

android关闭webview方法
```js
/**
 *exitCurrentPage为android的接口名称
*/
window.local_obj.exitCurrentPage();
```
ios关闭webview方法
```js
/**
 *oexitCurrentPage为ios的接口名称
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('exitCurrentPage', {});
});
```
#设置头像
android设置头像
```js
/**
 *setheadpicture为android的接口名称
 * params 参数传空即可
*/
window.local_obj.startPage('setheadpicture', '', '');
```
ios设置头像
```js
/**
 *setheadpicture为ios的接口名称
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('setheadpicture', {});
});
```
#系统设置
android系统设置
```js
/**
 *systemsetting为android的接口名称
 * params 参数传空即可
*/
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
/**
 *notedetail为android的接口名称
 *@param postid参数传帖子id
*/
window.local_obj.startPage('notedetail', postid, '');
```
ios打开贴子详情页
```js
/**
 *notedetail为ios的接口名称
 * postid参数传帖子id
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('notedetail', {
         'postid': params
    });
});
```
#打开好货详情页
android打开好货详情页
```js
/**
 *goodsdetail为android的接口名称
 * goodid参数传好货id
*/
window.local_obj.startPage('goodsdetail',goodid, '');
```
ios打开好货详情页
```js
/**
 *fondgoodsdetail为ios的接口名称
 *postid参数的值传好货id
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('fondgoodsdetail', {
        'postid': postid
    });
});
```
#打开圈子详情页
android打开圈子详情页
```js
/**
 *circledetail为android的接口名称
 *circleid参数传圈子id
*/
window.local_obj.startPage('circledetail', circleid, '');
```
ios打开圈子详情页
```js
/**
 *circleDetail为ios的接口名称
 *circleid参数传圈子id
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('circleDetail', {
        'postid': circleid
    });
});
```
#打开圈子中写帖子页面
android打开圈子中写帖子页面
```js
/**
 *writenote为android的接口名称
 *circleid参数传圈子id
*/
 window.local_obj.startPage('writenote', circleid, '');
```
ios打开圈子中写帖子页面
```js
/**
 *sentNote为ios的接口名称
 *circleid参数名的值传圈子id
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('sentNote', {
        'circleid': circleid
    });
});
```
#打开对话页
android打开对话页
```js
/**
 *sendpersonalmessage为android的接口名称
 *userid参数传用户id
*/
 window.local_obj.startPage('sendpersonalmessage', userid, '');
```
ios打开私信页
```js
/**
 *openMessageChatView为ios的接口名称
 *userid参数传用户id
*/
connectWebViewJavascriptBridge(function (bridge) {
    bridge.callHandler('openMessageChatView', {
        'userid': userid
    });
});
```
#设置分享信息接口
android设置分享信息
```js
/**
*shareContent分享接口
* share_title  分享的标题
* share_content  分享的的内容
* imgUrl    图片url
* share_url  目标url
* isShow 是否显示分享弹窗, "true" 为显示， "false" 为不显示
*/
window.local_obj.shareContent(share_title,share_content, imgUrl,share_url, "false");
```
ios设置分享信息---无
#触发分享接口
android触发分享接口
```js
/**
*shareContent分享接口
* share_title  分享的标题
* share_content  分享的的内容
* imgUrl    图片url
* share_url  目标url
* isShow 是否显示分享弹窗, "true" 为显示， "false" 为不显示
*/
window.local_obj.shareContent(share_title,share_content, imgUrl,share_url, "true");
```
ios触发分享接口
```js
/*
*share_native为ios的接口名称
*sharedata参数名，shareData的值传分享信息的对象信息
*/
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
#调用示例
打开webview方法 ,  
关闭webview方法 , 
设置头像,
系统设置,
打开贴子详情页,
打开好货详情页,
打开圈子详情页,
打开圈子中写帖子页面,
打开私信页,
引入interactive.js用以下方法调用
```js
/*
*bind-app传入的值为的接口名称
*data-href传入的值为需要传的参数值,比如：地址、圈子或帖子对应的id值
*/
<a href="javascript:;" bind-app="webview" data-href="url"></a>
```
分享用以下方式调用
```js
//先把信息埋到页面中如下
<meta name="app_share_title" content="任性一周花费不愁，30000元旅游基金等你来拿！" />
<meta name="app_share_description" content="原来，晒图就能免费玩~" />
<meta name="app_share_url" content="http://sns.pro.lamahui.com/active/national?postid={{ Input::get('postid') }}" />
<meta name="app_share_image" content="" />
/*
*点击按钮显示分享的触发事件
*/
  $('#sharebtn').on('click', function () {
      cat.triggerShare();
  });
```
