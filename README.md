# Chinese Writing｜中文写作与文稿修缮规范

**让文字准确地承载思想，自然地抵达读者。**

Chinese Writing 是一套面向大语言模型与 AI Agent 的中文写作规范，适用于即时对话，以及论文、报告、技术文档、提案、书信、评论等独立文稿。它从写作认知入手，引导模型辨明目的与受众，立骨起意，贯通文脉，再以自然清通的汉语完成表达与修缮。

规范所追求的语言气质：**朴拙立骨，雅言传神；意合顺畅，修辞有度。** 叙述处清通有力，转折处从容有度；该直陈时明快落笔，该铺陈时层层展开，该留白时余韵自生。文字的雅洁来自思想透彻、句法自然与取舍得当。

## 写作从认知开始

文章的品质，首先取决于作者是否明确自己要表达什么、面向谁表达，以及读者读完后应当获得什么。模型根据任务选择合宜的作者位置与叙述视角：对话回答直接服务当前交流，独立文稿则面向预定读者，形成自足的表达。

写作指令、提纲、批注与修改过程属于创作现场。它们应当转化为实际的组织与编辑动作，由成稿的品质体现。用户要求执行删改时，改动直接落实在目标内容上；交付物只呈现读者所需的信息。

## 立意统摄文脉

核心问题与主要判断决定材料的取舍，也决定篇章的走向。作者掌握的背景与推理，读者未必天然熟悉；必要的定义、前提与中间推导应在文中交代，让读者顺着清晰路径理解结论。

逻辑在骨不在皮。汉语依凭事理的内在脉络推进，段落之间依照真实的因果、条件、比较、递进或照应关系自然流转，无须通篇堆砌显性连接词。详略围绕主线安排，版式服务于阅读，文章由此形成浑然一体的气象。

## 汉语表达与修辞分寸

表达以准确、自然、有力为先。动词带动叙述，主语顺势承接，长定语适当拆分，句长随信息起伏。让步、转折、递进与限定各有语义任务，常用词与书面词各得其所。

正向表达从核心对象、实际行动与有效信息起笔。真实的对照能够凸显差异，虚构的对立与空泛拔高则会打断论述。面对局限与未尽之处，懂得正向定界与春秋笔法，含蓄藏拙，让边界自然随语境显露，不以突兀的缺陷自招打断阅读心流。

## 编辑判断与摒弃防御性说理

改写的目标是让文本更准确、更清楚、更完整，也更契合读者。核心事实从严，一般表述从宽，具体事实慎增。概括性描述可以合理归纳、展开和校准；逻辑关系依据上下文顺畅补足；精确数字、参数、身份、成果及关键因果则须有据可依。

文字面向真实读者，而非防范反驳的免责辩词。摒弃防御性说理与过度免责的执念，严禁将日常问候与常识对话引向哲学术语式的极端自证与杠精推演。以事实建立真实信赖，行文松弛自如。

## 项目结构

```text
chinese-writing/
├── .agents/
│   └── workflows/
│       └── chinese-writing.md    # Antigravity 原生 Slash Command 映射
├── SKILL.md                      # 核心执行规范（含 dsh 与 Codex 原生元数据）
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── references/
│   └── revision-workflow.md      # 文稿修订工作流
└── tests/
    └── acceptance-checklist.md   # 验收清单与反防御性说理测试用例
```

## 多平台快捷调用与安装

各主流 Agent 宿主对技能的交互触发机制有所不同，本项目已完成全平台原生适配：

| Agent 宿主 | 交互唤起方式 | 底层触发机制 | 适配支持 |
|---|---|---|---|
| **DeepSeek Harness (`dsh`)** | 输入 `/` 弹出补全建议，或键入 `/chinese-writing` | `SKILL.md` 配置 `user-invocable: true`，接入内置的 `slash-command-fuzzy-discovery` 模糊检索 | 原生支持 |
| **OpenAI / Codex** | 提示词输入框中输入 `$chinese-writing` | 遵循 OpenAI 标准规范，读取 `SKILL.md` 的 `name` 字段显式召唤 | 原生支持 |
| **Google Antigravity** | 输入框键入 `/chinese-writing`，或纯自然语言自适应触发 | 内置 `.agents/workflows/chinese-writing.md` 工作流，打通前端斜杠补全弹窗与语义意图双通道 | 原生支持 |
| **Claude Code** | 会话意图路由或通过斜杠命令唤起 | 兼容通用 Agent Skills 开放标准与 `.claude/` 目录规范 | 原生支持 |

---

### 1. DeepSeek Harness (dsh)

将完整项目目录放置或软链接到以下任一位置：

- **用户全局目录（推荐）：** `~/.dsh/skills/chinese-writing/`（Windows 对应 `%USERPROFILE%\.dsh\skills\chinese-writing\`）
- **当前项目目录：** `<repo>/.dsh/skills/chinese-writing/`

**一键软链接（Windows PowerShell）：**
```powershell
New-Item -ItemType Junction -Path "$env:USERPROFILE\.dsh\skills\chinese-writing" -Target "D:\drzqr\Documents\GitHub\chinese-writing"
```
启动或重启 `dsh`，在输入框键入 `/` 即可看到模糊匹配的 `/chinese-writing` 命令。

---

### 2. OpenAI / Codex

将项目目录复制或软链接至以下位置之一：

- 当前仓库：`<repo>/.agents/skills/chinese-writing/`
- 个人全局目录：`~/.agents/skills/chinese-writing/`（Windows 对应 `%USERPROFILE%\.agents\skills\chinese-writing\`）

在 Codex 会话中使用 `$chinese-writing` 即可显式调用。

---

### 3. Google Antigravity

Antigravity 同时支持**斜杠补全（`/` 菜单）**与**语义自适应发现**：

- **全局启用（推荐）：**
  - 技能规范挂载：`~/.gemini/config/skills/chinese-writing/`（对应 `%USERPROFILE%\.gemini\config\skills\`）
  - 斜杠命令挂载：`~/.gemini/config/workflows/chinese-writing.md`（对应 `%USERPROFILE%\.gemini\config\workflows\`）
- **当前项目启用：**
  - 直接保留仓库自带的 `.agents/workflows/chinese-writing.md` 与 `.agents/skills/chinese-writing/` 即可。

在聊天框键入 `/chinese-writing` 即可看到命令卡片，或直接用自然语言交流，Agent 会自动感知并激活。

---

### 4. Claude Code 与其他开放规范宿主

按对应宿主说明将目录放置于 `~/.claude/skills/chinese-writing/` 或 `<repo>/.claude/skills/chinese-writing/` 即可。

## 参与贡献与许可

欢迎提交能够检验规则边界的通用建议、跨文体改进与评测设计。请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。项目采用 MIT License，详见 [LICENSE](LICENSE)。

## 参考资料

- [OpenAI：Build skills](https://learn.chatgpt.com/docs/build-skills) — Agent Skills 目录结构与 Codex 技能发现规范。
