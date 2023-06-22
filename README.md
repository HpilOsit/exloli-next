# exloli-next

新一代的 exloli 客户端

## 特点

功能上其实没变，只是砍掉了大量没啥意义的功能，并且重新设计了数据库结构

而且代码质量从「不能看」进化到了「能看」的程度！（

## 配置文件

```toml
# 日志等级
log_level = "info,sqlx=warn,teloxide=error,exloli_next=debug"
# 下载线程的数量
# NOTE: 上传线程数量固定为 1
threads_num = 1
# 每次扫描的间隔
interval = "1h"
# 数据库文件位置
database_url = "db.sqlite"

[exhentai]
# E 站 cookie
cookie = "ipb_member_id=xxxxx; ..."
# 搜索参数
search_params = [
    ["f_cats", "577"],
    ["f_search", "female:lolicon language:Chinese"]
]
# 搜索多少本本子（注意不是页数）
# 将此处设置为 0，就不会主动上传任何本子
search_count = 10
# 翻译文件的位置
# 前往 https://github.com/EhTagTranslation/Database 下载
trans_file = "db.text.json"

[telegraph]
# telegrah 账号 token
access_token = "xxxx"
# 发布文章时使用的作者名字
author_name = "exloli"
# 发布文章时使用的作者名称
author_url = "https://t.me/exlolicon"

[telegram]
# 频道 ID，如果是私有频道，这里可以填数字 ID
channel_id = "@xxx"
# 群组 ID，因为我懒，所以这里只能填数字 ID，如果填写的 ID 不存在，则不会发送投票
# 可以用 @myidbot 来获取你的频道和群组 ID
group_id = -1001423106182
# bot ID
bot_id ="test_bot"
# bot token
token = "xxxx:xxxxxxxx"
```

## 从 exloli 迁移

直接运行即可，但是建议备份好数据库

## TODO

- 处理旧本子的投票：通过 /query 返回 OR 重新编辑频道消息添加投票 OR ？
