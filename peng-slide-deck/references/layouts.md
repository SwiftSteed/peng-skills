# HTML 布局模板库

> 在 Step 5（生成 HTML）时使用。每个模板是可直接粘贴到 `<div id="deck">` 中的完整 `<section>` 块。
> 模板中 `{...}` 为占位符，生成时替换为实际内容。

---

## Pre-flight：CSS 类速查表

生成 HTML 前，确认所有使用的 CSS 类在模板 `<style>` 中有定义。以下是 class 完整清单：

### 标题层级
| 类名 | 用途 | 字体族 | 字重 |
|------|------|--------|------|
| `.h-hero` | 封面超大标题（中文） | --font-headline-zh | 900 |
| `.h-hero-en` | 封面超大标题（英文） | --font-display | 800 |
| `.h-xl` | 页面大标题（中文） | --font-headline-zh | 700 |
| `.h-xl-en` | 页面大标题（英文） | --font-display | 700 |
| `.h-sub` | 副标题 | --font-headline-zh | 500 |
| `.h-md` | 中等标题 | --font-headline-zh | 600 |
| `.display` | 超大展示英文 | --font-display | 800 |
| `.display-zh` | 超大展示中文 | --font-headline-zh | 900 |
| `.kicker` | 标题上方小标签 | --font-mono | 400 |

### 正文层级
| 类名 | 用途 | 字体族 |
|------|------|--------|
| `.lead` | 导语/引言 | --font-headline-zh |
| `.body-zh` | 中文正文 | --font-body-zh |
| `.body-serif` | 衬线正文 | --font-headline-zh |
| `.meta` | 元数据/日期/标签 | --font-mono |
| `.meta-row` | 元数据行（flex） | --font-mono |
| `.en` | 内联英文斜体 | --font-display |
| `em` | 内联强调斜体 | --font-display |

### 数字
| 类名 | 用途 |
|------|------|
| `.big-num` | 超大数字（10vw） |
| `.mid-num` | 中等数字（5.5vw） |
| `.ghost` | 巨型背景数字/水印 |

### 布局网格
| 类名 | 列模式 | 用途 |
|------|--------|------|
| `.grid-2-7-5` | 7:5 两列 | 左大右小（图文混排） |
| `.grid-2-6-6` | 1:1 两列 | 等宽两栏对比 |
| `.grid-2-8-4` | 8:4 两列 | 左宽右窄（文字+配图） |
| `.grid-3` | 3 等列 | 三栏内容、并列要点 |
| `.grid-3-3` | 3 等列 auto-rows 1fr | 图片网格、3 列卡片 |
| `.grid-4` | 2×2 四格 | Dashboard、指标卡片 |
| `.grid-6` | 3×2 六格 | 数据大字报、多指标 |
| `.grid-9` | 3×3 九格 | 图标矩阵、功能展示 |

### 布局工具
| 类名 | 用途 |
|------|------|
| `.frame` | Flex 主内容容器 |
| `.col` | 垂直列（flex column） |
| `.row` | 水平行（flex row） |
| `.fill` | flex:1 填充 |
| `.center` | 居中内容 |
| `.split` | 1:1 两列 Flex |
| `.split-55` | 55:45 两列 Flex |
| `.bottom-left` | 绝对定位左下 |
| `.bottom-right` | 绝对定位右下 |
| `.top-right` | 绝对定位右上 |

### 组件
| 类名 | 用途 |
|------|------|
| `.chrome` | 顶部元数据栏（.left / .right / .sep） |
| `.foot` | 底部页脚（.title 显示标题） |
| `.stat-card` / `.stat-label` / `.stat-nb` / `.stat-unit` / `.stat-note` | 数据卡片 |
| `.stat` / `.n` / `.l` / `.m` | 大数字（旧式，用于 .grid-6） |
| `.callout` / `.callout-src` / `.q-big` | 引用/洞察框 |
| `.pipeline` / `.pipeline-section` / `.pipeline-label` | 流水线容器 |
| `.step` / `.step-nb` / `.step-title` / `.step-desc` | 步骤条目 |
| `.rowline` / `.k` / `.v` / `.m` | 表格行 |
| `.pillar` / `.ic` / `.t` / `.d` | 支柱概念卡 |
| `.plat` / `.name` / `.nb` / `.sub` / `.fill` | 平台指标卡 |
| `.tag` | 内联标签 |
| `.rule` | 分割线（.v 为竖线） |

