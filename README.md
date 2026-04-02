<b>Aiven免费数据库保活工具</b>
# auto-sent-aivenfreeMysql-mrkdb
https://aiven.io 提供免费1c1g的免费mysql数据库，解决24小时无动作会被poweroff的保活方案（含TG通知）<br><br>
<b>部署和使用说明：</b>fork本项目，变量中添加7个变量，分别为AVN_DB_HOST、AVN_DB_NAME、AVN_DB_PASSWORD、AVN_DB_PORT、AVN_DB_USER、TELEGRAM_BOT_TOKEN、TELEGRAM_CHAT_ID，其中前5个变量值在aiven里面可以找得到，后面2个tg里面获取（创建 Bot：在 Telegram 中搜索 @BotFather，创建新 Bot 并获取 Token，获取 Chat ID：搜索 @userinfobot，发送任意消息获取你的 Chat ID），首次在Action中运行一次'Database Keep-Alive-TG Ping and Log'，后续将定时每隔47分钟执行一次。<br><br>
<b>保活原理：</b>aiven数据库服务器默认24h无数据变化则自动关机，通过GitHub实现定时每47分钟检测一次数据库服务器是否在线，如果在线把检测数据写入数据库，实现数据库内容有变化，从而使数据库服务器的关机倒计时重置为24h。<br><br>
<b>workflow执行内容：</b>保活方案默认每47分钟ping一次数据库并将结果写入到数据库中的bh表内（数据有变化，数据库服务器的关机倒计时重置为24h），失败则每次都发tg消息，首次运行成功or失败后首次成功发送tg消息，连续成功则不发送消息。<br><br><br><br>
作者：FormID<br><br>
执笔：DeepSeek<br><br>
发布：GitHub<br><br>
2026.04.02调试完成<br><br>
感谢Aiven提供免费MySQL数据库，感谢GitHub和Telegram提供免费平台，感谢DeepSeek不懈努力。本项目代码可见、变量调用安全、用法通用，建议先发给AI确认没夹带私货，再使用。

