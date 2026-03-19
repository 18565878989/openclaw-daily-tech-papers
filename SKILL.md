---
name: daily-tech-papers
description: 每日全球技术论文推送。从 arXiv 获取最新的 AI/ML/NLP/CV 论文，定时推送给用户。当用户想要获取最新技术论文、设置论文推送、或需要了解 AI/ML 领域最新研究时使用此技能。
---

# 每日技术论文推送技能

此技能用于获取并推送全球最新的 AI/ML/NLP/CV 技术论文。

## 核心功能

1. **抓取论文** - 从 arXiv RSS 获取 cs.AI、cs.LG、cs.CL、cs.CV 四个分类的最新论文
2. **格式化消息** - 将论文整理为易读的飞书消息格式
3. **定时推送** - 每天早上 9:00 自动推送

## 论文分类标签

| arXiv 分类 | 显示标签 | 说明 |
|-----------|---------|------|
| cs.AI | 🤖 AI | 人工智能 |
| cs.LG | 🧠 机器学习 | Machine Learning |
| cs.CL | 💬 NLP | 自然语言处理 |
| cs.CV | 👁️ 计算机视觉 | Computer Vision |

## 消息格式

```
📚 全球最新技术论文推送
📅 YYYY年MM月DD日
🔬 共推送 N 篇精选论文

━━━━━━━━━━━━━━━━━━━━

1. 论文标题（截断70字符）
👤 作者1, 作者2, 作者3
📅 YYYY-MM-DD | 🤖 AI
🔗 https://arxiv.org/abs/XXXX.XXXXX

2. ...

━━━━━━━━━━━━━━━━━━━━
📌 来源: arXiv.org
💡 想深入了解某篇论文？直接问我！
```

## 使用方式

### 手动触发推送
```
运行脚本：/usr/bin/python3 ~/.openclaw/workspace/scripts/daily_tech_papers.py
```

### 定时任务设置
- **Cron 表达式**: `0 9 * * *`
- **时区**: Asia/Shanghai
- **Session**: isolated
- **推送渠道**: feishu

## 脚本位置

`~/.openclaw/workspace/scripts/daily_tech_papers.py`

## 依赖

- Python 3
- 标准库: urllib, xml.etree.ElementTree, email.utils, re, datetime, time

## 注意事项

1. arXiv RSS 只返回最近更新，不包含历史论文
2. 论文按发布时间排序，最多推送 15 篇
3. 作者只显示前 3 位
4. 标题截断至 70 字符以保持消息简洁