### 图片
| 类名 | 用途 |
|------|------|
| `.frame-img` | 图片容器（需搭配比例类） |
| `.frame-img > img` | 图片标签（object-fit:cover） |
| `.r-16x9` / `.r-16x10` / `.r-4x3` / `.r-3x2` / `.r-3x4` / `.r-1x1` | 宽高比（via aspect-ratio） |
| `.h-16` / `.h-18` / `.h-22` / `.h-26` / `.h-28` | 固定高度 |
| `.frame-cap` / `.img-cap` | 图片标题行 |
| `.img-slot` | 图片占位符（虚线框） |
| `.fit-contain` | 图片 contain 模式 |

### 图标
| 类名 | 用途 |
|------|------|
| `.ico` | 基础图标（1em） |
| `.ico-lg` | 大图标（2.6vw） |
| `.ico-md` | 中图标（1.8vw） |
| `.ico-sm` | 小图标（1.1vw） |

### 效果
| 类名 | 用途 |
|------|------|
| `.hi` | 内联高亮（下划线强调） |
| `.sign` | 手写签名风格 |
| `.ghost` | 巨型装饰文字 |

### 特殊布局
| 类名 | 用途 |
|------|------|
| `.layout-icon-grid` / `.icon-item` / `.icon-label` | 图标网格 |

### Slide 修饰符
| 类名 | 作用 |
|------|------|
| `slide.light` | 浅色底页 |
| `slide.dark` | 深色底页 |
| `slide.hero` | Hero 模式（减遮罩、透 WebGL） |
| `slide::after.texture` | 启���纹理叠加 |

### 动画属性
| 属性 | 值 | 说明 |
|------|-----|------|
| `data-anim` | `left` / `right` / `line` / `step` / `arrow` / `divider` | 动画方向标识 |
| `data-animate` | `cascade` / `hero` / `quote` / `directional` / `pipeline` | 动画配方（section 级） |
| `data-cols` | `3` / `4` / `6` | 流水线列数（默认 5） |

---

## 主题节奏规划（必须遵守）

### 硬性规则

1. **禁止 3 页及以上连续使用同一 theme 模式**
   - 即 `.light` → `.light` → `.dark`：允许
   - `.light` → `.light` → `.light`：禁止
   - `.dark` → `.dark` → `.dark`：禁止
   - `.hero.dark` → `.hero.light` → `.hero.dark`：允许（hero 是特殊模式）

2. **8 页以上的 slide deck 必须同时包含至少一个 hero dark 和一个 hero light**
   - 封面用 `.hero.dark`
   - 封底可用 `.hero.light` 或 `.hero.dark`
   - 中间过渡页与封面/封底交替

3. **深色内容页之后必须接浅色页**
   - `.dark`（内容页）→ `.light`（内容页）：必须
   - 即 dark 内容页不能连续出现

4. **每 3-4 页插入一个 hero 页作为视觉休止符**
   - 主题节奏理想模式：
     ```
     01 hero dark (封面)
     02 light (内容)
     03 light (内容) 
     04 hero light (过渡)
     05 dark (内容)
     06 light (内容)
     07 light (内容)
     08 hero dark (过渡/亮点)
     09 light (内容)
     10 light (内容)
     11 light (内容)
     12 hero dark (封底)
     ```

5. **主题分派速查**

   | 幻灯片类型 | theme class | 说明 |
   |-----------|-------------|------|
   | 封面 (Cover) | `slide hero dark` | 深色 hero |
   | 章节分隔 (Chapter Divider) | `slide hero light` 或 `slide hero dark` | 与封面交替 |
   | 内容页 (Content) | `slide light` 或 `slide dark` | 主要 light |
   | 数据大字报 (Stat Grid) | `slide light` | 数据需要清晰可见 |
   | 大引用 (Big Quote) | `slide hero dark` | 引语需要沉浸感 |
   | 封底 (Back Cover) | `slide hero dark` 或 `slide hero light` | 与封面不同 |

---

## 图片约定

### 宽高比准则

- 封面/封底图片使用 16:9（`.r-16x9`）
- 页面内插图使用与布局匹配的比例
- 图片网格中的多图统一比例（推荐 4:3 或 3:2）
- `<img>` 使用 `object-fit: cover`，`object-position: top center`

### 固定高度 vs aspect-ratio

