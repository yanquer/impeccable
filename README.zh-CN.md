# Impeccable

你没意识到自己需要的那套设计词汇。1 个 skill、20 个 commands，以及为高质量前端设计整理好的反模式清单。

[English README](README.md)

> **快速开始：** 访问 [impeccable.style](https://impeccable.style) 下载可直接使用的安装包。

## 为什么选择 Impeccable？

Anthropic 创建了 [frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) 这个 skill，用来引导 Claude 产出更好的 UI 设计。Impeccable 在这个基础上继续扩展，提供了更深入的设计知识和更强的可控性。

几乎所有 LLM 都从相似的通用模板中学到东西。没有额外引导时，你很容易得到同样的老问题：Inter 字体、紫色渐变、卡片里套卡片、彩色背景上放灰字。

Impeccable 通过下面几部分来对抗这种偏差：
- **一个扩展后的 skill**，附带 7 个领域参考文件（[查看源码](source/skills/frontend-design/)）
- **20 个 steering commands**，用于审计、评审、打磨、提炼、动画增强等任务
- **整理好的反模式清单**，明确告诉 AI 哪些做法不要用

## 包含内容

### 核心 Skill：frontend-design

这是一个完整的设计 skill，带有 7 个领域参考文件（[查看 skill](source/skills/frontend-design/SKILL.md)）：

| Reference | 覆盖内容 |
|-----------|----------|
| [typography](source/skills/frontend-design/reference/typography.md) | 字体系统、字族搭配、模块化字号比例、OpenType |
| [color-and-contrast](source/skills/frontend-design/reference/color-and-contrast.md) | OKLCH、带色倾向的中性色、暗色模式、无障碍 |
| [spatial-design](source/skills/frontend-design/reference/spatial-design.md) | 间距系统、网格、视觉层级 |
| [motion-design](source/skills/frontend-design/reference/motion-design.md) | 缓动曲线、错峰动画、减少动态 |
| [interaction-design](source/skills/frontend-design/reference/interaction-design.md) | 表单、焦点状态、加载模式 |
| [responsive-design](source/skills/frontend-design/reference/responsive-design.md) | 移动优先、流式设计、容器查询 |
| [ux-writing](source/skills/frontend-design/reference/ux-writing.md) | 按钮文案、错误信息、空状态 |

### 20 个 Commands

| Command | 作用 |
|---------|------|
| `/teach-impeccable` | 一次性初始化：收集设计上下文并写入配置 |
| `/audit` | 执行技术质量检查（a11y、性能、响应式） |
| `/critique` | UX 设计评审：层级、清晰度、情感共鸣 |
| `/normalize` | 对齐设计系统标准 |
| `/polish` | 发布前的最后打磨 |
| `/distill` | 提炼到最核心的表达 |
| `/clarify` | 优化不清晰的 UX 文案 |
| `/optimize` | 性能优化 |
| `/harden` | 错误处理、i18n、边界情况 |
| `/animate` | 增加有目的的动效 |
| `/colorize` | 引入有策略的色彩 |
| `/bolder` | 放大平淡设计的表现力 |
| `/quieter` | 降低过于强势的视觉表达 |
| `/delight` | 增加令人愉悦的细节 |
| `/extract` | 提取为可复用组件 |
| `/adapt` | 适配不同设备与场景 |
| `/onboard` | 设计引导流程 |
| `/typeset` | 修正字体选择、层级与字号 |
| `/arrange` | 修正布局、间距与视觉节奏 |
| `/overdrive` | 加入技术上更惊艳的效果 |

#### 使用示例

**`/audit`** - 执行质量检查并给出报告（不直接修改）
```bash
/audit blog              # 审查 blog hub 和文章页
/audit dashboard         # 检查 dashboard 组件
/audit checkout flow     # 聚焦 checkout 体验
```
*适用场景：* 在动手修改之前，先弄清楚哪里有问题。

**`/normalize`** - 对齐设计系统
```bash
/normalize blog          # 应用设计 token，修正间距
/normalize buttons       # 统一按钮样式
```
*适用场景：* 在 audit 之后，用来修复不一致问题。

**`/critique`** - UX 设计评审
```bash
/critique landing page   # 评审 landing page 的 UX
/critique onboarding     # 检查 onboarding 流程
```
*适用场景：* 当你想获得设计反馈，而不是技术修复建议时。

**`/polish`** - 发布前最后一轮打磨
```bash
/polish feature modal    # 发布前整理 modal
/polish settings page    # 最后检查 settings 页面
```
*适用场景：* 在部署上线前做最后收尾。

**组合使用 commands：**
```bash
/audit /normalize /polish blog    # 完整流程：审计 → 修复 → 打磨
/critique /harden checkout        # UX 评审 + 补强错误处理
```

### 反模式

这个 skill 明确写出了要避免的做法：

- 不要使用被过度使用的字体（Arial、Inter、系统默认字体）
- 不要在彩色背景上使用灰色文字
- 不要使用纯黑或纯灰（始终带一点色相倾向）
- 不要把所有内容都塞进卡片，也不要卡片套卡片
- 不要使用 bounce / elastic easing（会显得过时）

## 效果展示

访问 [impeccable.style](https://impeccable.style#casestudies) 查看真实项目在使用 Impeccable commands 前后的案例对比。

## 安装

### 方式 1：从官网下载安装（推荐）

访问 [impeccable.style](https://impeccable.style)，下载适用于你工具的 ZIP 包并解压到项目中。

### 方式 2：直接从仓库复制

**Cursor：**
```bash
cp -r dist/cursor/.cursor your-project/
```

> **注意：** Cursor skills 需要额外设置：
> 1. 在 Cursor Settings → Beta 中切换到 Nightly channel
> 2. 在 Cursor Settings → Rules 中启用 Agent Skills
>
> [了解更多 Cursor skills](https://cursor.com/docs/context/skills)

**Claude Code：**
```bash
# 项目级安装
cp -r dist/claude-code/.claude your-project/

# 或全局安装（对所有项目生效）
cp -r dist/claude-code/.claude/* ~/.claude/
```

**OpenCode：**
```bash
cp -r dist/opencode/.opencode your-project/
```

**Pi：**
```bash
cp -r dist/pi/.pi your-project/
```

**Gemini CLI：**
```bash
cp -r dist/gemini/.gemini your-project/
```

> **注意：** Gemini CLI skills 需要额外设置：
> 1. 安装预览版：`npm i -g @google/gemini-cli@preview`
> 2. 运行 `/settings` 并启用 "Skills"
> 3. 运行 `/skills list` 确认安装成功
>
> [了解更多 Gemini CLI skills](https://geminicli.com/docs/cli/skills/)

**Codex CLI：**
```bash
cp -r dist/codex/.codex/* ~/.codex/
```

**Trae：**
```bash
# Trae China（国内版）
cp -r dist/trae/.trae-cn/skills/* ~/.trae-cn/skills/

# Trae International（国际版）
cp -r dist/trae/.trae/skills/* ~/.trae/skills/
```

> **注意：** Trae 有两个版本，对应不同的配置目录：
> - **Trae China：** `~/.trae-cn/skills/`
> - **Trae International：** `~/.trae/skills/`
>
> 复制完成后，重启 Trae IDE 才会生效。

## 用法

安装完成后，就可以在你的 AI harness 里直接使用这些 commands：

```bash
/audit           # 找出问题
/normalize       # 修复不一致
/polish          # 最后打磨
/distill         # 去掉多余复杂度
```

大多数 commands 都支持可选参数，用来聚焦具体区域：

```bash
/audit header
/polish checkout-form
```

**注意：** Codex CLI 的语法不同，使用 `/prompts:audit`、`/prompts:polish` 这类形式。

## 支持的工具

- [Cursor](https://cursor.com)
- [Claude Code](https://claude.ai/code)
- [OpenCode](https://opencode.ai)
- [Pi](https://pi.dev)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- [Codex CLI](https://github.com/openai/codex)
- [VS Code Copilot](https://code.visualstudio.com)
- [Kiro](https://kiro.dev)
- [Trae](https://trae.ai)

## 参与贡献

构建说明和贡献指南见 [DEVELOP.md](DEVELOP.md)。

## License

Apache 2.0。详见 [LICENSE](LICENSE)。

`frontend-design` skill 基于 [Anthropic 的原始版本](https://github.com/anthropics/skills/tree/main/skills/frontend-design) 扩展而来。归属说明见 [NOTICE.md](NOTICE.md)。

---

Created by [Paul Bakaus](https://www.paulbakaus.com)
