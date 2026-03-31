# Changelog

本文件用于记录该项目所有值得注意的变更。

[English Changelog](CHANGELOG.md)

## [Unreleased]

### 新增
- 在 `source/skills/*/SKILL.md` 中新增可选的 `description-zh` 支持，用于提供中文 skill 描述。
- 为全部 21 个 source skills 补充中文描述，以提升 Codex 侧的 skill 发现能力。
- 新增测试，覆盖 `description-zh` 解析、Codex 描述解析逻辑，以及非 Codex provider 的回退行为。

### 变更
- 更新 Codex transformer：当存在 `description-zh` 时，生成的 Codex skill 描述会使用“中文在前、英文补充”的双语格式。
- 将 `.codex/skills/*/SKILL.md` 同步为重新生成后的中文增强版 Codex 输出。
- 更新贡献文档，说明 `description-zh` 的用途以及 Codex 专属的描述映射行为。