- **网格布局中**：使用 `.h-16` 到 `.h-28` 固定高度类，不使用 `aspect-ratio` 类
  - 理由：网格中 `aspect-ratio` 会与 `1fr` 行高冲突，产生不可预测的布局
- **独立图片（非网格）**：使用 `.r-16x9` 等 aspect-ratio 类

### 图片对齐规则

- **禁止 `align-self: end`**：图片不会贴底
- 网格容器（`.grid-3-3`、`.grid-6` 等）默认 `align-items: stretch`，图片会被拉伸填充
- 如需图片居中，在 `figure` 或 `.frame-img` 上使用 `align-self: center`
- 全幅背景图使用 `object-fit: cover; object-position: center;`

---

## 布局模板

### 1. title-hero（封面）

深色 Hero 页，大标题居中。适用于幻灯片第 1 页。

```html
<section class="slide hero dark">
  <div class="chrome">
    <div class="left"><span>{机构名}</span><span class="sep"></span><span>{日期}</span></div>
    <div class="right"><span>{标签}</span></div>
  </div>
  <div class="frame center">
    <div class="kicker">{上方小标签：如 "QUARTERLY REVIEW"}</div>
    <div class="h-hero">{中文主标题}</div>
    <div class="h-hero-en" style="margin-top:1vh;opacity:.68">{English Subtitle}</div>
    <div class="h-sub" style="margin-top:4vh;max-width:56vw">{副标题或一句话描述，≤ 30 字}</div>
    <div class="meta-row" style="margin-top:5vh">
      <span>{演讲者}</span><span>·</span><span>{角色}</span><span>·</span><span>{日期}</span>
    </div>
  </div>
  <div class="foot">
    <span>01 / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- `h-hero` 放中文主标题，`h-hero-en` 放英文翻译
- `kicker` 可选，放分类标签
- 如果只有一种语言，省略对应的标题行
- `foot .title` 放幻灯片简称

**变体：纯中文封面**

```html
<section class="slide hero dark">
  <div class="chrome">
    <div class="left"><span>{机构名}</span><span class="sep"></span><span>{日期}</span></div>
    <div class="right"><span>{01} / {总页数}</span></div>
  </div>
  <div class="frame center">
    <div class="kicker">{上方小标签}</div>
    <div class="h-hero">{主标题}</div>
    <div class="lead" style="margin-top:3vh;max-width:50vw;text-align:center">{一句话副标题}</div>
    <div class="meta" style="margin-top:6vh">{演讲者} / {角色} / {日期}</div>
  </div>
</section>
```

---

### 2. section-divider（章节分隔页）

章节过渡页，作为内容分组的视觉休止符。与封面交替使用 light/dark。

```html
<section class="slide hero light">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame center">
    <div class="kicker">PART {N}</div>
    <div class="h-hero" style="font-size:7.2vw">{章节标题}</div>
    <div class="h-sub" style="margin-top:2vh;max-width:46vw">{本章节一句话摘要}</div>
    <div class="rule" style="width:12vw;margin:4vh auto 0"></div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- 封面是 `.hero.dark` 时，第一个分隔页用 `.hero.light`
- 第二个分隔页用 `.hero.dark`，依此类推
- 分隔页也可以使用 `ghost` 元素做背景装饰：
  ```html
  <div class="ghost" style="right:-6vw;bottom:-10vh;font-size:40vw">{章节号}</div>
  ```

**变体：暗色分隔页**

```html
<section class="slide hero dark">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame center">
    <div class="kicker">PART {N}</div>
    <div class="h-hero">{章节标题}</div>
    <div class="h-sub" style="margin-top:2vh;max-width:46vw;opacity:.6">{本章节一句话摘要}</div>
    <div class="rule" style="width:12vw;margin:4vh auto 0;opacity:.3"></div>
  </div>
</section>
```

---

### 3. stat-grid（数据大字报 · Big Numbers）

