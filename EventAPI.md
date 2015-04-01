# 介绍 #
同城活动API的方法暂时只有5个，之后会加上搜索，参加和感兴趣等API
| get | 获取活动 |
|:----|:-------------|
| getForUser | 获取用户的所有活动 |
| add | 创建新活动 |
| update | 更新活动 |
| remove | 删除活动 |

# 示例 #
```
// 初始化service
var service = $.douban({ key: apiKey, secret: apiSecret });
service.login({ key: accessKey, secret: accessSecret });

// 获取某活动信息
var event = service.event.get('10288075');

// 弹出活动名 蜷川実花个展
alert(event.title);
```
更多示例可以参考测试 [tests.js](http://github.com/wuyuntao/jquery-douban/tree/master/tests%2Ftests.js) 的 "test event api"部分

# 同城活动类 #
上面的示例中，API返回的是一个同城活动类（Event）。它定义了豆瓣同城活动的信息，可以通过下面的命令创建，其中json为豆瓣返回的gdata json feed
```
var event = $.douban('event', json);
```
Event类有下面这些属性
| all | 属性列表 |
|:----|:-------------|
| id | 活动ID |
| title | 活动标题 |
| owner | 活动发起者，User object |
| summary | 活动摘要 |
| content | 活动全文 |
| startTime | 活动开始时间 |
| endTime | 活动结束时间 |
| url | 活动URL |
| imageUrl | 活动封面URL |
| category | 活动类别 |
| location | 活动城市 |
| address | 活动地点 |
| isInviteOnly | 是否只允许受邀请者参加 |
| isInviteEnabled | 是否能够邀请参加 |
| participants | 活动参与者数量 |
| wishers | 活动感兴趣者数量 |