

# 爱奇艺自动签到
功能：
1. 获取签到最新代码
2. 替换参数值
3. 签到并发送通知
# 使用方式
1. 打开爱奇艺官网 获取你的authcookie  获取方式 [文字教程](https://www.jianshu.com/p/b3759d78392b) ) authcookie有效期一般三个月
2. 右上角fork本仓库
3. 点击Settings -> Secrets -> 点击绿色按钮 (如无绿色按钮说明已激活。直接到第四步。)
4. 新增 new secret  参数名IQIYI_COOKIE 值是你刚才获取的authcookie
5. 任意修改仓库内任意文件或点击右上角 Star 即可触发。

**本项目需要设置的 Secrets:**

| 名称     | 内容           |   类型     |  说明|
| -------- | ------------- |  ------ | ----- |
| IQIYI_COOKIE  | 爱奇艺authcookie   | 必写参数 |

##### 推送通知环境变量(目前提供`微信server酱`、`pushplus(推送加)`、`iOS Bark APP`、`telegram机器人`、`钉钉机器人`、`企业微信机器人`、`iGot`等通知方式)

| Name                    |   归属   | 属性   | 说明                                                         |
| :---------------------: | :----------: | --------- | ------------------------------------------------------------ |
| `SEND_KEY`              |   推送开关        | 非必须 | 推送开关设置如设置该参数 仅在Cookie失效时推送,不设置则默认全部推送无论是否失败|
| `PUSH_KEY`              |   微信server酱推送   | 非必须 | server酱的微信通知[更新公告](https://sc.ftqq.com/9.version) |
| `BARK_PUSH`             |   [BARK推送](https://apps.apple.com/us/app/bark-customed-notifications/id1403753865)   | 非必须 | IOS用户下载BARK这个APP,填写内容是app提供的`设备码`，例如：https://api.day.app/123 ，那么此处的设备码就是`123`（注：支持自建填完整链接即可） |
| `BARK_SOUND`            |   [BARK推送](https://apps.apple.com/us/app/bark-customed-notifications/id1403753865)   | 非必须 | bark推送声音设置，例如`choo`,具体值请在`bark`-`推送铃声`-`查看所有铃声` |
| `TG_BOT_TOKEN`          |   telegram推送   | 非必须 | tg推送(需设备可连接外网),`TG_BOT_TOKEN`和`TG_USER_ID`两者必需,填写自己申请[@BotFather](https://t.me/BotFather)的Token,如`10xxx4:AAFcqxxxxgER5uw` |
| `TG_USER_ID`            |   telegram推送   | 非必须 | tg推送(需设备可连接外网),`TG_BOT_TOKEN`和`TG_USER_ID`两者必需,填写[@getuseridbot](https://t.me/getuseridbot)中获取到的纯数字ID |
| `DD_BOT_TOKEN`          |   钉钉推送   | 非必须 | 钉钉推送(`DD_BOT_TOKEN`和`DD_BOT_SECRET`两者必需)[官方文档](https://ding-doc.dingtalk.com/doc#/serverapi2/qf2nxq) ,只需`https://oapi.dingtalk.com/robot/send?access_token=XXX` 等于`=`符号后面的XXX即可 |
| `DD_BOT_SECRET`         |   钉钉推送   | 非必须 | (`DD_BOT_TOKEN`和`DD_BOT_SECRET`两者必需) ,密钥，机器人安全设置页面，加签一栏下面显示的SEC开头的`SECXXXXXXXXXX`等字符 , 注:钉钉机器人安全设置只需勾选`加签`即可，其他选项不要勾选 |
| `QYWX_KEY`              |   企业微信机器人推送     | 非必须 | 密钥，企业微信推送 webhook 后面的 key [详见官方说明文档](https://work.weixin.qq.com/api/doc/90000/90136/91770) |
| `QYWX_AM`               |   企业微信应用推送      | 非必须 | 依次填入 企业id,secret,@all(或者成员id),AgentID,图片id [详见官方说明文档](https://work.weixin.qq.com/api/doc/90000/90135/90236) [详见获取教程文档](https://note.youdao.com/ynoteshare1/index.html?id=351e08a72378206f9dd64d2281e9b83b) |
| `IGOT_PUSH_KEY`         |   iGot推送   | 非必须 | iGot聚合推送，支持多方式推送，确保消息可达。 [参考文档](https://wahao.github.io/Bark-MP-helper ) |
| `PUSH_PLUS_TOKEN`       |   pushplus推送  | 非必须 | 微信扫码登录后一对一推送或一对多推送下面的token(您的Token) [官方网站](https://www.pushplus.plus/)                     |
| `PUSH_PLUS_USER`        |   pushplus推送  | 非必须 | 一对多推送的“群组编码”（一对多推送下面->您的群组(如无则新建)->群组编码）注:(1、需订阅者扫描二维码 2、如果您是创建群组所属人，也需点击“查看二维码”扫描绑定，否则不能接受群组消息推送)，只填`PUSH_PLUS_TOKEN`默认为一对一推送                    |
| `TG_PROXY_HOST`         |  Telegram 代理的 IP  | 非必须 | 代理类型为 http。例子：http代理 http://127.0.0.1:1080 则填写 127.0.0.1 |
| `TG_PROXY_PORT`         |  Telegram 代理的端口  | 非必须 | 例子：http代理 http://127.0.0.1:1080 则填写 1080 |

可使用Star触发，点击自己仓库右上角Star即可激活，如是Unstar状态需要点击两次即可。
