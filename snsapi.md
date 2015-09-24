#JS和API交互接口
- [搜全部帖子](#搜全部帖子)     
- [搜用户](#搜用户)     
- [搜圈子](#搜圈子) 
- [圈子列表页](#圈子列表页) 
- [个人中心页面](#个人中心页面) 
- [我(他)的圈子列表页](#我他的圈子列表页) 
- [我(他)关注的圈子及我（他）的辣粉页](#我他关注的圈子及我他的辣粉页) 
- [我(他)收藏的帖子](#我他收藏的帖子) 
- [我(他) 发表的帖子](#我他发表的帖子) 
- [我(他)回复的帖子](#我他回复的帖子) 
- [看懂B超单](#看懂b超单) 
- [疫苗时间表](#疫苗时间表) 
- [产检时间表](#产检时间表) 
- [设置首页](#设置首页) 
- [建议反馈](#建议反馈) 
- [修改昵称](#修改昵称) 
- [修改密码](#修改密码) 
- [标记已完成的产检](#标记已完成的产检) 
- [取消已标记的产检](#取消已标记的产检) 
- [标记完成一次疫苗](#标记完成一次疫苗) 
- [取消已标记的疫苗](#取消已标记的疫苗) 




#搜索
# 搜全部贴子
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
            "user_image": "a.jpg",
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
#搜用户
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
                "avatar_image_url": "a.jpg",
                "nickname": "海之言ωs952",
                "baby_birthday_at": "备孕中",
                "level": "",
                "is_concern": 0//是否关注（0：未关注，1：已关注）
            }   
        ],
        "total": 1,//总条数
        "has": 0//是否有下一页
    }
}

```

#搜圈子
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
        "total": 1,//总条数
        "circle_list": [
            {
                "circle_id": 190,
                "circle_name": "宝宝风采",
                "description": "赶紧把你家宝宝的照片晒出来吧！",
                "check_url": "http://sns.pro.com/circle/channel?circle_id=190",
                "circle_image": "a.jpg",
                "in_circle": 0,//是否加入圈子（1：已加圈 0：未加圈）
                "faction_members": []
            }
        ],
        "has": 0//是否有下一页
    }
}
```
#列表页
#圈子列表页
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
        "total": 7,//总条数
        "circle_list": [
            {
                "circle_id": 190,
                "circle_name": "宝宝风采",
                "description": "赶紧把你家宝宝的照片晒出来吧！",
                "check_url": "http://sns.pro.com/circle/channel?circle_id=190",
                "circle_image": "a.jpg",
                "in_circle": 0,
                "faction_members": []
            }     
        ],
        "has": 0//是否有下一页
    }
}
```
#我(他)的圈子列表页
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
                "check_url": "http://sns.pro.com/circle/channel?circle_id=190",
                "circle_image": "a.jpg",
                "in_circle": 1,
                "faction_members": []
            }           
        ],
        "has": 0//是否有下一页
    }
}
```

#个人中心页面
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
            "avatar_image_url": "a.jpg", //头像图片地址
            "backgroud_image_url": "a.jpg",//个人中心背景图
            "province_name": "杭州市",
            "nickname": "哈哈",
            "baby_birthday_at": "备孕中",
            "follow_id": "224",
            "level": "LV.1",
            "user_index_url": "http://sns.pro.com/user/index?person_id=224&title=他的个人中心&user_id=0"
        },
        "banner_img": "a.jpg",
        "interaction_num": {
            "circle": 0,//圈子
            "focus": 0,//关注
            "fans": 0,//辣粉
            "collection": 0//收藏
        },
        "create_post": 0,//发表的帖子
        "reply_post": 0,//回复的帖子
        "fans_been": "",
        "is_own": true//是否是自己的个人中心页 （false:他人的个人中心）
    }
}
```


#我(他)关注的人及我（他）的辣粉页
```
//需要传的参数
{
  "method":"get_fans_list",//方法名
  "app_key":"14327",
  "params[person_id]":"用户ID" ,//用户ID
  "params[type_id]":"2",//类型
  "params[page_no]":1,//第几页
  "params[page_size]":10//每页多少条数据
  "params[keywords]":""//关键词（可选）
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "user_list": [
            {
                "area": "琼中黎族苗族自治县",
                "baby_infor": "女宝4岁11月",
                "is_concern": 1,
                "nickname": "馨妈爱宝宝",
                "user_image": "a.jpg",
                "user_level_id": "LV.1",
                "user_id": 100034970
            }
        ]
    }
}
```

#我(他)收藏的帖子
```
//需要传的参数
{
  "method":"get_post_list",//方法名
  "params[circle_id]":"圈子id",//圈子id
  "params[type_id]":0,
  "params[page_no]":1,//第几页
  "params[page_size]":10,//每页多少条数据
  "params[keywords]":" ",//关键词（可选）
  "params[tag_id]":" ",//标题（可选）
  "params[sponsor_id]":"发帖者ID",//发帖者ID
  "params[participator_id]":"参与者id",//参与者id
  "params[post_ids]":"贴子ids",//贴子ids
  "params[collector_id]":"收藏者id"//收藏者id
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "has": 0,//是否有下一页
        "total": 1,//总条数
        "list": [
            {
                "area": "杭州",
                "post_id": 99066,
                "is_best": 1,//是否是精选帖子
                "post_title": "有哪些让你相见恨晚的化妆品和护肤品？",
                "post_content": "准备换一批化妆品求重点推荐眼线笔",
                "support_count": 129,
                "reply_count": 71,
                "is_support": 0,//是否对帖子点过赞
                "user_profile": {
                    "avatar_image_url": "a.jpg",
                    "backgroud_image_url": "a.jpg",
                    "province_name": "张掖市",
                    "nickname": "以命爱你们",
                    "baby_birthday_at": "女宝1岁15天",
                    "follow_id": 100223970,
                    "level": "LV.1",
                    "user_index_url":"http://sns.pro.com/user/index?person_id=100223970&title=他的个人中心&user_id=224"
                },
                "post_type": 1,//是否是帖子（2:是好货）
                "share_url": "http://sns.pro.com/post/share?post_id=99066&device_id=",
                "share_title": "有哪些让你相见恨晚的化妆品和护肤品？",
                "share_content": "准备换一批化妆品求重点推荐眼线笔/液睫毛…",
                "share_image": "a.png",
                "is_concern": 0,
                "image_urls": [],
                "image_big_urls": [],
                "create_at": "22小时前"
            }
        ]
    }
}
```
#我(他)发表的帖子
```
//需要传的参数
{

  "method":"get_post_list",//方法名
  "params[circle_id]":"圈子id",//圈子id
  "params[type_id]":0,
  "params[page_no]":1,//第几页
  "params[page_size]":10,//每页多少条数据
  "params[keywords]":" ",//关键词（可选）
  "params[tag_id]":" ",//标题（可选）
  "params[sponsor_id]":"发帖者ID",//发帖者ID
  "params[participator_id]":"参与者id",//参与者id
  "params[post_ids]":"贴子ids",//贴子ids
  "params[collector_id]":"收藏者id"//收藏者id
  
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "has": 0,//是否有下一页
        "total": 1,//总条数
        "list": [
            {
                "area": "杭州市",
                "post_id": 111268,
                "is_best": 0,//是否是精选帖子
                "post_title": "关于宝宝的健康问题",
                "post_content": "宝贝的东西一定要用好的有质量的不要贪图小便宜",
                "support_count": 0,
                "reply_count": 0,
                "is_support": 0,
                "user_profile": {
                    "avatar_image_url": "a.jpg",
                    "backgroud_image_url": "a.jpg",
                    "province_name": "杭州市",
                    "nickname": "小小",
                    "baby_birthday_at": "备孕中",
                    "follow_id": 224,
                    "level": "LV.1",
                    "user_index_url": "http://sns.pro.com/user/index?person_id=224&title=我的圈&user_id=224"
                },
                "post_type": 1,//是否是帖子（2:是好货）
                "share_url": "http://sns.pro.com/post/share?post_id=111268&device_id=",
                "share_title": "关于宝宝的健康问题",
                "share_content": "宝贝的东西一定要用好的有质量的不要贪图小…",
                "share_image": "logo.png",
                "is_concern": 0,
                "image_urls": [],
                "image_big_urls": [],
                "create_at": "刚刚"
            }
        ]
    }
}
```
#我(他)回复的帖子
```
//需要传的参数
{

  "method":"get_post_list",//方法名
  "params[circle_id]":"圈子id",//圈子id
  "params[type_id]":0,
  "params[page_no]":1,//第几页
  "params[page_size]":10,//每页多少条数据
  "params[keywords]":" ",//关键词（可选）
  "params[tag_id]":" ",//标题（可选）
  "params[sponsor_id]":"发帖者ID",//发帖者ID
  "params[participator_id]":"参与者id",//参与者id
  "params[post_ids]":"贴子ids",//贴子ids
  "params[collector_id]":"收藏者id"//收藏者id
  
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "has": 0,//是否有下一页
        "total": 1,//总条数
        "list": [
            {
                "area": "杭州",
                "post_id": 99066,
                "is_best": 1,//是否是精选帖子
                "post_title": "有哪些让你相见恨晚的化妆品和护肤品？",
                "post_content": "准备换一批化妆品求重点推荐眼线笔/液睫毛膏腮红",
                "support_count": 131,
                "reply_count": 73,
                "is_support": 0,//是否点赞
                "user_profile": {
                    "avatar_image_url": "a.jpg",
                    "backgroud_image_url": "1.jpg",
                    "province_name": "张掖市",
                    "nickname": "以命爱你们",
                    "baby_birthday_at": "女宝1岁15天",
                    "follow_id": 100223970,
                    "level": "LV.1",
                    "user_index_url": "http://sns.pro.com/user/index?person_id=100223970&title=他的个人中心&user_id=224"
                },
                "post_type": 1,//是否是帖子（2是好货）
                "share_url": "http://sns.pro.com/post/share?post_id=99066&device_id=",
                "share_title": "有哪些让你相见恨晚的化妆品和护肤品？",
                "share_content": "准备换一批化妆品求重点推荐眼线笔/液睫毛…",
                "share_image": "logo.png",
                "is_concern": 0,
                "image_urls": [],
                "image_big_urls": [],
                "create_at": "刚刚"
            }
        ]
    }
}
```

#发现

#看懂B超单
```
//需要传的参数
{
  "method":"get_typeB"//方法名
  "app_key":14327,
  "params[page_no]":1//第几页
  "params[page_size]":100//每页多少条数据
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "list": [
            {
                "title": "FP胎位",
                "id": 17
            },
            
            {
                "title": "FE胎芽",
                "id": 23
            },
            {
                "title": "A/B脐带血流比值",
                "id": 43
            }
        ],
        "total": 20,//总条数
        "has": 0//是否有下一页
    }
}
```
#疫苗时间表
```
//需要传的参数
{
  "method":"get_vaccine_info"//方法名
  "app_key":14327,
  "params[page_no]":1//第几页
  "params[page_size]":100//每页多少条数据
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "list": {
            "days": "",
            "list": [
                {
                    "id": 44,
                    "property": [
                        "出生当天",
                        "1",
                        "卡介苗",
                        "预防结核病",
                        "第一次",
                        "1"
                    ],
                    "time": "1",
                    "next_vaccine": 0,
                    "date": "",
                    "is_finish": 0
                }      
            ]
        },
        "total": 36,//总条数
        "has": 0,//是否有下一页
        "power": 0
    }
}
```
#产检时间表
```
//需要传的参数
{
  "method":"get_baby_care"//方法名
  "app_key":14327,
  "params[page_no]":1//第几页
  "params[page_size]":100//每页多少条数据
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "list": [
            {
                "id": 18,
                "property": [
                    "一",
                    "12周",
                    "建档、NT检查、空腹"
                ],
                "next_care": 0,
                "date": "",
                "is_overdue": 0,
                "is_check": 0
            }
        ],
        "total": 13,//总条数
        "has": 0,//是否有下一页
        "power": 0
    }
}
```
#标记已完成的产检
```
//需要传的参数
{
  "method":"for_vaccination"//方法名
  "params[tools_id]":"",//小工具id
  "params[type]":add,
  "params[care]":baby,
  "app_key":14327
}
```
#取消已标记的产检
```
//需要传的参数
  "method': 'for_vaccination',
  "params[tools_id]": id,//小工具id
  "params[type]": 'del',
  "params[care]":baby,
  "app_key": 14327
```
#标记完成一次疫苗
```
//需要传的参数
{
  "method":"for_vaccination"//方法名
  "params[tools_id]":"",//
  "params[type]":add,
  "app_key":14327
}
```
#取消已标记的疫苗
//需要传的参数
```
  "method': 'for_vaccination',//方法名
  "params[tools_id]": id,
  "params[type]": 'del',
  "app_key": 14327
```

#设置页

#设置首页
```
//需要传的参数
{
"method":"get_user_info"//方法名
"app_key":14327,  
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {
        "image_url": "1.jpg",
        "nickname": "小小",
        "city_name": "杭州市",
        "user_status": "备孕中",
        "baby_birthday": ""
    }
}
```
#修改昵称
```
//需要传的参数
{
  "method":"set_user_profile"//方法名
  "app_key":14327,
  "params[nickname]":"昵称"//输入的昵称
 
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {}
}
```
#修改密码
```
//需要传的参数
{
  "method":"reset_user_pwd"//方法名
  "params[old_pwd]":"旧密码"//旧密码
  "params[new_pwd]":"新密码"//新密码
}
```

#建议反馈
```
//需要传的参数
{
  "method":"set_feedback_in"//方法名
  "params[content]":"反馈的内容",//反馈的内容
  "params[mobile]":"手机号码" //手机号码
 
}
//返回结果
{
    "code": "0",
    "msg": "成功",
    "data": {}
}
```



#指令类
