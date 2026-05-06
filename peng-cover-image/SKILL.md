---
name: peng-cover-image
description: 基于 HTML+CSS 的文章封面生成器。保留 baoyu-cover-image 的 5 维定制系统（Type×Palette×Rendering×Text×Mood）+ 11 套配色 + 7 种渲染风格。输出为单文件 HTML，适用于文章封面、社交分享图、博客头图、邮件头图。支持 16:9、2.35:1、1:1 等多种比例。当用户需要"封面图"、"文章封面"、"cover image"、"头图"时使用。
version: 0.1.0
---

# HTML Cover Image Generator

将文章信息转化为**单文件 HTML** 封面图。核心设计：

- **一页即封面** — 单个 HTML 文件，打开即见，截图即用
- **5 维定制** — Type × Palette × Rendering × Text × Mood，继承自 baoyu-cover-image
- **纯 HTML+CSS** — 无需生图，浏览器预览后截图或导出
- **多比例支持** — 16:9（默认）、2.35:1、4:3、3:2、1:1、3:4

## 与 baoyu-cover-image 的关系

| 维度 | baoyu-cover-image | peng-cover-image |
|------|-----------------|------------------|
| 输出 | 单张 PNG | 单文件 HTML |
| 风格 | 5 维 → 提示词 | 5 维 → CSS 变量 |
| 生成 | 调用生图 API | 直接写入 HTML |
| 使用 | 嵌入文章 | 浏览器打开 → 截图 / 导出 PDF / 嵌入网页 |

## 语言

用中文回应用户，技术标记保留英文。

## 选项

| 选项 | 描述 |
|------|------|
| `--type <name>` | 构图类型：hero / conceptual / typography / metaphor / scene / minimal |
| `--palette <name>` | 配色：warm / elegant / cool / dark / earth / vivid / pastel / mono / retro / duotone / macaron |
| `--rendering <name>` | 渲染风格：flat-vector / hand-drawn / painterly / digital / pixel / chalk / screen-print |
| `--text <level>` | 文字量：none / title-only / title-subtitle / text-rich |
| `--mood <level>` | 对比度：subtle / balanced / bold |
| `--font <name>` | 字体：clean / handwritten / serif / display |
| `--aspect <ratio>` | 比例：16:9 / 2.35:1 / 4:3 / 3:2 / 1:1 / 3:4 |
| `--title <text>` | 封面标题 |
| `--subtitle <text>` | 副标题 |
| `--author <text>` | 作者名 |
| `--lang <code>` | 语言（en, zh, ja 等） |

## 5 个维度

| 维度 | 可选值 | 默认 |
|------|--------|------|
| **Type** | hero, conceptual, typography, metaphor, scene, minimal | auto |
| **Palette** | warm, elegant, cool, dark, earth, vivid, pastel, mono, retro, duotone, macaron | auto |
| **Rendering** | flat-vector, hand-drawn, painterly, digital, pixel, chalk, screen-print | auto |
| **Text** | none, title-only, title-subtitle, text-rich | title-only |
| **Mood** | subtle, balanced, bold | balanced |
| **Font** | clean, handwritten, serif, display | clean |

### Type（构图类型）

| Type | 说明 | CSS 表现 |
|------|------|----------|
| `hero` | 大标题居中，视觉冲击 | 标题超大、居中、背景突出 |
| `conceptual` | 抽象概念表达 | 几何装饰、色块碰撞、留白充裕 |
| `typography` | 字体主导 | 排版实验、字重对比、字号跨度大 |
| `metaphor` | 隐喻视觉 | 图形元素象征内容主题 |
| `scene` | 场景感 | 层次丰富、前景/中景/后景 |
| `minimal` | 极简 | 大量留白、单一线条或色块点缀 |

### Palette（11 套配色）