3 列 × 2 行六格数据卡片。使用 `.grid-6` + `.stat-card` 组件。

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame grid-6">
    <div class="stat-card" data-anim>
      <div class="stat-label">Metric Label 1</div>
      <div class="stat-nb">86<span class="stat-unit">%</span></div>
      <div class="stat-note">一行简短说明数据含义</div>
    </div>
    <div class="stat-card" data-anim>
      <div class="stat-label">Metric Label 2</div>
      <div class="stat-nb">24<span class="stat-unit">×</span></div>
      <div class="stat-note">对比基线提升倍数</div>
    </div>
    <div class="stat-card" data-anim>
      <div class="stat-label">Metric Label 3</div>
      <div class="stat-nb">3.2<span class="stat-unit">M</span></div>
      <div class="stat-note">覆盖用户规模</div>
    </div>
    <div class="stat-card" data-anim>
      <div class="stat-label">Metric Label 4</div>
      <div class="stat-nb">99.9<span class="stat-unit">%</span></div>
      <div class="stat-note">服务可用性 SLA</div>
    </div>
    <div class="stat-card" data-anim>
      <div class="stat-label">Metric Label 5</div>
      <div class="stat-nb">45<span class="stat-unit">min</span></div>
      <div class="stat-note">平均响应时间</div>
    </div>
    <div class="stat-card" data-anim>
      <div class="stat-label">Metric Label 6</div>
      <div class="stat-nb">12<span class="stat-unit">个</span></div>
      <div class="stat-note">落地国家/地区数量</div>
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- 每个 `.stat-card` 必有三件套：`stat-label`（标签）+ `stat-nb`（数字）+ `stat-note`（说明）
- `.stat-unit` 放单位（%、×、M、min 等），会缩小显示
- 必须用 `light` 主题（数据在深色背景上可读性差）
- 带 `data-animate="cascade"` 实现逐条动画入场

**变体：4 格 Dashboard（.grid-4）**

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame grid-4">
    <div class="stat-card" data-anim>
      <div class="stat-label">DAU</div>
      <div class="stat-nb">1.2<span class="stat-unit">M</span></div>
      <div class="stat-note">同比增长 28%</div>
    </div>
    <!-- 重复 ×4 -->
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

---

### 4. split-screen（左文右图 · Quote + Image）

左侧文字内容（可以是 quote、要点列表或叙述段落），右侧配图。使用 `.grid-2-7-5`。

```html
<section class="slide light" data-animate="directional">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame grid-2-7-5">
    <div class="col" style="justify-content:center">
      <div class="h-xl" data-anim="left">{标题}</div>
      <div class="body-zh" style="margin-top:2.8vh" data-anim="left">{正文内容，可以是一段或多段。保持信息密度适中，不超过 120 字。</div>
      <div class="callout" style="margin-top:3vh" data-anim="left">
        <div class="q-big">{核心洞察或引用语句}</div>
        <span class="callout-src">— {来源 / 人名}</span>
      </div>
    </div>
    <figure class="frame-img r-3x4" data-anim="right">
      <img src="images/{页码}-{语义}.jpg" alt="{描述}">
      <figcaption class="frame-cap"><span>{图注}</span></figcaption>
    </figure>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- 左侧 7 份宽、右侧 5 份宽（`.grid-2-7-5`）
- 文字侧用 `data-anim="left"`，图片侧用 `data-anim="right"`
- 可以 `.r-3x4` 竖图或 `.r-16x9` 横图
- 如需左图右文：交换 `<div class="col">` 和 `<figure>` 的位置即可

---

### 5. image-grid（图片网格）

3 列图片对比。统一比例，使用 `.h-22` 或 `.h-26` 固定高度（不用 aspect-ratio 类）。

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame">
    <div class="h-xl" data-anim style="margin-bottom:2vh">{总标题}</div>
    <div class="grid-3-3">
      <figure class="tile" data-anim>
        <div class="frame-img h-22 r-4x3">
          <img src="images/{页码}-img1.jpg" alt="{描述}">
        </div>
        <figcaption class="frame-cap"><span class="pf">{项目名 A}</span></figcaption>
      </figure>
      <figure class="tile" data-anim>
        <div class="frame-img h-22 r-4x3">
          <img src="images/{页码}-img2.jpg" alt="{描述}">
        </div>
        <figcaption class="frame-cap"><span class="pf">{项目名 B}</span></figcaption>
      </figure>
      <figure class="tile" data-anim>
        <div class="frame-img h-22 r-4x3">
          <img src="images/{页码}-img3.jpg" alt="{描述}">
        </div>
        <figcaption class="frame-cap"><span class="pf">{项目名 C}</span></figcaption>
      </figure>
      <!-- 如果是 6 张图，再加一行 -->
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**关键规则**：
- 在 `grid-3-3` 中，`frame-img` 同时使用 `h-{n}` 类和 `r-{ratio}` 类
  - `h-{n}` 控制高度（grid 需要确定的尺寸）
  - `r-{ratio}` 控制宽高比（作为 fallback）
- 统一同一 page 内所有图片的比例和高度
- `figure.tile` 包裹图片 + 说明

---

### 6. pipeline（流水线 / 步骤流程）

5 步流程（默认），支持 3/4/6 步变体。使用 `.pipeline` + `.step`。

```html
<section class="slide light" data-animate="pipeline">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame">
    <div class="h-xl" style="margin-bottom:2vh">{流程总标题}</div>
    <div class="pipeline" data-cols="5">
      <div class="step" data-anim="step">
        <div class="step-nb">01</div>
        <div class="step-title">步骤一标题</div>
        <div class="step-desc">简短描述，10-15 字</div>
      </div>
      <div class="step" data-anim="step">
        <div class="step-nb">02</div>
        <div class="step-title">步骤二标题</div>
        <div class="step-desc">简短描述</div>
      </div>
      <div class="step" data-anim="step">
        <div class="step-nb">03</div>
        <div class="step-title">步骤三标题</div>
        <div class="step-desc">简短描述</div>
      </div>
      <div class="step" data-anim="step">
        <div class="step-nb">04</div>
        <div class="step-title">步骤四标题</div>
        <div class="step-desc">简短描述</div>
      </div>
      <div class="step" data-anim="step">
        <div class="step-nb">05</div>
        <div class="step-title">步骤五标题</div>
        <div class="step-desc">简短描述</div>
      </div>
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- `data-animate="pipeline"` 启用逐步揭示：空格键或右箭头逐步展开
- `data-anim="step"` 标记每个步骤为渐进式揭示
- 通过 `data-cols="3"` / `"4"` / `"6"` 改变列数（默认 5）
- 如果需要跨多个阶段的流水线，使用 `pipeline-section` 分开：
  ```html
  <div class="pipeline-section">
    <div class="pipeline-label">Phase 1: Foundation</div>
    <div class="pipeline" data-cols="3">...</div>
  </div>
  <div class="pipeline-section">
    <div class="pipeline-label">Phase 2: Growth</div>
    <div class="pipeline" data-cols="3">...</div>
  </div>
  ```

