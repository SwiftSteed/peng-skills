# 内容与风格规则

> 在 Step 3（生成大纲）和 Step 5（生成 HTML）时作为内容质量标准。
> 每条规则包含检查方法和违规示例。

---

## 1. 尊重读者注意力

### 原则

每张幻灯片传达**一个且仅一个**清晰的信息。读者扫描一页的时间不超过 5 秒，必须在 5 秒内理解这页要说什么。

### 实施规则

- 每页主标题（`.h-xl`）就是一个完整的陈述句，读者只看标题就能理解这页的核心信息
- 正文不超过 3 个要点（每个 ≤ 25 字）
- 如果一页需要 4 个以上要点，拆分为两页
- 数据页（stat-grid）每页 4-6 个指标，不要更多
- 优先删除而非压缩：拿不准的信息宁可删掉

### 检查方法

```
读完每页的主标题，不看正文：
- 能理解这页在说什么吗？
- 能复述给另一个人听吗？
- 如果两个答案都是"否" → 重写标题
```

### 违规示例

```html
<!-- 错误：标题是标签，不是陈述 -->
<div class="h-xl">市场规模</div>

<!-- 正确：标题是完整陈述 -->
<div class="h-xl">全球市场规模预计 2027 年突破 500 亿美元</div>
```

---

## 2. 数据可追溯

### 原则

幻灯片中出现的每一个数字、百分比、统计结论，都必须标注来源。

### 实施规则

- 数据引用格式：`来源: {机构名}, {年份}` 或 `— {报告名称}`
- 如果数据是估算/预测，标注"预测值"或"估算"
- 数据页面在 `.foot` 或 `.stat-note` 中标注来源
- 不标注来源的数据视为不可采信

### HTML 实现

```html
<!-- stat-note 中标注来源 -->
<div class="stat-card">
  <div class="stat-label">GLOBAL USERS</div>
  <div class="stat-nb">2.8<span class="stat-unit">B</span></div>
  <div class="stat-note">来源: Statista, 2025</div>
</div>

<!-- callout-src 中标注引语来源 -->
<div class="callout">
  <div class="q-big">"云原生不是目的地，而是旅程。"</div>
  <span class="callout-src">— Kelsey Hightower, KubeCon 2024</span>
</div>

<!-- foot 中标注页面数据来源 -->
<div class="foot">
  <span>05 / 14</span>
  <span class="title" style="opacity:.5;font-size:10px">数据来源: IDC 2025Q2</span>
</div>
```

### 违规示例

```html
<!-- 错误：没有来源 -->
<div class="stat-nb">87<span class="stat-unit">%</span></div>
<div class="stat-note">用户满意度评分</div>

<!-- 正确 -->
<div class="stat-nb">87<span class="stat-unit">%</span></div>
<div class="stat-note">用户满意度评分 · 来源: NPS Survey Q2 2025 (n=12,000)</div>
```

---

## 3. 每页自包含

### 原则

任意一页幻灯片单独拿出来都应该可以独立理解。读者不需要看前后页就能明白这页的内容。

### 实施规则

- 每页的 `.h-xl` 标题是独立的完整陈述，不依赖上一页的上下文
- 避免指代词："它"、"这个"、"如上所述"、"接着" —— 全部用具体名词替代
- Chrome 的 `.left` 中标注当前章节，提供上下文锚点
- 如果一页引用了前面提到过的术语，在这一页重新给出简短定义
- 图片必须有 `figcaption`（`.frame-cap`）说明

### 检查方法

```
随机抽取任意一页，单独看：
- 能理解这页在说什么吗？
- 标题和正文自洽吗？
- 如果有图片，图片说明能独立看懂吗？
```

### 违规示例

```html
<!-- 错误：标题依赖上下文 -->
<div class="h-xl">基于以上分析，我们提出三个建议</div>
<!-- 读者不知道"以上分析"是什么 -->

<!-- 正确 -->
<div class="h-xl">性能优化三方向：缓存、并行、压缩</div>

<!-- 错误：图片无说明 -->
<figure class="frame-img r-16x9">
  <img src="images/03-chart.jpg" alt="">
</figure>

<!-- 正确 -->
<figure class="frame-img r-16x9">
  <img src="images/03-response-time.jpg" alt="响应时间分布">
  <figcaption class="frame-cap">
    <span class="pf">响应时间分布 (P50/P95/P99)</span>
    <span class="nb">ms</span>
  </figcaption>
</figure>
```

---

## 4. 无占位符

### 原则

交付给用户的 HTML 文件中，不得存在任何占位符。所有文案、数据、图片路径必须已填充实际内容。

### 实施规则

- `[必填]` 格式的占位符全部替换
- `{变量名}` 格式的模板变量全部填充
- 所有 `.img-slot` 替换为实际图片（或确认用户接受占位）
- `TODO`、`TBD`、`FIXME`、`placeholder` 等标记全部清除
- `lorem ipsum` 等填充文本全部替换

### 检查命令

