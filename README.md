# javascript和app交互指南

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
