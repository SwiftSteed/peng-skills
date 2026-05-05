# HTML 组件参考

> 在 Step 5（生成 HTML）时使用。每个组件展示标准 HTML 代码片段和使用说明。
> 所有组件基于 `assets/template.html` 中的 CSS 类定义。

---

## 1. Slide Shell（幻灯片外壳）

每个 `<section>` 的标准结构。必须有 `.slide`、主题类（`.light` 或 `.dark`）、可选的 `.hero` 修饰符。

### 浅色内容页

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  
  <div class="frame">
    <!-- 页面内容 -->
  </div>
  
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

### 深色内容页

```html
<section class="slide dark" data-animate="cascade">
  <!-- 结构同浅色页 -->
</section>
```

### Hero 页（封面/章节分隔/封底）

```html
<section class="slide hero dark" data-animate="hero">
  <!-- .hero 减遮罩、透 WebGL 背景 -->
</section>
```

### 规则

| 属性 | 规则 |
|------|------|
| `.slide` | 必须，所有 slide 的基类 |
| `.light` / `.dark` | 必须二选一。控制文字颜色、背景遮罩颜色 |
| `.hero` | 可选。大幅降低遮罩透明度（`.light::before` 从 .78 降到 .16），允许 WebGL 背景穿透 |
| `data-animate` | 可选。值：`cascade`（默认）/ `hero` / `quote` / `directional` / `pipeline` |
| `data-theme` | 可选。显式覆盖 JS 的主题检测（通常不需要，JS 从 class 自动判断） |

### 页面主题选择指南

| 内容类型 | 推荐 .light/.dark | 是否 hero |
|----------|-------------------|-----------|
| 封面 | dark | 是 |
| 内容正文 | light | 否 |
| 数据展示 | light | 否 |
| 引用语 | dark | 是 |
| 图片网格 | light | 否 |
| 对比 | light | 否 |
| 章节分隔 | light 或 dark（与封面交替） | 是 |
| 封底 | dark | 是 |

---

## 2. Typography（字体层级）

### 2.1 字体分配规则（硬性规则）

| 角色 | 字体族变量 | 用途 |
|------|-----------|------|
| 中文标题 | `--font-headline-zh` | `.h-hero`、`.h-xl`、`.h-sub`、`.h-md`、`.display-zh`、`.lead`、`.body-serif` |
| 英文标题/Display | `--font-display` | `.h-hero-en`、`.h-xl-en`、`.display`、`em`、`.en`、`.big-num`、`.mid-num`、`.ghost` |
| 中文正文 | `--font-body-zh` | `.body-zh`、`.stat-note`、`.step-title`、`.step-desc`、`.pillar .d`、`.rowline .v` |
| 英文正文 | `--font-body-en` | （在英文模板中用于 .body-zh 的替代） |
| 等宽/元数据 | `--font-mono` | `.kicker`、`.chrome`、`.foot`、`.meta`、`.meta-row`、`.stat-label`、`.tag`、`.frame-cap`、`.step-nb` |
| 手写 | `--font-handwritten` | `.sign`（签名效果，极少使用） |

**核心规则**：衬线 = 标题（serif），无衬线 = 正文（sans-serif），等宽 = 元数据（mono）。不可混用。

### 2.2 标题层级使用场景

```html
<!-- 封面大标题 -->
<div class="h-hero">重新定义协作方式</div>        <!-- 中文封面 -->
<div class="h-hero-en">Redefining Collaboration</div> <!-- 英文封面 -->

<!-- 页面主标题 -->
<div class="h-xl">核心发现与洞察</div>             <!-- 内容页主标题 -->
<div class="h-xl-en">Key Findings</div>            <!-- 英文内容页主标题 -->

<!-- 副标题 -->
<div class="h-sub">本章节从三个维度分析市场趋势</div>   <!-- 副标题，opacity .7 -->

<!-- 中等标题 -->
<div class="h-md">数据来源与方法论</div>            <!-- 章节内小标题 -->

<!-- 超大字装饰 -->
<div class="display">VISION</div>                  <!-- 英文 display 字 -->
<div class="display-zh">愿景</div>                  <!-- 中文 display 字 -->
```

### 2.3 正文层级使用场景