```bash
# 在 index.html 目录中执行
grep -n '\[必填\]' index.html       # 应无结果
grep -n 'TBD\|TODO\|FIXME' index.html  # 应无结果
grep -n 'img-slot' index.html       # 应无结果（或有合理理由）
grep -n 'lorem ipsum' index.html    # 应无结果
```

---

## 5. 叙事型标题

### 原则

标题**讲故事**，不**贴标签**。每个标题都是一个完整的、有信息量的陈述。

### 好标题 vs 坏标题

| 坏标题（标签式） | 好标题（叙事式） |
|-----------------|-----------------|
| 市场分析 | 2025 年企业级 AI 市场同比增长 42% |
| 产品优势 | 从部署到上线只需 3 天，竞品平均 14 天 |
| 团队介绍 | 12 人团队，来自 Google/Meta/Stanford |
| 技术架构 | 微服务 + 事件溯源：支持每秒 50 万并发 |
| 竞品对比 | 价格不到竞品一半，功能覆盖率 120% |
| 未来规划 | Q3 上线多语言，Q4 覆盖亚太 5 国 |
| 客户案例 | 某银行：交易处理时间从 2 小时降至 3 分钟 |
| 核心数据 | 月活跃用户突破 1200 万，留存率 74% |

### 标题写作公式

```
[具体主体] + [具体动作/变化] + [具体数字/结果]
```

如果标题中没有任何数字或具体结果，它很可能是一个标签，需要重写。

### HTML 实现

```html
<!-- 错误：标签式 -->
<div class="h-xl">产品介绍</div>

<!-- 正确：叙事式 -->
<div class="h-xl">从数据采集到业务洞察：链路耗时从 4 小时缩短至 8 分钟</div>
```

---

## 6. 避免 AI 陈词滥调

### 原则

幻灯片文案中避开过度使用、空洞无物的 AI 生成常用词。

### 禁止使用的词和短语

#### 动词
- ~~delve into~~ / ~~dive into~~ / ~~dive deep~~ → 用 "分析"、"探讨"、"研究" 替代
- ~~explore~~ → 用 "考察"、"审视"、"检验" 替代
- ~~embark on a journey~~ → 用 "开始" 替代
- ~~unlock~~ / ~~unleash~~ → 用 "释放"、"实现" 替代
- ~~leverage~~ → 用 "利用"、"借助" 替代
- ~~harness~~ → 用 "运用"、"驾驭" 替代
- ~~revolutionize~~ → 用 "改变"、"革新" 替代

#### 形容词/副词
- ~~groundbreaking~~ / ~~cutting-edge~~ → 用具体证据替代（如"行业首次"、"性能提升 10 倍"）
- ~~game-changing~~ → 同上
- ~~seamless~~ / ~~seamlessly~~ → 用具体描述替代（如"零停机"、"自动迁移"）
- ~~robust~~ → 用具体数字替代
- ~~innovative~~ → 直接描述创新点
- ~~holistic~~ → 用"全面"或直接说明覆盖哪些方面

#### 名词
- ~~journey~~ / ~~odyssey~~ → 用"过程"、"阶段"替代
- ~~landscape~~ → 用"市场"、"领域"、"格局"替代
- ~~ecosystem~~ → 用"生态"或说明具体包含哪些组成部分
- ~~paradigm / paradigm shift~~ → 直接说发生了什么变化
- ~~synergy~~ → 用"协同效应"或具体描述

#### 结构
- ~~In conclusion,~~ / ~~In summary,~~ → 封底直接用标题说出结论
- ~~It is worth noting that~~ → 直接说内容
- ~~As we can see,~~ → 删除
- ~~Without further ado,~~ → 删除

### 检查方法

生成大纲后，对大纲中的标题和正文运行关键词检查：

```
搜索词: delve, dive, explore, embark, unlock, unleash, leverage, 
        harness, revolutionize, groundbreaking, game-changing, 
        seamless, robust, innovative, holistic, journey, odyssey, 
        landscape, ecosystem, paradigm, synergy, cutting-edge
```

如果出现：逐个替换为具体措辞。

### HTML 中特别注意事项

- `.kicker` 和 `.stat-label` 区域尤其容易出现 "UNLOCKING POTENTIAL"、"SEAMLESS INTEGRATION" 等陈词滥调
- 技术类幻灯片容易在标题出现 "Revolutionizing X"、"Reimagining Y"

---

## 7. 有意义的封底

### 原则

封底是留给读者的最后印象，**不能只是"谢谢观看"**。它必须包含实质内容——可以是核心信息的再一次提炼、具体的行动号召、或者发人深思的问题。

### 封底方案

| 方案 | 内容 | 适用场景 |
|------|------|----------|
| **核心信息重述** | 提炼全文最核心的一句话，以 display 或 h-hero 呈现 | 所有场景 |
| **行动号召 (CTA)** | 具体的下一步操作：注册、下载、联系、访问 | 商业/产品 |
| **开放问题** | 一个发人深思的问题，引发后续讨论 | 学术/研究 |
| **关键数字回顾** | 全文最重要的 3 个数字（用 stat-card 微缩版） | 数据密集型 |
| **引用收尾** | 与主题呼应的名言或洞察 | 人文/创意 |
| **联系方式** | 邮箱、网站、社交媒体 | 演讲/会议 |