---

### 7. hero-question（悬念问题页）

大问题作为视觉焦点，引发好奇心。

```html
<section class="slide hero dark">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame center">
    <div class="kicker">THE QUESTION</div>
    <div class="display" style="font-family:var(--font-headline-zh);font-size:6.2vw;line-height:1.12">
      {用 1-2 句话提出的核心问题？}
    </div>
    <div class="lead" style="margin-top:3vh;max-width:42vw;opacity:.62">
      {问题的上下文或一句过渡}
    </div>
    <div class="rule" style="width:8vw;margin:4vh auto 0;opacity:.25"></div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
  </div>
</section>
```

**用法**：
- 放在关键转折点，问题 = 下一页要回答的内容
- 使用 hero dark 增加悬念感
- 问题本身不要超过 2 行
- 可以在背景使用 `ghost` 元素增强氛围：
  ```html
  <div class="ghost" style="left:-4vw;top:10vh;font-size:30vw;font-family:var(--font-display)">?</div>
  ```

---

### 8. big-quote（大引用页）

引用语为主视觉，沉浸式呈现。

```html
<section class="slide hero dark" data-animate="quote">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame center">
    <div class="display" style="font-size:5.2vw;line-height:1.14;max-width:64vw;text-align:center;font-style:italic" data-anim="line">
      "{引用语，建议 15-30 字，不宜过长}"
    </div>
    <div class="meta-row" style="margin-top:4vh" data-anim="line">
      <span>{作者姓名}</span><span>·</span><span>{头衔/出处}</span>
    </div>
    <div class="body-zh" style="margin-top:3vh;max-width:40vw;text-align:center;opacity:.68" data-anim="line">
      {一句话解读或评论，可选}
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- `data-animate="quote"` 实现逐行淡入（先元数据再文本行）
- `data-anim="line"` 标记每行为动画单元
- 引用语必须带出处
- 适配 hero dark 增加庄重感

---

### 9. binary-comparison（Before/After 对比）

左右并排对比，使用 `.grid-2-6-6`。

```html
<section class="slide light" data-animate="directional">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame grid-2-6-6">
    <!-- 左栏：Before / 方案 A -->
    <div class="col" data-anim="left" style="align-items:center;text-align:center">
      <div class="tag" style="margin-bottom:2vh">BEFORE</div>
      <figure class="frame-img r-16x9" style="max-height:38vh">
        <img src="images/{页码}-before.jpg" alt="{描述}">
      </figure>
      <div class="h-md" style="margin-top:2vh">{方案 A / 旧方案 标题}</div>
      <div class="body-zh" style="margin-top:1.4vh;text-align:center;max-width:28vw">
        {方案 A 的核心描述，≤ 50 字}
      </div>
    </div>
    <div class="rule v" data-anim="divider" style="justify-self:center;height:60%"></div>
    <!-- 右栏：After / 方案 B -->
    <div class="col" data-anim="right" style="align-items:center;text-align:center">
      <div class="tag" style="margin-bottom:2vh">AFTER</div>
      <figure class="frame-img r-16x9" style="max-height:38vh">
        <img src="images/{页码}-after.jpg" alt="{描述}">
      </figure>
      <div class="h-md" style="margin-top:2vh">{方案 B / 新方案 标题}</div>
      <div class="body-zh" style="margin-top:1.4vh;text-align:center;max-width:28vw">
        {方案 B 的核心描述，≤ 50 字}
      </div>
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- `data-animate="directional"`：左侧先入（`data-anim="left"`），divider 第二（`data-anim="divider"`），右侧再入（`data-anim="right"`）
- `.rule.v` 做中点竖线分隔
- 上方可使用 `.tag` 做分类标签
- 适合：Before/After、方案对比、优缺点、旧 vs 新