```html
<!-- 导语/引言（字号较大） -->
<div class="lead">这是一句概括性导语，用于页面顶部的核心摘要。建议不超过 40 字。</div>

<!-- 中文正文（标准） -->
<div class="body-zh">正文内容，适合较长的叙述性文字。每段建议控制在 80 字以内，避免信息过载。</div>

<!-- 衬线正文（更有阅读感） -->
<div class="body-serif">使用衬线体呈现正文，带来更强的文学感和阅读节奏。适合人文类内容。</div>

<!-- 元数据行 -->
<div class="meta">2026-05-05 / PENG / RESEARCH</div>

<!-- 元数据行（flex 排列，用 · 分隔） -->
<div class="meta-row">
  <span>张三</span><span>·</span><span>高级研究员</span><span>·</span><span>2026.05</span>
</div>
```

### 2.4 内联样式

```html
<!-- 英文斜体（在中文上下文中） -->
<p class="body-zh">这个概念在英文中称为<span class="en">Serendipity</span>，意指意外发现。</p>

<!-- 强调（自动渲染为 italic + --font-display） -->
<p class="body-zh">这是本季度<em>最重要</em>的发现。</p>
```

---

## 3. Chrome & Foot（顶部/底部元数据栏）

### Chrome（顶部栏）

```html
<div class="chrome">
  <div class="left">
    <span>{机构/章节名}</span>
    <span class="sep"></span>
    <span>{日期/版本}</span>
  </div>
  <div class="right">
    <span>{页码} / {总页数}</span>
  </div>
</div>
```

**规则**：
- `.sep` 渲染为一条 40px 宽、1px 高的横线分隔符
- 字体始终是 `--font-mono`，字号 `max(11px, 0.78vw)`
- 左侧放上下文信息，右侧放页码或标签
- 封面页通常省略页码

### Foot（底部栏）

```html
<div class="foot">
  <span>{页码} / {总页数}</span>
  <span class="title">{短标题}</span>
</div>
```

**规则**：
- `.foot .title` 使用 `--font-headline-zh`（与正文标题一致），字号 13px，opacity .75
- 左侧放页码，右侧放幻灯片简称
- foot 在 shell 中通过 `margin-top: auto` 自动沉底

---

## 4. Kicker（标题上方小标签）

```html
<div class="kicker">QUARTERLY REVIEW</div>
<div class="h-xl">Q2 业绩回顾</div>
```

**规则**：
- 字体 `--font-mono`，字号 `max(11px, 0.78vw)`
- 字母间距 `.3em`，全大写
- opacity .6
- 下方 `margin-bottom: 2.6vh`
- 通常与 `.h-xl` 或 `.h-hero` 配对使用

---

## 5. Stat Card（数据指标卡片）

### 标准 Stat Card（用于 .grid-6 或 .grid-4）

```html
<div class="stat-card">
  <div class="stat-label">MONTHLY ACTIVE USERS</div>
  <div class="stat-nb">12.8<span class="stat-unit">M</span></div>
  <div class="stat-note">同比增长 32%，创历史新高</div>
</div>
```

**三件套必须齐全**：
1. `.stat-label` — 指标名称（全大写、等宽、opacity .55）
2. `.stat-nb` — 大数字（`--font-display`、800 字重、带 `.stat-unit` 单位）
3. `.stat-note` — 说明文字（中文字体、opacity .72）

### 旧式大数字（用于更自由的布局）

```html
<div class="stat">
  <div class="m">REVENUE GROWTH</div>   <!-- meta 标签 -->
  <div class="n">286<span class="stat-unit">%</span></div>  <!-- 大数字 -->
  <div class="l">较去年同期的营收增幅，超过行业平均水平 2.3 倍</div>  <!-- 描述 -->
</div>
```

**差异**：
- `.stat .n` 使用 `font-size: 8vw`（比 stat-nb 的 5.8vw 更大）
- `.stat .l` 使用中文字体，`font-size: max(13px, 1.05vw)`
- `.stat .m` 与 `.stat-label` 类似但字号更小

### 在网格中使用

```html
<div class="frame grid-6">
  <div class="stat-card" data-anim>
    <div class="stat-label">ACTIVE USERS</div>
    <div class="stat-nb">1.2<span class="stat-unit">M</span></div>
    <div class="stat-note">月活跃用户数</div>
  </div>
  <!-- 重复 × 6 -->
</div>
```

`.grid-4 .stat-card .stat-nb` 的字号会自动缩小到 `5vw`。
`.grid-3 .stat-card .stat-nb` 的字号会自动缩小到 `6.8vw`。

