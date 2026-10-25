# Aya-event_on_history

HoshinoBot 插件：历史上的今天。

## 指令

| 指令 | 说明 |
|---|---|
| 历史上的今天 / 看看历史 | 查询历史上的今天发生的事件 |

## 安装

1. 将 `history.py` 放入 `hoshino/modules/eventonhistory/`
2. 在 `hoshino/config/__bot__.py` 的 `MODULES_ON` 中加入 `'eventonhistory'`
3. 重启 bot

## 依赖

- pytz（其余为标准库；`requests` / `BeautifulSoup` 为遗留 import，实际未使用）

## 数据来源

百度百科公开接口 `https://baike.baidu.com/cms/home/eventsOnHistory/<月份>.json`

## 已知问题

- 在 async 处理函数中使用阻塞的 `urllib.request.urlopen`，请求期间会阻塞整个事件循环
- 未做异常处理，接口不可用时会直接抛出异常
