# 树洞 · TreeHole

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE.txt)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://skillhub.cn/skills/treehollow)
[![SkillHub](https://img.shields.io/badge/SkillHub-%E6%A0%91%E6%B4%9E-orange.svg)](https://skillhub.cn/skills/treehollow)

> A warm, non-judgmental AI listener — a reusable Claude Skill with built-in crisis detection & escalation.
> 一个温暖、不评判的 AI 倾听者 Skill——自带危机识别与转介。

## English · Overview

**TreeHole** is a reusable Claude Skill that turns any AI app into a warm, non-judgmental listener — with built-in crisis detection and escalation.

**Who it's for:** developers building emotional-companion, mental-health, education, or social apps.

**What it gives you:**

- Empathetic listening grounded in Rogers' *unconditional positive regard* and Pennebaker's *expressive writing* — not a generic chatbot prompt.
- Crisis detection & escalation for self-harm / suicide / abuse / bullying, graded red / yellow / green — **without diagnosis or treatment**.
- Tech-agnostic & configurable: no hard-coded hotlines, age thresholds, laws, or table/framework names — just fill in your own country's parameters.
- Bilingual (English/Chinese) with full guardrails: no PII collection, no third-party disclosure.

**Install:**

- One-click via [SkillHub](https://skillhub.cn/skills/treehollow), or
- `git clone https://github.com/xiaojianpingsheng/treehollow.git` and drop the folder into your AI tool's skills directory.

**Quick start:** fill the `{placeholders}` in `references/` with your local hotlines / age thresholds / laws, wire up the 5 tool contracts in `SKILL.md`, and you're done. Full integration notes: [`DEVELOPER.md`](DEVELOPER.md).

**Live demo:** https://fjtk3njxz2vu.meoo.pub

> 完整中文文档见下方 ↓ · Full documentation in Chinese below.

---

**「树洞」是一个可复用的 Claude Skill**：把「一个会好好听你说话的 AI 倾听者」打包好（提示词 + 5 个工具契约 + 危机护栏），让你（开发者）拿进自己的 App，当后台的情绪倾听者。

- 🎯 **适合谁**：正在做情感陪伴 / 心理 / 教育 / 社交类 App 的独立开发者和小团队。
- 🧭 **什么是 Skill**：Skill 是一份「给 AI 的角色说明书 + 规则 + 能力清单」，放进 AI 编程工具的 skills 目录即可被识别加载，不改你的技术栈。

---

## 在线演示

想先看看「树洞」真实聊起来是什么样？打开这个演示页（测试版）体验：

**🔗 https://fjtk3njxz2vu.meoo.pub**

> 这是树洞的一个真实使用界面；你要接入的是本仓库里的 Skill 本体（`SKILL.md` + `references/`），不是这个页面。

## 安装

**方式一 · SkillHub 一键安装（推荐）**

在 [SkillHub](https://skillhub.cn/skills/treehollow) 上搜索「树洞」或「TreeHole」，一键安装到你正在用的 AI 编程工具里。

**方式二 · 手动 / git clone**

```bash
git clone https://github.com/xiaojianpingsheng/treehollow.git
```

然后把整个 `treehollow/` 文件夹放进你所用 AI 编程工具的 skills 目录即可。

## 它解决什么问题

你想给自己的 App（情感陪伴 / 心理 / 教育 / 社交类）加一个「AI 倾听者」，但从零做会遇到三件麻烦事：

1. **提示词难写**——怎么让 AI 先接住情绪、不评判、不灌鸡汤，需要专门琢磨。
2. **危机兜底最怕出事**——面向人群（尤其青少年）的产品，一旦有人表达自伤、自杀、被侵害，处理不当要担法律责任。
3. **写死就难复用**——号码、年龄线、法规各国不同，写死了就没法给别人用。

树洞把这三件事做成**现成的、专业的、可配置的**：拿来就能用，接入时填你自己国家的参数即可。

## 核心特性

- **专业理论背书**：罗杰斯「无条件积极关注」+ 彭尼贝克「表达性书写」，跟随便写个 prompt 的陪聊拉开档次。
- **危机识别 + 转介（不诊断不治疗）**：识别自伤 / 自杀 / 被侵害 / 被霸凌四类信号，按红 / 黄 / 绿分级处置，命中即转介 + 上报。
- **技术无关、可配置**：不写死表名、框架、号码、年龄、法规，全部是参数，开发者填自己国家的即可。
- **中英双语**：技能名英文、核心规则中英对照，内容主体中文，天然适配国际路线。
- **护栏完整**：不收集可识别身份、不向第三方透露倾诉内容（危机转介除外）。

## 快速开始（3 步）

1. **放进技能目录**：把整个 `treehollow/` 文件夹放进你所用 AI 编程工具的 skills 目录，让它能被识别加载。
2. **填写配置参数**：把 `references/` 里的 `{参数名}` 占位符，替换成你所在国家/地区的转介号码、年龄阈值、法规名（详见 [`DEVELOPER.md`](DEVELOPER.md) 第 4 节）。
3. **接上 5 个工具**：把 `SKILL.md` 第 4 节的 5 个「工具契约」，接到你 App 的真实后端能力上（详见 [`DEVELOPER.md`](DEVELOPER.md) 第 5 节）。

接完后，你的 App 就多了一个会先接住情绪、且能识别危机并转介的倾听者。

## 仓库结构

```
treehollow/
├── SKILL.md                     # 主干：身份卡 + 说话准则 + 危机铁律 + 工具清单
├── DEVELOPER.md                 # 开发者接入说明（给你看的）
├── references/                  # AI 按需加载的细则
│   ├── crisis-escalation.md     #   危机分级处置细则
│   ├── compliance.md            #   可配置合规红线
│   ├── listening-method.md      #   倾听方法论
│   ├── response-playbook.md     #   话术库
│   └── expression-templates.md  #   表达模板
└── assets/
    └── example-conversations.md #   示例对话（正反对照）
```

## 安全与合规（重要）

- **不是医疗工具**：不诊断、不治疗，不冒充心理医生 / 咨询师。
- **危机优先**：一旦出现危机信号，转介规则高于一切，绝不自行判断「是不是开玩笑 / 无风险」。
- **匿名与隐私**：不收集可识别身份、不向第三方透露倾诉内容（危机转介除外）。
- **合规内容非法律意见**：年龄分层、监护授权、危机处置是产品设计建议，正式商用前请由专业律师审核（详见 [`DEVELOPER.md`](DEVELOPER.md) 第 7 节）。

## Roadmap

- [x] v1.0.0 核心倾听能力 + 危机识别与转介
- [ ] 更多语言的转介资源模板
- [ ] 更多场景的话术库（校园 / 家庭 / 职场）

> 有想加的场景或语言？欢迎提 issue 告诉我们。

## 反馈与贡献

欢迎提 issue 反馈问题或想法；想参与完善，欢迎 fork 后提 PR。

📮 联系作者「箫剑平生」：xjpingsheng@126.com

## 许可证与免责声明

本项目采用 [MIT License](LICENSE.txt)。

> 免责声明：树洞是一个测试版工具，不提供医疗诊断、治疗或心理干预。使用者应自行承担接入与运营责任。