---

## 6. Callout（引用/洞察框）

```html
<div class="callout">
  <div class="q-big">"技术的真正价值不在于它有多先进，而在于它解决了什么问题。"</div>
  <span class="callout-src">— 《人月神话》Fred Brooks</span>
</div>
```

**结构**：
- `.callout` — 容器（左边框 3px、padding、半透明背景）
  - 浅色页：`background: rgba(var(--ink-rgb), .05)`
  - 深色页：`background: rgba(var(--paper-rgb), .06)`
- `.q-big` — 引用文字（`--font-headline-zh`、600 字重、`font-size: max(17px, 1.6vw)`）
- `.callout-src` — 来源标注（等宽、11px、全大写）

**使用注意**：
- 不嵌套过深（不要 callout 内再 callout）
- 引用语控制在 30 字以内
- `.q-big` 可选，省略则使用 callout 自己的文字大小

---

## 7. Pipeline（流水线）

### 标准 5 步流水线

```html
<div class="pipeline" data-cols="5">
  <div class="step" data-anim="step">
    <div class="step-nb">01</div>
    <div class="step-title">需求分析</div>
    <div class="step-desc">收集并分析用户需求</div>
  </div>
  <div class="step" data-anim="step">
    <div class="step-nb">02</div>
    <div class="step-title">方案设计</div>
    <div class="step-desc">制定技术方案与架构</div>
  </div>
  <div class="step" data-anim="step">
    <div class="step-nb">03</div>
    <div class="step-title">开发实现</div>
    <div class="step-desc">迭代开发与单元测试</div>
  </div>
  <div class="step" data-anim="step">
    <div class="step-nb">04</div>
    <div class="step-title">质量验证</div>
    <div class="step-desc">集成测试与性能压测</div>
  </div>
  <div class="step" data-anim="step">
    <div class="step-nb">05</div>
    <div class="step-title">上线发布</div>
    <div class="step-desc">灰度发布与全量上线</div>
  </div>
</div>
```

**组件层次**：
- `.pipeline` — 容器，`grid-template-columns: repeat(N, 1fr)`
- `data-cols` — 列数（3/4/5/6，默认 5）
- `.step` — 单步（上边框 1px 分隔）
- `.step-nb` — 步骤号（`--font-display` italic、opacity .45）
- `.step-title` — 步骤��称（700 字重、`1.55vw`）
- `.step-desc` — 步骤描述（opacity .72）

### 多阶段流水线

```html
<div class="pipeline-section">
  <div class="pipeline-label">Phase 1: Foundation</div>
  <div class="pipeline" data-cols="3">
    <div class="step" data-anim="step">
      <div class="step-nb">01</div>
      <div class="step-title">...</div>
      <div class="step-desc">...</div>
    </div>
    <!-- ×3 -->
  </div>
</div>

<div class="pipeline-section">
  <div class="pipeline-label">Phase 2: Growth</div>
  <div class="pipeline" data-cols="3">
    <div class="step" data-anim="step">
      <div class="step-nb">04</div>
      <!-- ... -->
    </div>
    <!-- ×3 -->
  </div>
</div>
```

**动画**：
- section 级 `data-animate="pipeline"`
- 空格键或右箭头逐步展开（`window.__pipeAdvance()`）
- `data-anim="step"` 标记步骤（初始 opacity .15）
- 可选 `data-anim="arrow"` 做步骤间箭头（不需要实际元素，JS 会处理）

---

## 8. Rowline（表格行）

```html
<div class="rowline">
  <div class="k">关键指标</div>
  <div class="v">指标具体的数值或描述，可以是较长的说明文字</div>
  <div class="m">2026</div>
</div>
```

**结构**：
- `.rowline` — 行容器（`grid-template-columns: 1fr 2fr 1fr`，gap 2vw）
- `.k` — 键/名称（`--font-headline-zh`、700 字重、`1.7vw`）
- `.v` — 值/描述（`--font-body-zh`、opacity .85）
- `.m` — 元数据/日期（`--font-mono`、靠右对齐 `justify-self: end`）

**使用场景**：
- 时间线里程碑
- 对比表
- 术语定义
- 参数列表

**多行**：
```html
<div class="rowline">...</div>
<div class="rowline">...</div>
<div class="rowline">...</div>
```
每行之间有 `border-top: 1px solid` 分隔，最后一行有 `border-bottom`。

