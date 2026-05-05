<div align="center">

# peng-skills

**AI Agent Skills for Content Creation**

内容创作技能合集。

[English](./README.md) · [中文](./README.zh-CN.md)

</div>

---

## 技能列表

| 技能 | 简介 |
|------|------|
| [peng-slide-deck](./peng-slide-deck/SKILL.md) | HTML+CSS 幻灯片生成器 — 4 维正交风格系统（纹理×情绪×排版×密度=525 种组合）、17 个精调预设、8 步可审查管线 |

## 快速开始

```bash
git clone https://github.com/peng2219/peng-skills.git
ln -sf $(pwd)/peng-skills/peng-slide-deck ~/.claude/skills/peng-slide-deck
```

## peng-slide-deck

> 基于 [JimLiu](https://github.com/JimLiu) 的 [baoyu-slide-deck](https://github.com/JimLiu/baoyu-skills)。将生图换成纯 HTML+CSS 输出——保留 4 维风格系统和可审查管线，用浏览器原生渲染。

将内容转化为单文件 HTML 幻灯片——无需生图后端、无需 PPT 工具，浏览器打开即用。

### 用法

```bash
# 从 markdown 文件
/peng-slide-deck path/to/article.md

# 指定风格和受众
/peng-slide-deck path/to/article.md --style corporate
/peng-slide-deck path/to/article.md --audience executives

# 目标页数
/peng-slide-deck path/to/article.md --slides 15

# 仅生成大纲（不生成 HTML）
/peng-slide-deck path/to/article.md --outline-only

# 指定语言和主题色
/peng-slide-deck path/to/article.md --lang zh --theme indigo
```

### 选项

| 选项 | 描述 |
|------|------|
| `--style <name>` | 视觉风格：预设名或 `custom` |
| `--audience <type>` | 受众：beginners, intermediate, experts, executives, general |
| `--lang <code>` | 输出语言（en, zh, ja 等） |
| `--slides <N>` | 目标页数（推荐 8-25，最大 30） |
| `--outline-only` | 仅生成大纲，跳过 HTML |
| `--html-only` | 仅生成 HTML，跳过审查 |
| `--theme <name>` | 主题色：ink, indigo, forest, kraft, dune |

### 核心特性

- **4 维正交风格系统**：纹理(5) × 情绪(7) × 排版(5) × 密度(3) = 525 种 CSS 主题
- **17 个精调预设**：blueprint、corporate、minimal、sketch-notes、bold-editorial、vintage 等——根据内容关键词自动推荐
- **8 步可审查管线**：分析 → 确认 → 大纲 → 审查 → 生成 HTML → 审查 → 预览 → 交付
- **字体零版权风险**：Google Fonts (SIL OFL) → Apple 系统字体 → CSS 通用族名
- **自包含输出**：单 HTML 文件，含 WebGL 背景、键盘/滚轮/触屏翻页、ESC 索引视图、离线 Motion One 动效
- **直接打印 PDF**：浏览器内 Cmd+P

## 许可证

本项目基于 [MIT 许可证](./LICENSE) 开源。
