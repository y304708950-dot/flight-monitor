# ✈️ 机票价格监控 MVP

全网比价 · 价格追踪 · 智能提醒 · 日历视图

## 快速启动

```bash
cd ~/.openclaw/workshop/flight-monitor
python3 app.py
```

浏览器打开: http://localhost:8888

## 功能

| 功能 | 说明 |
|------|------|
| 🔍 多平台比价 | 携程、飞猪、去哪儿、天巡、航司官网 |
| 📅 日历价格图 | 5个月日历视图，一眼看出低价日 |
| 🔔 降价提醒 | 设置目标价，自动通知 |
| 📱 手机适配 | 响应式设计，手机优先 |
| 🌙 深色模式 | 自动跟随系统主题 |

## API

- `GET /api/search?origin=济南&dest=大阪&depart_date=2026-09-25` - 搜索航班
- `GET /api/calendar?origin=济南&dest=大阪&start_date=2026-09-01&months=2` - 日历价格
- `GET /api/alerts` - 查看提醒
- `POST /api/alerts?origin=济南&dest=大阪&depart_date=2026-09-25&target_price=2000` - 创建提醒
- `DELETE /api/alerts/{id}` - 删除提醒

## 数据源

当前使用模拟数据展示MVP效果。接入真实数据需要：
1. 申请 Skyscanner API (免费tier)
2. 或使用 Google Flights 网页抓取
3. 或接入 Amadeus API (有免费试用)

## 技术栈

- 后端: Python FastAPI
- 前端: 原生 HTML/CSS/JS（无框架依赖）
- 存储: JSON 文件
- 部署: 单机 uvicorn