---

## 9. Pillar（概念支柱卡）

```html
<div class="pillar">
  <div class="ic">
    <i data-lucide="layers" class="ico-lg"></i>
  </div>
  <div class="t">模块化架构</div>
  <div class="d">核心系统采用微服务架构，每个模块独立部署和扩展，提升开发效率和系统弹性。</div>
</div>
```

**结构**：
- `.pillar` — 容器（flex column、gap 1.8vh）
- `.ic` — 图标区（`--font-display` italic、或 Lucide SVG）
- `.t` — 标题（`--font-headline-zh`、700 字重、`2.4vw`）
- `.d` — 描述（`--font-body-zh`、opacity .76）

**在网格中使用**：
```html
<div class="grid-3">
  <div class="pillar" data-anim>...</div>
  <div class="pillar" data-anim>...</div>
  <div class="pillar" data-anim>...</div>
</div>
```

---

## 10. Platform Card（平台指标卡）

```html
<div class="plat">
  <div class="name">iOS</div>
  <div class="nb">4.8<span style="font-family:var(--font-headline-zh);font-weight:500;font-size:.45em;opacity:.72;margin-left:.14em">分</span></div>
  <div class="sub">APP STORE RATING</div>
  <div class="fill">★★★★★</div>
</div>
```

**结构**：
- `.plat` — 容器（底部对齐 flex、上边框分隔）
- `.name` — 平台名（`--font-headline-zh`、700 字重、`1.8vw`）
- `.nb` — 大数字（`--font-display`、700 字重、`3.2vw`）
- `.sub` — 标签（等宽、10px、全大写）
- `.fill` — 装饰填充（`--font-body-zh`、300 字重、`2.4vw`、opacity .28）

**典型布局（4 平台卡）**：
```html
<div class="grid-4">
  <div class="plat" data-anim>...</div>
  <div class="plat" data-anim>...</div>
  <div class="plat" data-anim>...</div>
  <div class="plat" data-anim>...</div>
</div>
```

---

## 11. Tag & Rule（内联标签和分割线）

### Tag

```html
<span class="tag">BETA</span>
<span class="tag">2026</span>
```

- 等宽字体、11px、字母间距 .24em、全大写
- 内联 block、padding 6px 14px、1px 实线边框
- opacity .85

### Rule（横线）

```html
<div class="rule"></div>
```
- 全宽、1px 高、背景 currentColor、opacity .25
- 上下 margin 3vh

### Rule Vertical（竖线）

```html
<div class="rule v"></div>
```
- 1px 宽、100% 高
- 用在二分对比布局中作为分隔

```html
<!-- 对比布局中的竖分隔 -->
<div class="grid-2-6-6">
  <div class="col">...</div>
  <div class="rule v" data-anim="divider" style="justify-self:center;height:60%"></div>
  <div class="col">...</div>
</div>
```

---

## 12. Figure/Image（图片系统）

### 标准图片（带宽高比约束）

```html
<figure class="frame-img r-16x9">
  <img src="images/03-architecture.jpg" alt="系统架构图">
  <figcaption class="frame-cap">
    <span class="pf">图 1：系统架构总览</span>
    <span class="nb">V3.2</span>
  </figcaption>
</figure>
```

### 图片尺寸速查

| 类名 | 效果 | 适合场景 |
|------|------|----------|
| `.r-16x9` | `aspect-ratio: 16/9; max-height: 64vh` | 横图、封面图、全宽图 |
| `.r-16x10` | `aspect-ratio: 16/10; max-height: 56vh` | 略窄横图 |
| `.r-4x3` | `aspect-ratio: 4/3; max-height: 56vh` | 标准插图 |
| `.r-3x2` | `aspect-ratio: 3/2; max-height: 46vh` | 紧凑横图 |
| `.r-3x4` | `aspect-ratio: 3/4; max-height: 60vh` | 竖图、图文混排 |
| `.r-1x1` | `aspect-ratio: 1/1; max-height: 50vh` | 正方形图 |

### 固定高度（用于网格）

| 类名 | 高度 |
|------|------|
| `.h-16` | `16vh` |
| `.h-18` | `18vh` |
| `.h-22` | `22vh` |
| `.h-26` | `26vh` |
| `.h-28` | `28vh` |

### **CRITICAL：网格中的图片必须使用固定高度**

