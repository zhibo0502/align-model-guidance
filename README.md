# align-model-guidance

按指定模型的官方指导逐项审查项目的 agent 文档、skills 和相关 prompt，并交付可复核的对齐结果。

适用于不同项目与模型供应商。每次使用时读取目标模型的当前官方文档，不固化 GPT-6 参数或某次审计的条目数量。文档对齐不会自动切换生产模型、调用付费 API 或发布改动。

## 安装与使用

将本仓库克隆到 Codex 用户技能目录下的 `align-model-guidance` 文件夹，通常是 `~/.codex/skills/align-model-guidance`。若已安装，更新现有目录，避免覆盖本地改动。

在目标项目中调用：

```text
$align-model-guidance 按 GPT-6 Astra 的当前官方 model guidance，逐项审查并调整本项目的 agent 文档、skills 和相关 prompt，报告真实覆盖率。
```

可替换为其他明确的模型名称。只需要诊断时加上“只审阅，不修改”。

## 输出与边界

技能分别记录指导判定、适用项对齐、文件筛查、语义审阅四种覆盖率。每个比例包含整数分子/分母，并保留官方来源、文件范围、处置依据和未解决项。不适用、关键词扫描或格式校验不算真实模型行为验证。

- [技能入口](SKILL.md)
- [覆盖率与证据约定](references/coverage.md)
- [Codex 界面元数据](agents/openai.yaml)

当前版本经过技能结构、相对链接和元数据校验；尚未进行跨项目行为实验。设计参考了 2026-09-08 读取的 [GPT-6 Astra 官方指导](https://developers.openai.com/api/docs/guides/latest-model#prompting-best-practices)。这是独立维护的技能，不是 OpenAI 官方发布的技能。
