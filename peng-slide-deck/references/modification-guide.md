# HTML 幻灯片修改指南

> 生成 index.html 后，用户可能需要修改幻灯片。
> 本指南覆盖 5 种常见操作及其完整流程。

---

## 核心原则

1. **直接修改 HTML** — 不需要重新生成整个幻灯片，直接编辑 `index.html` 中的 `<section>` 即可。
2. **保持 chrome 一致性** — 每次增删页面后，必须更新 chrome 中的页码显示。
3. **CSS 变量集中管理** — 所有主题相关的颜色/字体/间距都在 `:root` 块中，改动一处全局生效。
4. **备份先行** — 修改前建议复制一份备份。

---

## 操作 1：编辑单页幻灯片

### 场景

修改某一页的文字、布局、图片或样式。

### 流程

1. 在 `index.html` 中找到目标 `<section class="slide ...">`
   - 按 `chrome` 中的页号定位（页号 = `<section>` 在文件中的顺序）
2. 直接修改 `<section>` 内部的 HTML 内容
3. 如果需要修改样式，在该 `<section>` 上添加 `style="..."` 属性，或修改 `<style>` 块中的通用类
4. 保存文件，刷新浏览器查看效果

### 示例

```html
<!-- 修改前 -->
<section class="slide slide-content" data-theme="light">
  <div class="slide-body">
    <h2>原有标题</h2>
    <p>原有正文内容。</p>
  </div>
</section>

<!-- 修改后 -->
<section class="slide slide-content" data-theme="light">
  <div class="slide-body">
    <h2>新标题</h2>
    <p>修改后的正文内容，增加了更多细节。</p>
    <ul>
      <li>新增要点 1</li>
      <li>新增要点 2</li>
    </ul>
  </div>
</section>
```

### 注意事项

- 不要改变 `<section>` 的 class 结构（`slide`、`slide-content`/`slide-hero` 等）
- 新增的 class 名必须已在 `<style>` 中有定义
- 如果新增内容超出页面可视范围，考虑拆分到下一页

---

## 操作 2：添加新页

### 场景

在两页之间或末尾插入一张新幻灯片。

### 流程

1. 确定插入位置（在哪两页之间）
2. 在对应 `<section>` 标签之间插入新的 `<section>` 块
3. 对新页后方的所有 `<section>`，更新它们的 `data-slide` 属性（页号 +1）
4. 更新 chrome 组件中的页码显示（如果有硬编码的总页数）
5. 如果有导航圆点由 JS 动态生成（`data-slides-count`），确认 JS 会自动计算页数

### 示例

```html
<!-- 在第 2 页和第 3 页之间插入新页 -->

<!-- 原第 2 页 -->
<section class="slide slide-content" data-theme="light">
  ...
</section>

<!-- 新增页（成为新的第 3 页） -->
<section class="slide slide-content" data-theme="light">
  <div class="slide-body">
    <h2>新插入的标题</h2>
    <p>新插入的内容描述。</p>
  </div>
</section>

<!-- 原第 3 页（现在变成第 4 页）— 页码已在 chrome 中自动更新 -->
<section class="slide slide-content" data-theme="dark">
  ...
</section>
```

### chrome 页码更新

如果 chrome 组件中使用的是以下方式，页码会自动更新：
- `document.querySelectorAll('.slide').length` — 自动计数
- `data-total-slides` 配合 JS 初始化

如果 chrome 中硬编码了总页数（如 `[3/14]`），必须手动更新：
- 将总页数 +1（例如 `14` → `15`）
- 缩略图索引的最大值同步更新

---

## 操作 3：删除页

### 场景

删除一张不需要的幻灯片。

### 流程

1. 在 `index.html` 中找到目标 `<section>`，删除整个块
2. 对其后所有的 `<section>`，它们的页号会在 chrome 的自动计数中自然递减
3. 如果 chrome 中硬编码了总页数，将总页数 -1
4. 检查删除后相邻页面的主题色是否破坏了节奏规则（无 3 页连续相同模式）

### 注意事项

- 删除后确认 Hero 页分布仍然合理（封面、封底、过渡页位置正确）
- 如果删除的是唯一的数据可视化页，考虑将后续某一页改为数据布局
- 不要在删除了某页后留下空白页号（检查连续）

---

## 操作 4：更换主题色

### 场景

将整个幻灯片从一种主题色切换到另一种（如从"墨水经典"切换到"沙丘"）。

### 流程

1. 在 `index.html` 中找到 `<style>` 块内的 `:root` 选择器
2. 替换 `:root` 中与主题色相关的 CSS 变量
3. **不需要改动任何 `<section>` 的 HTML** — 所有页面通过 CSS 变量继承新主题色
4. 保存文件，刷新浏览器查看效果

### 主题色变量对照

在 `:root` 中，主题色相关变量通常命名为：