**变体：文案对比（无图片）**

```html
<section class="slide light" data-animate="directional">
  <!-- ...chrome... -->
  <div class="frame grid-2-6-6">
    <div class="col" data-anim="left">
      <div class="tag">TRADITIONAL</div>
      <div class="h-md" style="margin-top:2.8vh">传统方案</div>
      <div class="body-zh" style="margin-top:1.8vh">
        <ul style="list-style:none;padding:0">
          <li style="margin-bottom:1vh">✗ 痛点 1</li>
          <li style="margin-bottom:1vh">✗ 痛点 2</li>
          <li style="margin-bottom:1vh">✗ 痛点 3</li>
        </ul>
      </div>
    </div>
    <div class="col" data-anim="right">
      <div class="tag" style="border-color:var(--palette-accent-1)">OUR APPROACH</div>
      <div class="h-md" style="margin-top:2.8vh">我们的方案</div>
      <div class="body-zh" style="margin-top:1.8vh">
        <ul style="list-style:none;padding:0">
          <li style="margin-bottom:1vh">✓ 优势 1</li>
          <li style="margin-bottom:1vh">✓ 优势 2</li>
          <li style="margin-bottom:1vh">✓ 优势 3</li>
        </ul>
      </div>
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

---

### 10. text-with-figure（图文混排）

左侧宽文本（8 份） + 右侧窄图（4 份）。信息密度较高。

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="left"><span>{章节名}</span></div>
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame grid-2-8-4">
    <div class="col" data-anim>
      <div class="kicker">{KICKER 标签}</div>
      <div class="h-xl">{标题}</div>
      <div class="body-serif" style="margin-top:1.8vh">
        {正文第一段，可以是较长的叙述性文字，控制在 80-100 字以内。使用 .body-serif 衬线体提供舒适的阅读体验。}
      </div>
      <div class="body-zh" style="margin-top:1.4vh;opacity:.72">
        {正文第二段，补充信息，控制在 60 字以内。可加一句关键数据。}
      </div>
      <div class="callout" style="margin-top:2vh">
        <div class="q-big">{核心观点，≤ 25 字}</div>
        <span class="callout-src">— {来源}</span>
      </div>
    </div>
    <figure class="frame-img r-3x4" data-anim style="max-height:64vh">
      <img src="images/{页码}-fig.jpg" alt="{描述}">
      <figcaption class="frame-cap"><span class="pf">{图注标题}</span><span class="nb">{数据标注}</span></figcaption>
    </figure>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

**用法**：
- `.grid-2-8-4`：左 8 份（文本），右 4 份（窄图）
- 右侧配图推荐 3:4 竖图（`.r-3x4`）
- 正文可用 `.body-serif` + `.body-zh` 分层
- 内嵌 callout 突出核心观点

---

## 补充布局（作为笔记）

以下布局来自 baoyu-slide-deck 的信息图布局体系，可用于特定场景：

### icon-grid（图标网格）

3 列 × N 行的图标 + 标签矩阵。适用于概念分类、功能展示。

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame">
    <div class="h-xl" style="margin-bottom:2vh">{总标题}</div>
    <div class="layout-icon-grid">
      <div class="icon-item" data-anim>
        <i data-lucide="zap" class="ico-lg"></i>
        <div class="icon-label">功能或概念名</div>
      </div>
      <!-- 重复 N 次，推荐 6 或 9 个 -->
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

### two-columns / three-columns（内容列）

`.grid-2-6-6` 或 `.grid-3` + pillar 或通用内容。

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame">
    <div class="h-xl" style="margin-bottom:2vh">{总标题}</div>
    <div class="grid-3">
      <div class="pillar" data-anim>
        <div class="ic"><i data-lucide="target" class="ico-lg"></i></div>
        <div class="t">{支柱标题}</div>
        <div class="d">简短描述（20-30 字），说明此支柱的核心内容和价值。</div>
      </div>
      <div class="pillar" data-anim>
        <div class="ic"><i data-lucide="trending-up" class="ico-lg"></i></div>
        <div class="t">{支柱标题}</div>
        <div class="d">简短描述。</div>
      </div>
      <div class="pillar" data-anim>
        <div class="ic"><i data-lucide="shield" class="ico-lg"></i></div>
        <div class="t">{支柱标题}</div>
        <div class="d">简短描述。</div>
      </div>
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

### dashboard（指标仪表盘）

`.grid-4` + `.stat-card`。适用于关键指标一览。

与 stat-grid（模板 3）类似，但使用 2×2 四格。替换 `grid-6` 为 `grid-4` 即可。

### timeline（时间线）

可使用连续多个 `.rowline` 组成时间线，或使用 `pipeline` 布局。

```html
<section class="slide light" data-animate="cascade">
  <div class="chrome">
    <div class="right"><span>{页码} / {总页数}</span></div>
  </div>
  <div class="frame">
    <div class="h-xl" style="margin-bottom:2vh">发展里程碑</div>
    <div class="rowline" data-anim>
      <div class="k">里程碑名</div>
      <div class="v">达成成果描述</div>
      <div class="m">2024</div>
    </div>
    <div class="rowline" data-anim>
      <div class="k">里程碑名</div>
      <div class="v">达成成果描述</div>
      <div class="m">2025</div>
    </div>
    <div class="rowline" data-anim>
      <div class="k">里程碑名</div>
      <div class="v">达成成果描述</div>
      <div class="m">2026</div>
    </div>
  </div>
  <div class="foot">
    <span>{页码} / {总页数}</span>
    <span class="title">{短标题}</span>
  </div>
