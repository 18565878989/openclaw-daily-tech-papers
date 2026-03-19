---
name: daily-tech-papers
description: 每日全球技术论文推送。从 arXiv 获取最新的 AI/ML/NLP/CV 论文，定时推送给用户。当用户想要获取最新技术论文、设置论文推送、或需要了解 AI/ML 领域最新研究时使用此技能。
---

# Daily Tech Papers - 每日技术论文推送

让 AI 助手每天自动推送全球最新的 AI/ML/NLP/CV 技术论文。

## 功能特点

- 📚 从 arXiv 获取最新论文
- 🤖 支持 AI、机器学习、NLP、计算机视觉 4 个分类
- ⏰ 支持定时自动推送
- 📱 格式化输出，适配飞书/微信等平台

## 安装

### 方法 1: 使用 clawhub CLI（推荐）

```bash
clawhub install 18565878989/openclaw-daily-tech-papers
```

### 方法 2: 手动安装

1. 克隆仓库：
```bash
git clone https://github.com/18565878989/openclaw-daily-tech-papers.git
```

2. 复制技能文件到 OpenClaw：
```bash
cp -r daily-tech-papers ~/.openclaw/workspace/skills/
```

3. 复制脚本到 scripts 目录：
```bash
mkdir -p ~/.openclaw/workspace/scripts
cp scripts/daily_tech_papers.py ~/.openclaw/workspace/scripts/
```

## 使用方法

### 手动触发

在 OpenClaw 中直接说：
- 「推送今日论文」
- 「最新技术论文」
- 「AI 论文推送」

### 定时推送设置

在 OpenClaw 中设置 cron 任务：

```
每天早上 9:00 自动推送
```

示例 cron 配置：
- 时间：`0 9 * * *` (Asia/Shanghai)
- Session: isolated
- 推送渠道: feishu

## 论文分类

| 分类 | 标签 | 说明 |
|------|------|------|
| cs.AI | 🤖 AI | 人工智能 |
| cs.LG | 🧠 机器学习 | Machine Learning |
| cs.CL | 💬 NLP | 自然语言处理 |
| cs.CV | 👁️ 计算机视觉 | Computer Vision |

## 推送效果示例

```
📚 全球最新技术论文推送
📅 2026年03月19日
🔬 共推送 15 篇精选论文

━━━━━━━━━━━━━━━━━━━━

1. Transformers are Bayesian Networks
👤 Gregory Coppola
📅 2026-03-19 | 🤖 AI
🔗 https://arxiv.org/abs/2603.17063

2. AI Scientist via Synthetic Task Scaling
👤 Ziyang Cai, Harkirat Behl
📅 2026-03-19 | 🤖 AI
🔗 https://arxiv.org/abs/2603.17216

...

━━━━━━━━━━━━━━━━━━━━
📌 来源: arXiv.org
💡 想深入了解某篇论文？直接问我！
```

## 脚本使用

```bash
# 直接运行
python3 scripts/daily_tech_papers.py

# JSON 格式输出（用于程序调用）
python3 scripts/daily_tech_papers.py --feishu
```

## 数据来源

- **arXiv.org** - 全球最大的预印本学术论文库
- RSS Feed: `http://export.arxiv.org/rss/{category}`

## 依赖

- Python 3.7+
- 标准库（无需额外安装）：
  - `urllib`
  - `xml.etree.ElementTree`
  - `email.utils`
  - `re`
  - `datetime`
  - `time`

## 项目结构

```
daily-tech-papers/
├── SKILL.md           # 本文件 - 技能说明
└── README.md          # 安装和使用说明

scripts/
└── daily_tech_papers.py  # 论文抓取脚本
```

## License

MIT License

## 作者

- GitHub: [18565878989](https://github.com/18565878989)
- OpenClaw Directory: [OpenClaw Directory](https://openclawdirectory.co.uk/)

## 相关项目

- [OpenClaw](https://openclaw.ai/) - AI 个人助手框架
- [CLI-Anything](https://github.com/HKUDS/CLI-Anything) - 让任何软件都能被 AI 控制
- [Awesome Claude Skills](https://github.com/ComposioHQ/awesome-claude-skills) - Claude 技能精选列表
