# HTML 幻灯片质量检查清单

> 在 Step 5 生成 HTML 和 Step 6 审查 HTML 时使用。
> 逐项检查，所有 P0 项必须通过才能交付。
> P1、P2、P3 项发现问题时修复，但不阻断交付（除非用户要求完美级质量）。

---

## P0：阻断级（必须通过，否则不交付）

### 1. 所有 [必填] 占位符已替换

- [ ] `<title>[必填：幻灯片标题]</title>` — 已替换为实际标题
- [ ] 所有 `[必填：...]` 格式的占位符已消除
- [ ] 全文搜索 `[必填` 无匹配结果
- [ ] 全文搜索 `TODO` / `TBD` / `placeholder` 无匹配结果（大小写不敏感）

### 2. CSS 类使用检查

- [ ] 所有 HTML 中使用的 class 名在 `<style>` 块中有对应定义
- [ ] 检查方法：提取 `class="..."` 中的所有类名 → 搜索 `<style>` 中对应的 `.class-name {`
- [ ] 常见遗漏：`.slide-cover`、`.slide-content`、`.slide-back`、`.hero-title`、`.section-subtitle`
- [ ] 自定义 CSS 变量 `--xxx` 均在 `:root` 中有声明

### 3. 禁止 emoji 作为图标

