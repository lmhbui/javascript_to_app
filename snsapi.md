#JS和API交互接口

#列表类
## 搜全部贴子
```
//需要传的参数：
{
    "method": "search", //方法名
    "params[keywords]": "关键词", //关键词
    "params[type]": 2, //搜索类型（备注：type为1时是搜索本圈的帖子）
    "params[page_no]": 1, //第几页
    "params[page_size]": 10 //每页多少条数据
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
##搜用户
```
//需要传的参数
{
  "method":"search_user",//方法名
  "params[keywords]":"关键词",//关键词
  "params[page_no]":1,  //第几页
  "params[page_size]":10 //每页多少条数据

}

//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "list": [
            {
                "id": 100041343,
                "avatar_image_url": "http://img.test.lamahui.com//static/images/2015/09/18/dimage_3_804.jpg",
                "nickname": "海之言ωs952",
                "baby_birthday_at": "备孕中",
                "level": "",
                "is_concern": 0
            }   
        ],
        "total": 2,
        "has": 0
    }
}

```

##搜圈子
```
//需要传的参数
{
  "method":"get_circle_list",//方法名
  "params[keywords]":"关键词",//关键词
  "params[page_no]":1,  //第几页
  "params[page_size]":10 //每页多少条数据

}

//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "total": 1,
        "circle_list": [
            {
                "circle_id": 190,
                "circle_name": "宝宝风采",
                "description": "赶紧把你家宝宝的照片晒出来吧！",
                "check_url": "http://sns.pro.lamahui.com/circle/channel?circle_id=190",
                "circle_image": "http://img.pro.lamahui.com/static/images/2015/09/17/5496ebab048976565449d74db4c351579033.jpg",
                "in_circle": 0,
                "faction_members": []
            }
        ],
        "has": 0
    }
}
```

##圈子列表页
```
//需要传的参数
{
  "method":"get_circle_list",//方法名
  "app_key":"14327",
  "params[category_id]":0,//分类ID 
  "params[page_no]":1, //第几页  
  "params[page_size]":10 //每页多少条数据
  "params[keywords]":" ",//关键词
}

//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "total": 7,
        "circle_list": [
            {
                "circle_id": 190,
                "circle_name": "宝宝风采",
                "description": "赶紧把你家宝宝的照片晒出来吧！",
                "check_url": "http://sns.pro.lamahui.com/circle/channel?circle_id=190",
                "circle_image": "http://img.pro.lamahui.com/static/images/2015/09/17/5496ebab048976565449d74db4c351579033.jpg",
                "in_circle": 0,
                "faction_members": []
            }     
        ],
        "has": 0
    }
}
```

##个人中心页面
```
//需要传的参数
{
  "method":"view_user_page",//方法名
  "app_key":"14327",
  "params[person_id]":"用户ID" //用户ID
}

//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "user_infor": {
            "avatar_image_url": "http://img09.lamahui.com/static/images/2015/09/17/72dd1f4698a7560d215cfcb97f8023230C92F0CFFE7314BB05FD69753D88427D.jpg?imageView2/1/w/100/h/100/q/90/interlace/1",
            "backgroud_image_url": "http://img09.lamahui.com//kindeditor/image/2015/08/13/a3677091d1865d2e941ed583b41486fa5939.jpg",
            "province_name": "杭州市",
            "nickname": "哈哈",
            "baby_birthday_at": "备孕中",
            "follow_id": "224",
            "level": "LV.1",
            "user_index_url": "http://sns.pro.lamahui.com/user/index?person_id=224&title=他的个人中心&user_id=0"
        },
        "banner_img": "http://img09.lamahui.com//kindeditor/image/2015/08/13/a3677091d1865d2e941ed583b41486fa5939.jpg",
        "interaction_num": {
            "circle": 0,
            "focus": 0,
            "fans": 0,
            "collection": 0
        },
        "create_post": 0,
        "reply_post": 0,
        "fans_been": "",
        "is_own": true
    }
}
```

##我/他 的圈子列表页
```
//需要传的参数
{
  "method":"get_circle_list",//方法名
  "app_key":"14327",
  "params[person_id]":"用户ID" ,//用户ID
  "params[page_no]":1,//第几页
  "params[page_size]":10//每页多少条数据
  "params[keywords]":""//关键词（可选）
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "total": 2,
        "circle_list": [
            {
                "circle_id": 190,
                "circle_name": "宝宝风采",
                "description": "赶紧把你家宝宝的照片晒出来吧！",
                "check_url": "http://sns.pro.lamahui.com/circle/channel?circle_id=190",
                "circle_image": "http://img.pro.lamahui.com/static/images/2015/09/17/5496ebab048976565449d74db4c351579033.jpg",
                "in_circle": 1,
                "faction_members": []
            }           
        ],
        "has": 0
    }
}
```


#指令类