```html
<!-- 正确：在 grid 中使用 h-{n} + r-{ratio} -->
<div class="grid-3-3">
  <figure class="tile">
    <div class="frame-img h-22 r-4x3">
      <img src="images/04-img1.jpg" alt="...">
    </div>
    <figcaption class="frame-cap"><span class="pf">标题</span></figcaption>
  </figure>
</div>

<!-- 错误：在 grid 中只用 aspect-ratio（会与 1fr 行高冲突） -->
<div class="grid-3-3">
  <div class="frame-img r-16x9">  <!-- 不要这样做 -->
    <img src="...">
  </div>
</div>
```

### contain 模式

```html
<div class="frame-img r-4x3 fit-contain">
  <img src="images/logo.png" alt="Logo">
</div>
```
- 添加 `.fit-contain` 使图片完整显示而不会被裁切
- 适用于 Logo、图表等需要完整显示的图片

### FIGURE 标签

```html
<!-- 作为 tile（网格中） -->
<figure class="tile">
  <div class="frame-img h-22 r-4x3">
    <img src="..." alt="...">
  </div>
  <figcaption class="frame-cap">...</figcaption>
</figure>

<!-- 作为独立图片 -->
<figure class="frame-img r-16x9">
  <img src="..." alt="...">
</figure>
```

---

## 13. Icon（Lucide 图标）

### 规则：禁止 Emoji，只用 Lucide

