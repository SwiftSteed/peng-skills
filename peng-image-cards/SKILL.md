---
name: peng-image-cards
description: 基于 HTML+CSS 的竖屏内容卡片生成器。保留 baoyu-image-cards 的 12 风格 × 8 布局 × 3 配色系统，用纯 HTML/CSS 替代生图。输出为自包含 HTML 文件，适用于公众号排版、邮件营销、个人主页等场景。当用户需要"图片卡片"、"小红书图片"、"微信图文"、"卡片"、"image cards"时使用。
version: 0.1.0
---

# HTML Image Card Generator

将内容转化为**单文件 HTML** 的竖屏内容卡片。核心设计：

- **竖屏优先** — 默认 3:4 比例，适配手机屏幕，上下滚动浏览
- **12 风格 × 8 布局 × 3 配色** — 继承自 baoyu-image-cards 的视觉系统，全部 CSS 化
- **纯 HTML+CSS 实现** — 无需生图，浏览器打开即见效果
- **嵌入式分发** — 可截图发社交媒体，也可将 HTML 片段嵌入公众号文章

## 与 baoyu-image-cards 的关系

本 skill 是 baoyu-image-cards 的 HTML+CSS 移植版：

| 维度 | baoyu-image-cards | peng-image-cards |
|------|-----------------|-----------------|
| 输出格式 | 逐张 PNG 图片 | 单文件 HTML（可滚动） |
| 风格系统 | 12 风格 × 8 布局 × 3 配色 → 提示词 | 12 风格 × 8 布局 × 3 配色 → CSS 变量 |
| 生成方式 | 调用图像生成后端 | 直接写入 HTML |
| 使用场景 | 小红书/朋友圈发图片 | 公众号排版 / 邮件 / 网页嵌入 / 截图发社交媒体 |
| 工作流 | 4 步 | 7 步（含 HTML 审查） |

## 语言

用中文回应用户，技术标记（风格名、文件路径、CSS 类名）保留英文。

## 选项

| 选项 | 描述 |
|------|------|
| `--style <name>` | 视觉风格（12 选 1） |
| `--layout <name>` | 信息布局（8 选 1） |
| `--palette <name>` | 配色覆盖：macaron / warm / neon |
| `--preset <name>` | 风格+布局快捷组合（28 选 1） |
| `--cards <N>` | 目标卡片数（1-10，推荐 3-7） |
| `--outline-only` | 仅生成大纲 |
| `--html-only` | 仅生成 HTML，不进入审查 |

## 风格系统

### 12 个视觉风格

| 风格 | 关键词 | CSS 表现 |
|------|--------|----------|
| `cute`（默认） | 甜美、少女 | 圆角、粉色系、柔光边框 |
| `fresh` | 清爽、自然 | 白底、绿/蓝点缀、轻盈阴影 |
| `warm` | 温暖、亲切 | 暖色调、柔和渐变、有机线条 |
| `bold` | 高冲击力 | 粗边框、强对比、大字重 |
| `minimal` | 极简、高级 | 留白充裕、细线、克制配色 |
| `retro` | 复古、怀旧 | 暖黄/棕色调、粗粒纹理、衬线字 |
| `pop` | 活力、趣味 | 荧光色撞色、几何装饰、动态感 |
| `notion` | 手绘线条、知识感 | 细线插图风、草稿笔触、灰度基调 |
| `chalkboard` | 黑板、教学 | 深色底、粉笔色文字、粗犷感 |
| `study-notes` | 真实笔记风 | 蓝笔+红批注+黄荧光笔、手写字体 |
| `screen-print` | 丝印海报 | 纯色块、网点纹理、大胆叙事 |
| `sketch-notes` | 手绘教育风 | 马卡龙色、晃动线条、暖奶油底色 |

完整风格规范：`references/styles/<style>.md`。

### 8 个布局

| 布局 | 适用场景 | CSS 实现 |
|------|---------|----------|
| `sparse` | 1-2 要点，封面/结尾 | 居中大标题，大量留白 |
| `balanced` | 3-4 要点，标准内容 | 2×2 网格或上下均分 |
| `dense` | 5-8 要点，知识卡片 | 紧凑网格，小字高密 |
| `list` | 枚举/排行（4-7 项） | 编号列表，层次清晰 |
| `comparison` | 左右对比 | 双栏，中轴线分隔 |
| `flow` | 流程/时间线（3-6 步） | 竖排步骤，连接线 |
| `mindmap` | 中心发散（4-8 分支） | 中央节点+放射分支 |
| `quadrant` | 四象限/田字格 | 2×2 四块，各含标题 |