</section>
```

---

## 布局决策矩阵

| 内容类型 | 首选布局 | 备选布局 |
|----------|----------|----------|
| 封面 | `title-hero` | — |
| 议程/目录 | `two-columns` + rowline | `icon-grid` |
| 核心消息/问题 | `hero-question` | `big-quote` |
| 数据展示（4-6 个） | `stat-grid` (.grid-6) | `dashboard` (.grid-4) |
| 对比（2 个选项） | `binary-comparison` | `.split` |
| 步骤/流程 | `pipeline` | timeline (rowline) |
| 图文混排（文主图辅） | `text-with-figure` (.grid-2-8-4) | `.grid-2-7-5` |
| 图文混排（左文右图） | `split-screen` (.grid-2-7-5) | `.split-55` |
| 多图片展示 | `image-grid` (.grid-3-3) | `.grid-3` |
| 概念/支柱（3 个） | `three-columns` (.grid-3 + pillar) | `.grid-2-6-6` |
| 概念/功能（6-9 个） | `icon-grid` | `.grid-9` |
| 引用语 | `big-quote` | callout 内嵌 |
| 章节分隔 | `section-divider` | hero light/dark |
| 封底 | `title-hero` 变体 | `big-quote` + CTA |

---

## 布局节奏规则

1. **不得连续 3 页使用相同布局** — 即使内容类型允许，也需要注入视觉多样性
2. **数据页（stat-grid/dashboard）后接文字页** — 给受众消化数据的时间
3. **图片网格后接有明确标题的页面** — 过渡要平滑
4. **pipeline 是信息密集型布局** — 前后各放一页较轻量的页面（如 hero-question 或 big-quote）
5. **每 5-6 页应出现一个"呼吸页"** — hero-question、big-quote、section-divider 等低信息密度页面