所有图标使用 [Lucide](https://lucide.dev/icons/) 图标集。

```html
<!-- 标准图标（内联） -->
<i data-lucide="zap" class="ico"></i>

<!-- 大图标（独立展示） -->
<i data-lucide="cpu" class="ico-lg"></i>

<!-- 中图标（段落中） -->
<i data-lucide="info" class="ico-md"></i>

<!-- 小图标（装饰） -->
<i data-lucide="external-link" class="ico-sm"></i>
```

### 图标尺寸

| 类 | 尺寸 | 描边宽度 | 用途 |
|----|------|----------|------|
| `.ico` | 1em | 1.4 | 行内图标，随文字大小 |
| `.ico-lg` | 2.6vw | 1.2 | 独立展示（pillar、hero） |
| `.ico-md` | 1.8vw | 1.3 | 段落内强调 |
| `.ico-sm` | 1.1vw | 1.4 | 装饰/标记、opacity .7 |

### 常用图标速查

| 场景 | Lucide 图标名 |
|------|--------------|
| 速度/性能 | `zap` |
| 增长/上升 | `trending-up` |
| 安全/保护 | `shield` |
| 数据/分析 | `bar-chart-3` |
| 目标/精准 | `target`、`crosshair` |
| 时间/历史 | `clock` |
| 用户/人 | `users`、`user` |
| 设置/工具 | `settings`、`wrench` |
| 搜索/发现 | `search`、`compass` |
| 文档/文件 | `file-text` |
| 链接/连接 | `link` |
| 地球/全球 | `globe` |
| 星/评分 | `star` |
| 心/喜欢 | `heart` |
| 箭头/方向 | `arrow-right`、`arrow-up-right` |
| 检查/确认 | `check`、`check-circle` |
| 警告/注意 | `alert-triangle` |
| 灯泡/想法 | `lightbulb` |
| 代码/开发 | `code-2`、`terminal` |
| 层/架构 | `layers` |
| 云/云端 | `cloud` |
| 锁/安全 | `lock` |
| 数据库 | `database` |
| 消息/对话 | `message-circle` |

**页尾必须调用**：
```html
<script>lucide.createIcons();</script>
```
（模板已包含此调用，无需重复添加。）

---

## 14. Ghost（巨型背景装饰文字）

```html
<div class="ghost" style="right:-6vw;bottom:-12vh;font-size:40vw">03</div>
```

**属性**：
- 绝对定位（需自行设置 top/right/bottom/left）
- `--font-display`、900 字重
- `font-size: 34vw`（默认，可覆盖）
- `opacity: .06`
- `letter-spacing: -.04em`
- 无 pointer-events（不可交互，纯装饰）

**使用场景**：
- 章节号作为水印
- 关键词作为背景氛围
- 数字装饰

**注意**：
- 必须设置 `position`（inline style 或单独 class）
- 超出页面边缘是设计意图（用负值 right/bottom 实现部分裁切）
- 深色页和浅色页中颜色自动适配（因为是 currentColor 继承）

---

## 15. Highlight（内联高亮标记）

```html
<p class="body-zh">
  这是本季度<span class="hi">最重要的发现</span>，它改变了我们对市场的认知。
</p>
```

**效果**：
- 浅色页：文字下方出现 `rgba(var(--ink-rgb), .08)` 背景色块（`.28em` 高）
- 深色页：文字下方出现 `rgba(var(--paper-rgb), .15)` 背景色块

**注意**：
- `.hi` 依赖 `::after` 伪元素，需要 `position: relative`（类中已处理）
- 高亮宽度自动匹配文字（`left: -.1em; right: -.1em`）
- 仅高亮短文本（≤ 10 字），长文本高亮效果差

---

## 16. Image Slot（图片占位符）

当图片尚未准备好时使用。

```html
<div class="img-slot">
  <span class="plus">+</span>
  <span class="label">INSERT IMAGE<br>16:9 · ≥1600px WIDE</span>
</div>
```

**变体（不同比例）**：
```html
<div class="img-slot r-4x3">...</div>
<div class="img-slot r-3x2">...</div>
<div class="img-slot r-1x1">...</div>
```

**注意**：
- 虚线边框（1.5px dashed）
- 内部虚线（`::before` 伪元素、1px solid、inset 8px）
- 正式交付时所有 `.img-slot` 必须替换为实际 `<img>`
- 在 checklist 中会检查（P0-1：无占位符残留）

---

## 17. Motion Animation（动效系统）

### data-anim 属性

| 值 | 初始状态（motion-ready 时） | 动画效果 |
|----|---------------------------|----------|
| `left` | `opacity: 0; translateX(-24px)` | 从左侧飞入 |
| `right` | `opacity: 0; translateX(24px)` | 从右侧飞入 |
| `line` | `opacity: 0; translateY(10px)` | 从下方淡入 |
| `step` | `opacity: .15` | 逐步揭示 |
| `arrow` | `opacity: .15` | 箭头出现 |
| `divider` | 无特殊初始状态 | 分隔线淡入 |
| 无值 | `opacity: 0` | 默认从下方淡入 |

### data-animate（Section 级动画配方）

| 配方 | 效果 | 适用场景 |
|------|------|----------|
| `cascade`（默认） | 所有 `[data-anim]` 元素依次从下方淡入（stagger .1s） | 通用内容页 |
| `hero` | 所有元素一起从下方淡入（stagger .16s，duration .9s） | 封面、章节分隔 |
| `quote` | line 元素逐行淡入（stagger .55s），其他先入（stagger .12s） | 引用页 |
| `directional` | left 元素先入 → divider 第二 → right 元素最后入 | 对比、图文混排 |
| `pipeline` | 渐进式逐步揭示，空格键/右箭头驱动 | 流程展示 |

### 使用范例

**Cascade（通用内容页）**：
```html
<section class="slide light" data-animate="cascade">
  <div class="h-xl" data-anim>标题先出现</div>
  <div class="body-zh" data-anim>正文随后出现</div>
  <div class="body-zh" data-anim>更多内容再出现</div>
</section>
```

**Directional（图文对比）**：
```html
<section class="slide light" data-animate="directional">
  <div class="col" data-anim="left">左侧内容先入</div>
  <div class="rule v" data-anim="divider"></div>
  <div class="col" data-anim="right">右侧内容后入</div>
</section>
```

**Pipeline（步骤展示）**：
```html
<section class="slide light" data-animate="pipeline">
  <div class="step" data-anim="step">步骤 1</div>
  <div class="step" data-anim="step">步骤 2</div>
  <div class="step" data-anim="step">步骤 3</div>
</section>
```

### 动画系统注意事项

1. `body.motion-ready` 类在 Motion One 库成功加载后自动添加
2. 如果 Motion One 加载失败（本地 CDN + 远程 CDN 均失败），所有 `[data-anim]` 元素恢复为 `opacity: 1`，动画降级为静态展示
3. 页面切换动画默认 450ms 后触发当前页动画（等待翻页过渡完成）
4. Pipeline 动画的 `window.__pipeAdvance()` 只在当前 active slide 是 pipeline 类型时才生效
5. 不支持自定义动画时间线 — 所有时间参数由 recipe 固定
6. 每个 `[data-anim]` 元素的动画只播放一次（页面切入时），不会在页面间重复触发