布局规范：`references/layouts/<layout>.md`。

### 3 个配色覆盖

| 配色 | 底色 | 强调色 | 感觉 |
|------|------|--------|------|
| `macaron` | 暖奶油 #F5F0E8 | 蓝 #A8D8EA / 紫 #D5C6E0 / 薄荷 #B5E5CF | 柔和、教育 |
| `warm` | 柔桃色 #FFECD2 | 橙 #ED8936 / 赤陶 #C05621 / 金 #F6AD55 | 温暖、大地 |
| `neon` | 深紫 #1A1025 | 青 #00F5FF / 品红 #FF00FF / 绿 #39FF14 | 高能、未来 |

### 28 个预设（风格+布局快捷组合）

**知识 & 学习**：`knowledge-card` `checklist` `concept-map` `swot` `tutorial` `classroom` `study-guide` `hand-drawn-edu` `sketch-card` `sketch-summary`

**生活方式 & 分享**：`cute-share` `girly` `cozy-story` `product-review` `nature-flow`

**观点 & 冲击**：`warning` `versus` `clean-quote` `pro-summary`

**潮流 & 娱乐**：`retro-ranking` `throwback` `pop-facts` `hype`

**海报 & 编辑**：`poster` `editorial` `cinematic`

### 自动风格选择

| 内容关键词 | 推荐预设 |
|-----------|----------|
| 美妆、穿搭、少女、可爱 | `cute-share` 或 `girly` |
| 健康、自然、清新、有机 | `product-review` 或 `nature-flow` |
| 生活、故事、情感、温暖 | `cozy-story` |
| 避坑、重要、必看、警告 | `warning` 或 `versus` |
| 专业、商务、优雅 | `clean-quote` 或 `pro-summary` |
| 经典、复古、传统 | `throwback` 或 `retro-ranking` |
| 趣味、冷知识、惊人 | `hype` 或 `pop-facts` |
| 知识、概念、效率、SaaS | `knowledge-card` 或 `checklist` |
| 教育、教程、学习、课堂 | `tutorial` 或 `classroom` |
| 笔记、手写、学习重点 | `study-guide` |
| 影评、观点、海报风、戏剧 | `poster` 或 `editorial` |
| 手绘、图解、流程图 | `hand-drawn-edu` 或 `sketch-card` |

无匹配时回退到 `cute-share`。

### 卡片数启发式

| 源内容长度 | 推荐卡片数 |
|-----------|-----------|
| < 300 字 | 1-3 |
| 300-800 字 | 3-5 |
| 800-1500 字 | 5-7 |
| > 1500 字 | 7-10（考虑拆分为多系列） |

## 文件布局

```
image-cards/{topic-slug}/
├── source-{slug}.{ext}     # 源内容
├── analysis.md              # 分析结果
├── outline.md               # 大纲（含 CSS_STYLE_INSTRUCTIONS）
└── index.html               # 最终 HTML 输出（唯一产出物）
```

**备份规则**：写入前如文件已存在，重命名为 `{name}-backup-YYYYMMDD-HHMMSS.{ext}`。

## 工作流

```
- [ ] Step 1: Setup & 分析
- [ ] Step 2: 确认 ⚠️ 必需
- [ ] Step 3: 生成大纲
- [ ] Step 4: 审查大纲（条件性）
- [ ] Step 5: 生成 HTML 卡片
- [ ] Step 6: 审查 HTML（条件性）
- [ ] Step 7: 预览与交付
```

### Step 1: Setup & 分析

**1.1 加载 EXTEND.md** — 按优先级查找：

| 路径 | 范围 |
|------|------|
| `.baoyu-skills/peng-image-cards/EXTEND.md` | 项目 |
| `$HOME/.baoyu-skills/peng-image-cards/EXTEND.md` | 用户 |

读取并输出偏好摘要。未找到则使用默认值。