### 禁止的封底

```html
<!-- 禁止 -->
<div class="h-hero">谢谢</div>
<div class="h-hero">Thank You</div>
<div class="h-hero">Q & A</div>
<div class="h-hero">感谢聆听</div>
```

### 正确示例

```html
<!-- 方案 A：核心信息重述 + CTA -->
<section class="slide hero light">
  <div class="chrome">
    <div class="right"><span>12 / 12</span></div>
  </div>
  <div class="frame center">
    <div class="display" style="font-family:var(--font-headline-zh);font-size:6vw;line-height:1.12">
      从今天开始，用 3 天完成竞品 14 天才能做到的部署
    </div>
    <div class="lead" style="margin-top:3vh;opacity:.72">
      立即注册，获 30 天免费试用
    </div>
    <div class="meta" style="margin-top:5vh">
      platform.io/trial · arch@company.com
    </div>
  </div>
</section>
```

---

## 8. 一致的视觉语言

### 原则

整个 slide deck 使用统一的图标风格、色彩模式和网格系统。前后的决策相互一致，不会出现一套 Lucide 线性图标突然出现一个实心图标的情况。

### 具体规则

#### 8.1 图标一致性

- 所有图标使用 **Lucide 图标集**，不得混入其他图标库或 emoji
- 同一 slide deck 中同类图标使用相同尺寸类（如 `.pillar .ic` 中统一使用 `.ico-lg`）
- 一个 slide deck 中图标描边宽度保持一致（Lucide 默认 `stroke-width` 通过 CSS 控制）
- 图标颜色始终继承 `currentColor`，不单独设置 `stroke` 属性

#### 8.2 色彩一致性

- 强调色（`--palette-accent-1`）贯穿全文用于同一类信息（如关键数字、链接、高亮）
- 警告色（`--palette-warning`）始终用于同一类信号（如负增长、风险提示）
- 同一 slide 内不使用超过 3 种主题色以外的颜色
- `.tag` 默认使用 `currentColor` 边框和文字，如需突出使用 accent 时应全局一致

#### 8.3 间距一致性

- 同级标题与正文的间距全局统一（由 CSS 变量 `--content-gap` 和网格 `gap` 控制）
- 同一 slide 内多个卡片的内部间距相同
- Chrome 和 Foot 的间距全局一致（由 CSS 变量控制）

#### 8.4 网格一致性

- 同级页面使用相同或近似的网格布局
- `.grid-3` 中三列元素的高度和内部结构保持一致
- 网格中的图片统一使用 `h-{n}` 固定高度而非混合 aspect-ratio

#### 8.5 字体一致性

- 标题字体（`--font-headline-zh` / `--font-display`）贯穿全文不变
- 正文字体（`--font-body-zh`）贯穿全文不变
- 等宽字体（`--font-mono`）贯穿全文不变
- 不得在同一 slide 内标题用两种不同字体

### 检查方法

```
1. 全文搜索 i data-lucide，确认所有图标名称都来自 Lucide
2. 检查 :root 中的 --palette-accent-1 在全文 HTML 中的使用是否一致
3. 逐页检查 h-xl 的 font-family（应始终相同，由 CSS 类控制）
4. 检查 grid 容器中的直接子元素是否使用相同的卡片类型
```

---

## 综合质量检查清单

在生成大纲和 HTML 后，逐项检查：

### 内容质量
- [ ] 每页主标题是完整陈述句
- [ ] 每页核心信息可以在 5 秒内理解
- [ ] 所有数据标注了来源
- [ ] 没有"它"、"这个"等指代词
- [ ] 没有 `[必填]`、`{变量}`、`TODO` 等占位符
- [ ] 封底不是"谢谢"或"Thank You"
- [ ] 没有 AI 陈词滥调（delve、unlock、revolutionize...）

### 视觉质量
- [ ] 所有图标来自 Lucide，没有 emoji
- [ ] 强调色使用一致（同一类信息用同一色）
- [ ] 同级标题与正文间距统一
- [ ] 网格中所有卡片结构一致
- [ ] 字体分配符合规则（衬线=标题、无衬线=正文、等宽=元数据）

### 结构质量
- [ ] 每页自包含（单独看也能理解）
- [ ] 无连续 3 页使用相同布局
- [ ] 无连续 3 页使用相同 theme
- [ ] ≥ 8 页时有至少 1 个 hero dark 和 1 个 hero light
- [ ] 每 3-4 页有视觉休止符

### 图片质量
- [ ] 图片使用标准宽高比（16:9 / 4:3 / 3:4 / 1:1）
- [ ] 网格中图片使用固定高度（h-{n}）
- [ ] 无 align-self: end
- [ ] 所有图片有 alt 文本和 figcaption