| 配色 | 主色 | 辅色 | 适合 |
|------|------|------|------|
| `warm` | 暖橙 #ED8936 | 金 #F6AD55 | 人文、生活 |
| `elegant` | 珊瑚 #E8A598 | 青 #5B8A8A | 时尚、奢侈品 |
| `cool` | 蓝 #2563EB | 深蓝 #1E3A5F | 科技、数据 |
| `dark` | 紫 #8B5CF6 | 青 #06B6D4 | 影视、游戏 |
| `earth` | 森林绿 #276749 | 鼠尾草 #9AE6B4 | 自然、可持续 |
| `vivid` | 红 #EF4444 | 绿 #22C55E | 热点、竞技 |
| `pastel` | 粉 #FFB6C1 | 薄荷 #98D8C8 | 生活方式、育儿 |
| `mono` | 纯黑 #000 | 深灰 #1F1F1F | 极简、商务 |
| `retro` | 珊瑚 #E07A5F | 薄荷绿 #81B29A | 怀旧、文化 |
| `duotone` | 焦橙 #E8751A | 深青 #0A6E6E | 戏剧、电影 |
| `macaron` | 天蓝 #A8D8EA | 薄荷 #B5E5CF | 教育、清新 |

### Rendering（渲染风格）

| 风格 | CSS 表现 |
|------|----------|
| `flat-vector` | 纯色块、清晰边界、几何图形 |
| `hand-drawn` | 手写字体、不规则边框、草图感 |
| `painterly` | 柔和渐变、模糊阴影、水彩质感 |
| `digital` | 干净渐变、细边框、现代 UI 感 |
| `pixel` | 像素化装饰、粗边框、块状背景 |
| `chalk` | 深色底、粉笔白文字、粗犷线条 |
| `screen-print` | 网点纹理、大胆配色、海报感 |

### Text（文字层级）

| Level | 内容 |
|-------|------|
| `none` | 纯视觉，无文字 |
| `title-only` | 仅标题（默认） |
| `title-subtitle` | 标题 + 副标题 |
| `text-rich` | 标题 + 副标题 + 作者 + 标签 |

### Mood（对比度）

| Level | 效果 |
|-------|------|
| `subtle` | 低对比、柔和过渡 |
| `balanced` | 适中（默认） |
| `bold` | 高对比、强冲击 |

### 自动选择

| 内容关键词 | 推荐 Type | 推荐 Palette |
|-----------|-----------|-------------|
| 技术、编程、AI、数据 | conceptual | cool |
| 生活、故事、情感、人文 | hero | warm |
| 时尚、奢侈、设计、品牌 | minimal | elegant |
| 自然、环保、健康、户外 | scene | earth |
| 影视、游戏、娱乐、科幻 | hero | dark |
| 新闻、热点、竞技、体育 | typography | vivid |
| 教育、科普、学术、教程 | conceptual | macaron |
| 怀旧、历史、文化、传统 | typography | retro |
| 商务、管理、创业、金融 | minimal | mono |

## 文件布局

```
cover-image/{topic-slug}/
├── source-{slug}.{ext}
├── analysis.md
└── index.html
```

## 工作流

```
- [ ] Step 1: Setup & 分析
- [ ] Step 2: 确认 ⚠️ 必需
- [ ] Step 3: 生成 HTML 封面
- [ ] Step 4: 审查（条件性）
- [ ] Step 5: 预览与交付
```

### Step 1: Setup & 分析

加载 EXTEND.md，分析内容类型、语言、风格信号，自动推荐 Type + Palette + Rendering + Mood。

### Step 2: 确认 ⚠️ 必需

展示推荐方案，批量确认：Type / Palette / Rendering / Text level / Mood / Font / Aspect ratio。

### Step 3: 生成 HTML 封面

1. 从 `assets/template.html` 拷贝模板
2. 替换 `:root` 变量块
3. 填入标题、副标题、作者等文字内容
4. 应用 Type 对应的布局、Rendering 对应的装饰

> [!IMPORTANT]
> **编码安全**：必须使用 `Write` 工具直接写入 `index.html`。

### Step 4: 审查（条件性）

展示封面效果，询问：继续 / 调整维度 / 重新生成。

### Step 5: 预览与交付

```bash
open "cover-image/{topic-slug}/index.html"
```

## 使用场景

- 浏览器打开 → 截图（Cmd+Shift+4）→ 用作文章封面、社交分享图
- 导出 PDF → 用于印刷或文档封面
- 嵌入网页 → 作为博客文章的头图 `<iframe>` 或复制 HTML
- Open Graph 图片 → 截图后设为 `<meta property="og:image">`

## 字体策略

与 peng-slide-deck 相同：Google Fonts → 系统字体 → 通用族名。所有字体无版权风险。

## 注意事项

- 浏览器打开即预览，无需服务器
- 支持任意比例，默认 16:9
- Cmd+P 可打印或导出 PDF
- Google Fonts 在国内不可用时自动回退系统字体