**1.2 分析内容** — 分类内容类型、检测语言、标注风格信号、识别关键要点、估算卡片数。

**1.3 检查已有输出** — 如果 `image-cards/{topic-slug}/` 存在，询问处理方式。

保存分析结果到 `analysis.md`。

### Step 2: 确认 ⚠️ 必需

**硬性门控**：必须完成确认才能进入 Step 3。除非用户明确说"直接生成"/"不用确认"/"跳过确认"。

展示推荐方案，批量 5 个问题：
1. 风格+布局（推荐预设 / 备选 / 自定义）
2. 配色（默认 / macaron / warm / neon）
3. 卡片数
4. 是否审查大纲
5. 是否审查 HTML

### Step 3: 生成大纲

解析风格 → `references/styles/<style>.md`；布局 → `references/layouts/<layout>.md`；配色 → `references/palettes/<palette>.md`。

构建 `CSS_STYLE_INSTRUCTIONS`（`:root` 变量块），写入大纲。每张卡片包含：位置、标题、要点、布局类型。

`--outline-only` 时在此停止。

### Step 4: 审查大纲（条件性）

展示卡片列表（`# | 标题 | 布局`）、总数、解析后的风格+配色。询问：继续 / 编辑大纲 / 重新生成。

### Step 5: 生成 HTML 卡片

1. 从 `assets/template.html` 拷贝模板到 `image-cards/{topic-slug}/index.html`
2. 替换 `[必填]` 占位符
3. 从大纲的 `CSS_STYLE_INSTRUCTIONS` 中提取完整 `:root` 块，替换模板中的风格变量
4. 为每张卡片生成对应的 `<article class="card ...">` HTML
5. 插入到模板的 `<!-- CARDS_HERE -->` 位置

> [!IMPORTANT]
> **编码安全**：必须使用 `Write` 工具直接写入 `index.html`。禁止通过 Bash heredoc、Python 脚本等间接方式生成最终 HTML 文件。

`--html-only` 时在此停止。

### Step 6: 审查 HTML（条件性）

展示生成的卡片摘要，询问：继续 / 编辑 HTML / 重新生成。

### Step 7: 预览与交付

```bash
open "image-cards/{topic-slug}/index.html"
```

直接浏览器打开即可，无需本地服务器。

```
Image Card Series Complete!

Topic: [topic]
Style: [name] · Layout: [name] · Palette: [name]
Location: image-cards/{topic-slug}/
Cards: N

- 01: [封面标题]
- ...
- NN: [结尾标题]

HTML: index.html
```

## 卡片修改

| 操作 | 流程 |
|------|------|
| 编辑 | 直接修改 `index.html` 中对应 `<article>` |
| 添加 | 插入新 `<article>`，更新序号 |
| 删除 | 删除对应 `<article>` |
| 换配色 | 替换 `:root` 块中的 palette 变量 |
| 换风格 | 替换 `:root` 块中的风格变量 |
| 换布局 | 修改对应 card 的 class |

## 使用场景

### 场景 A：社交媒体
浏览器打开 → 截图工具逐张截取 → 发小红书/朋友圈/微博

### 场景 B：公众号排版
从 `index.html` 中提取 `<article>` 卡片，嵌入公众号编辑器 HTML 模式

### 场景 C：邮件营销
复制 HTML，粘贴到邮件客户端，比图片更轻、加载更快

### 场景 D：个人主页
一套卡片拼成 Link-in-bio 页面，一个链接发出去

## 参考文件

| 文件 | 内容 |
|------|------|
| `assets/template.html` | 完整可运行的 HTML 模板 |
| `references/styles/<style>.md` | 各风格 CSS 规范 |
| `references/layouts/<layout>.md` | 各布局 CSS 规范 |
| `references/palettes/<palette>.md` | 各配色 CSS 变量 |

## 字体策略

与 peng-slide-deck 相同：Google Fonts（首选）→ Apple 系统字体（回退）→ CSS 通用字体族（兜底）。所有字体 SIL OFL 或系统自带，无版权风险。

## 注意事项

- HTML 文件自包含，无需服务器
- 竖屏卡片默认 3:4 比例，手机全屏浏览体验最佳
- 支持键盘 ↑↓ 滚动、触屏滑动
- 打印：Cmd+P 可保存为 PDF
