# Market News (每日 AI 新闻中转站)

每日 AI 自动总结与聚合的市场新闻数据中转仓库。

## 目录结构说明

```text
market-news/
├── data/
│   ├── latest.json         # 最新一期的聚合新闻摘要与核心要点
│   └── daily/              # 历史归档数据 (按日期命名，如 YYYY-MM-DD.json)
├── scripts/                # 新闻抓取、AI 总结、格式化处理与自动化同步脚本
├── .gitignore              # Git 忽略配置
└── README.md               # 项目说明文档
```

## 数据格式规范 (JSON 示例)

`data/latest.json` 及 `data/daily/YYYY-MM-DD.json` 标准格式：

```json
{
  "updated_at": "2026-09-27T10:30:00+08:00",
  "date": "2026-09-27",
  "summary": "今日全球与 A 股核心市场动态概述...",
  "highlights": [
    "重点要闻 1",
    "重点要闻 2"
  ],
  "categories": [
    {
      "name": "宏观要闻",
      "items": [
        {
          "title": "新闻标题",
          "content": "核心内容摘要",
          "source": "cls / wscn / other",
          "published_at": "2026-09-27T09:15:00+08:00",
          "tags": ["宏观", "政策"]
        }
      ]
    }
  ]
}
```

## 自动化同步

本仓库作为数据中转中心，可通过外部定时任务（如 GitHub Actions、本地 Cron 或后端自动化流水线）定期更新并推送到远程仓库供客户端（如主页、看板等）消费。
