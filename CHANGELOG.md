# Changelog

## 0.1.0 — 2026-11-03

### 初始发布

- 建立面向大语言模型与 AI Agent 的中文写作与文稿修缮规范（Chinese Writing）。
- 确立「朴拙立骨，雅言传神；意合顺畅，修辞有度」的核心语言审美。
- 确立核心写作判断：作者位置与受众意识、立意统摄文脉、汉语句法筋骨、修辞分寸与春秋笔法、分层事实核验与摒弃防御性说理。
- 提出「逻辑在骨不在皮」与「含蓄藏拙」原则，提倡意合顺畅与正向定界，杜绝防御性过度免责与虚空抬杠。
- 建立文稿修订工作流（`references/revision-workflow.md`）与输出质量验收清单（`tests/acceptance-checklist.md`）。
- **多平台交互全面适配：**
  - **DeepSeek Harness (`dsh`)：** 配置 `user-invocable: true`，原生支持 `/` 模糊补全发现。
  - **OpenAI / Codex：** 遵循标准规范，原生支持 `$chinese-writing` 显式召唤。
  - **Google Antigravity：** 内置 `.agents/workflows/chinese-writing.md`，原生打通 `/chinese-writing` 斜杠命令与语义自适应双通道。