- [ ] 全文搜索 emoji（Unicode 范围 `\p{Emoji}`），不得出现在图标位置
- [ ] 所有图标使用 [Lucide](https://lucide.dev/icons/) 图标集（`<i data-lucide="...">` 方式）
- [ ] Lucide 图标名称正确（与 lucide.dev 文档一致）
- [ ] `lucide.createIcons()` 在页面初始化时调用

### 4. 图片宽高比标准化

- [ ] 所有 `<img>` 标签使用标准宽高比（16:9、4:3、1:1、3:2），不保留原始图片比例
- [ ] 封面/封底图片使用 16:9
- [ ] 页面内插图使用与布局匹配的比例
- [ ] 通过 `aspect-ratio` CSS 属性或 `width`+`height` 属性锁定比例
- [ ] `<img>` 使用 `object-fit: cover` 或 `contain` 确保裁剪一致

### 5. 字体规范

- [ ] 所有标题/headline 元素（h1、h2、`.hero-title`、`.slide-title`）使用衬线字体（serif）或风格标题字体
- [ ] 所有正文/body 元素（p、li、`.slide-body`、`.caption`）使用无衬线字体（sans-serif）
- [ ] 等宽字体仅用于代码块、数据展示（.code、.data、pre）
- [ ] 字体回退链完整（例如 `'Noto Serif SC', 'Source Han Serif SC', serif`）
- [ ] Google Fonts 引用与 CSS font-family 声明一致

### 6. 页数一致性

- [ ] 浏览器中打开 index.html，用键盘逐页浏览，实际页数 = chrome 中显示的页数
- [ ] 所有页号从 01 到 NN 连续，无跳号、无重复
- [ ] 最后一张是封底（back cover），不是空白页或"谢谢"
- [ ] 封面页号 = 01，封底页号 = 实际总页数

### 7. 主题色节奏

- [ ] 相邻页面的主题色模式（light/dark/hero）不得连续 3 页相同
- [ ] Hero 页（封面、封底、关键转折页）使用深色背景
- [ ] 内容页使用浅色背景（或主题色变体）
- [ ] 规则：dark → light → light → dark → light → light → dark ...（2 light max 连续）
- [ ] 检查方法：遍历所有 `<section>`，检查 `data-theme` 或 class，计算连续模式

---

## P1：布局节奏

### 8. Hero 页与非 Hero 页交替

- [ ] Hero 页（`slide-hero` / `slide-cover` / `slide-back`）不得连续出现
- [ ] 理想的 Hero 分布：封面 = Hero → 内容 × 3-5 → Hero（过渡）→ 内容 × 3-5 → 封底 = Hero
- [ ] Hero 页间距 ≥ 3 张普通内容页

### 9. 数据页与密集页交替

- [ ] 数据密集型页（`key-stat`、`dashboard`、`bento-grid`）与文字型页交替出现
- [ ] 不得连续 3 页以上无数据可视化
- [ ] 不得连续 3 页以上全是数据无文字解释

### 10. 术语一致性

- [ ] 核心概念/产品名在全文中使用完全相同的措辞
- [ ] 同一事物的中文/英文翻译一致（不要混用"用户"/"User"/"使用者"）
- [ ] 技术术语使用一致的大小写（如 JSON 不是 Json，API 不是 api）
- [ ] 检查方法：列出所有专有名词，全文搜索确认每次出现形式一致

---

## P2：视觉润色

### 11. WebGL 背景透明度

- [ ] 封面/深色页：WebGL 粒子/网格可见度高（opacity 0.15-0.35）
- [ ] 浅色内容页：WebGL 背景透明度降低（opacity 0.05-0.15），避免干扰阅读
- [ ] 数据密集型页：WebGL 完全关闭或最低可见度（opacity < 0.08）
- [ ] 通过 CSS 变量 `--webgl-opacity` 控制，每页可单独覆盖

### 12. 图片对齐检查

- [ ] 所有 `<img>` 标签的 `align-self` 不为 `end`（这会导致图片贴底）
- [ ] 图片在弹性布局中正确居中（`align-self: center` 或由容器 `align-items` 控制）
- [ ] 全幅背景图使用 `object-fit: cover; object-position: center;`
- [ ] 图文混排中的图片垂直方向与文字区域对齐

### 13. 标题与正文间距

- [ ] 标题（h1 / h2 / .slide-title）与正文之间 `margin-top: 6vh` 到 `8vh`
- [ ] 同一页面内多个段落之间间距 ≥ `1.5rem`
- [ ] 列表项之间 `gap ≥ 0.75rem`
- [ ] 底部留白 ≥ `4vh`（避免内容贴底边）
- [ ] 检查方法：在浏览器中测量，或检查 CSS 中 margin/gap 值

---

## P3：操作检查

### 14. 图片路径

- [ ] 所有 `<img src="...">` 使用相对路径（如 `images/03-figma.jpg`）
- [ ] 不以 `/` 开头（非绝对路径）
- [ ] 不以 `file://` 开头
- [ ] 不含 `../` 的向上引用
- [ ] 路径中文件存在于对应位置

### 15. 导航功能

- [ ] **键盘 ← →** 方向键正常翻页
- [ ] **鼠标滚轮** 滚动触发翻页（无连续跳过问题）
- [ ] **触屏滑动** 左右滑动正常翻页（移动设备）
- [ ] **底部圆点导航** 点击正确跳转到对应页
- [ ] **ESC 键** 触发索引视图（展示所有页面缩略图）
- [ ] **首页/末页边界** — 第一页前和最后一页后不会翻到空白
- [ ] 页面切换动画无闪烁、无跳帧
- [ ] `index.html` 可在无本地服务器的情况下直接打开（所有资源内嵌或 CDN 引用）

---

## 最终自检

在 Step 6 审查 HTML 后，用以下清单做最终确认：

```
[ ] P0-1: 所有 [必填] 占位符已替换
[ ] P0-2: CSS 类全部定义
[ ] P0-3: 无 emoji 作为图标，全部使用 Lucide
[ ] P0-4: 图片宽高比标准化
[ ] P0-5: 标题衬线 / 正文无衬线
[ ] P0-6: 实际页数匹配 chrome 中显示
[ ] P0-7: 主题色节奏 (无 3+ 连续相同模式)
[ ] P1-8: Hero / 非 Hero 交替 (间距 ≥ 3 页)
[ ] P1-9: 数据页 / 文字页交替
[ ] P1-10: 术语一致
[ ] P2-11: WebGL 背景透明度正确
[ ] P2-12: 图片对齐正确
[ ] P2-13: 标题/正文间距充足
[ ] P3-14: 图片路径为相对路径
[ ] P3-15: 导航全部正常

通过: __ / 15
未通过项: _______________
```

---

## 快速检查脚本

生成 HTML 后，自动执行以下检查：

1. **搜索残留占位符**：`grep -n '\[必填' index.html` → 应无结果
2. **搜索 emoji**：`grep -Pn '[\x{1F600}-\x{1F6FF}]' index.html` → 应无结果（或有合理理由）
3. **统计 `<section>` 数量**：`grep -c '<section class="slide' index.html` → 应等于目标页数
4. **验证 CSS 变量**：对比 `:root` 块中声明的变量与 HTML 中使用的 `var(--xxx)` → 应完全匹配

```bash
#!/bin/bash
# 快速自检脚本（示例）
FILE="index.html"

echo "=== P0 Quick Checks ==="

# 1. Placeholder check
PLACEHOLDERS=$(grep -c '\[必填' "$FILE" 2>/dev/null || echo 0)
echo "P0-1: Placeholders remaining: $PLACEHOLDERS (should be 0)"

# 2. Emoji check (basic)
EMOJI=$(grep -Pc '[\x{1F300}-\x{1F9FF}]' "$FILE" 2>/dev/null || echo 0)
echo "P0-3: Emoji found: $EMOJI (should be 0)"

# 3. Section count
SECTIONS=$(grep -c '<section class="slide' "$FILE")
echo "P0-6: Sections found: $SECTIONS"

# 4. Image path check
ABSOLUTE_IMGS=$(grep -c 'src="/' "$FILE" 2>/dev/null || echo 0)
echo "P3-14: Absolute image paths: $ABSOLUTE_IMGS (should be 0)"
```
