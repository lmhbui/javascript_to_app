
#社区与app交互接口
- [打开一个webview调用](#打开webview方法)     
- [返回/退出当前页调用](#关闭webview方法)     
- [设置头像调用](#设置头像) 
- [系统设置调用](#系统设置) 
- [打开贴子详情页调用](#打开贴子详情页) 
- [打开好货详情页调用](#打开好货详情页) 
- [打开圈子详情页调用](#打开圈子详情页) 
- [打开圈子中写帖子页面调用](#打开圈子中写帖子页面) 
- [打开私信页调用](#打开私信页) 
- [分享调用](#分享调用) 

#打开webview方法
```js
<a href="javascript:;"  bind-app="webview" data-href="/user/editnickname?showtitle=false">打开webview方法</a>
```
#关闭webview方法
```js
<a href="javascript:;" bind-app="exitwebview">关闭webview方法</a>
```
#设置头像
```js
<a href="javascript:;" data-href="" bind-app="setheadpicture">设置头像</a>
```
#系统设置
```js
<a href="javascript:;" bind-app="systemsetting" data-href="">系统设置</a>
```
#打开贴子详情页
```js
<a href="javascript:;" bind-app="notedetail" data-href="<%= post_id %>" >打开贴子详情页</a>
```
#打开好货详情页
```js
<a href="javascript:;" bind-app="goodsdetail" data-href="<%= goodid %>" >好货详情页</a>
```
#打开圈子详情页
```js
<a href="javascript:;" bind-app="circledetail" data-href="<%= circleid %>" >圈子详情页</a>
```
#打开圈子中写帖子页面
```js
<a href="javascript:;" bind-app="writenote" data-href="<%= circleid %>">写帖子页面</a>
```
#打开私信页
```js
<a href="javascript:;" bind-app="sendmessage" data-href="<%= userid %>">打开私信页</a>
```
#分享调用
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
/*
*如果不点击只会把分享信息发送到安卓的接口,ios未有接口
*/
```
