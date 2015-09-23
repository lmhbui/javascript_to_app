#JS和API交互接口

#列表类
## 搜全部贴子
```
//需要传的参数：
{
    'method': 'search', //方法名
    'params[keywords]': '关键词', //关键词
    'params[type]': 1, //搜索类型
    'params[page_no]': 1, //第几页
    'params[page_size]': 10 //每页多少条数据
}
```

```
//返回结果
{
    "code": "0",
    "msg": "\u6210\u529f",
    "data": {
        "list": [{
            "title": "\u6211\u5fc5\u987b\u51fa\u6765\u8bf4\u8bf4\u4e86\uff0c\u771f\u662f\u9189...",
            "has_image": 0,
            "create_at": "\u521a\u521a",
            "comment_list": 0,
            "nickname": "\u674e\u5c0f\u5c0f\u82cf",
            "user_image": "http:\/\/img.test.lamahui.com\/\/static\/images\/2015\/09\/18\/dimage_2_40494.jpg",
            "is_top": 0,
            "post_id": 110338,
            "is_essence": 0,
            "content": "content",
            "tags": {
                "816": "\u788e\u788e\u5ff5",
                "818": "\u5bb6\u957f\u91cc\u77ed",
                "820": "\u65e0\u8bdd\u4e0d\u8c08"
            }
        }],
        "total": 11880, //总条数
        "has": 1 //是否有一下页
    }
}
```






#指令类