```css
:root {
  /* 主题色 — 更换以下变量即可切换主题 */
  --theme-bg-dark: #...;        /* 深色页背景 */
  --theme-bg-light: #...;       /* 浅色页背景 */
  --theme-text-dark-bg: #...;   /* 深色背景上的文字色 */
  --theme-text-light-bg: #...;  /* 浅色背景上的文字色 */
  --theme-accent: #...;         /* 强调色（链接、高亮） */
  --theme-accent-secondary: #...; /* 第二强调色 */
  --theme-border: #...;         /* 边框和分隔线 */
  --theme-shadow: #...;         /* 阴影色 */
  --theme-overlay: #...;        /* 图片叠加色 */
}
```

### 5 套主题色快速参考

从各主题预设文件复制 `:root` 块：

| 主题 | 深色背景 | 浅色背景 | 强调色 |
|------|----------|----------|--------|
| 墨水经典 | `#1a1a1a` | `#fafafa` | `#c1272d` |
| 靛蓝瓷 | `#1a2a4a` | `#f0f4fa` | `#3b82f6` |
| 森林墨 | `#1a3018` | `#f4f8f2` | `#2d8a4e` |
| 牛皮纸 | `#3d2b1f` | `#faf3e6` | `#c17d3b` |
| 沙丘 | `#2d2a25` | `#faf8f3` | `#b8905a` |

> 实际值以主题预设文件为准。上表仅为快速参考。

---

## 操作 5：更换风格（预设或维度）

### 场景

从一种预设切换到另一种，或从预设切换到自定义维度。

### 流程

1. 在 `index.html` 中找到 `<style>` 块内的 `:root` 选择器
2. 替换与风格相关的 CSS 变量：
   - **纹理变量**（`--bg-pattern`、`--bg-noise`、`--bg-grid` 等）
   - **字体变量**（`--font-headline`、`--font-body`、`--font-mono`）
   - **间距变量**（`--slide-padding`、`--content-gap`、`--headline-size`、`--body-size`）
   - **色彩变量**（`--bg`、`--text`、`--accent-primary`、`--accent-secondary` 等）
3. 保留主题色变量不变（主题色和风格是独立的维度）
4. 如果切换了 Typography 维度，确认 `<link>` 中的 Google Fonts 引用已更新
5. 保存文件，刷新浏览器查看效果

### 风格变量 vs 主题变量

| 变量类别 | 属于 | 改变时机 | 示例 |
|----------|------|----------|------|
| `--bg`、`--text`、`--accent-*` | 风格 (Mood) | 换预设 | `--accent-primary: #2563EB;` |
| `--font-*` | 风格 (Typography) | 换预设 | `--font-headline: 'Noto Serif SC';` |
| `--slide-padding`、`--content-gap` | 风格 (Density) | 换预设 | `--slide-padding: 6vh 8vw;` |
| `--bg-pattern`、`--bg-noise` | 风格 (Texture) | 换预设 | `--bg-grid-opacity: 0.05;` |
| `--theme-bg-dark`、`--theme-bg-light`、`--theme-text-*` | 主题 | 换主题 | `--theme-accent: #c1272d;` |

---

## 修改后检查清单

每次修改后运行：

```
[ ] 浏览器中打开 index.html 验证修改生效
[ ] 逐页浏览确认无布局错乱
[ ] 确认 chrome 总页数正确（如果有增删）
[ ] 确认主题色节奏未被破坏（无 3+ 连续相同模式）
[ ] 如果是增删页：确认 Hero 页分布仍然合理
[ ] 如果是换主题：确认深色页上的文字可读
[ ] 如果是换风格：确认字体正确加载
[ ] 如果是换布局：确认新增的 CSS class 在 <style> 中有定义
[ ] 所有图片仍然正常显示
[ ] 导航功能正常（键盘/滚轮/触屏）
```

---

## 常见修改场景速查

| 我想... | 操作 | 改动范围 |
|---------|------|----------|
| 改一页的标题文字 | 编辑该页 `<section>` 内的 `<h2>` | 单页 |
| 调整所有标题字号 | 修改 `:root` 中的 `--headline-size` | 全局 |
| 把蓝色主题换成绿色 | 操作 4 — 换主题色 | `:root` 主题变量 |
| 从 corporate 切换到 sketch-notes | 操作 5 — 换风格 | `:root` 风格变量 + 字体 link |
| 在第 5 页后加一页 | 操作 2 — 插入新 `<section>`，更新总页数 | HTML 结构 |
| 移除第 8 页 | 操作 3 — 删除 `<section>`，更新总页数 | HTML 结构 |
| 把某页的列表改成双列对比 | 替换该页布局 class + HTML 结构 | 单页 |
| 更换封面背景色 | 在封面 `<section>` 上添加 `style` 属性 | 单页 |
| 更新全部页面数据 | 考虑重新生成大纲 + HTML | 全文 |
