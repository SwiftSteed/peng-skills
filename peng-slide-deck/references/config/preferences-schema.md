# EXTEND.md 偏好架构

> 用户可通过 EXTEND.md 文件预设幻灯片生成偏好，避免每次回答确认问题。
> 运行时在 Step 1 加载，确认流程（Step 2）中展示的内容受此影响。

---

## 文件位置

按优先级查找，第一个找到的生效：

| 优先级 | 路径 | 范围 |
|--------|------|------|
| 1（最高） | `.baoyu-skills/peng-slide-deck/EXTEND.md` | 项目级 |
| 2 | `$HOME/.baoyu-skills/peng-slide-deck/EXTEND.md` | 用户级 |

两个文件格式相同。项目级覆盖用户级。

### 查找流程

```
1. 检查项目根目录下的 .baoyu-skills/peng-slide-deck/EXTEND.md
2. 如果不存在，检查 $HOME/.baoyu-skills/peng-slide-deck/EXTEND.md
3. 如果都不存在，使用内置默认值
```

### 加载时输出

找到文件时输出摘要：

```
加载偏好: .baoyu-skills/peng-slide-deck/EXTEND.md
- 风格: blueprint
- 主题: ink
- 受众: general
- 其他选项: [列出非默认项]
```

未找到时：

```
未找到 EXTEND.md，使用内置默认值。
```

---

## 完整 Schema

```yaml
# ============================================================
# Slide Deck Preferences (HTML)
# 文件位置: .baoyu-skills/peng-slide-deck/EXTEND.md
#           或 $HOME/.baoyu-skills/peng-slide-deck/EXTEND.md
# ============================================================

## ---------------------------
## 默认选项 (Defaults)
## ---------------------------

# 风格预设：17 个预设名之一 或 "custom"
# 预设列表: blueprint, chalkboard, corporate, minimal,
#           sketch-notes, hand-drawn-edu, watercolor,
#           dark-atmospheric, notion, bold-editorial,
#           editorial-infographic, fantasy-animation,
#           intuition-machine, pixel-art, scientific,
#           vector-illustration, vintage
style: blueprint

# 主题色预设：5 选 1
# ink     — 墨水经典（黑白灰，通用/商务）
# indigo  — 靛蓝瓷（蓝色系，科技/研究/数据）
# forest  — 森林墨（绿棕色系，自然/可持续/文化）
# kraft   — 牛皮纸（暖棕色系，怀旧/人文/文学）
# dune    — 沙丘（暖灰棕系，艺术/设计/创意）
theme: ink

# 目标受众
# beginners    — 初学者（清晰解释，循序渐进）
# intermediate — 中级（有基础，可处理技术细节）
# experts      — 专家（深度、精确、可验证）
# executives   — 高管（结果、ROI、战略）
# general      — 通用（混合背景）
audience: general

# 输出语言
# auto — 自动检测源内容语言
# en   — English
# zh   — 中文
# ja   — 日本語
# 其他 BCP 47 语言代码也可使用
language: auto

# 是否在生成大纲后审查
# true  — 生成大纲后先审查再继续（推荐）
# false — 跳过审查，直接生成 HTML
review: true

# 是否在生成 HTML 后审查
# true  — 生成 HTML 后先审查再交付（推荐）
# false — 跳过审查，直接交付
review_html: true


## ---------------------------
## 自定义维度 (仅当 style: custom 时生效)
## ---------------------------
dimensions:
  # 纹理 (Texture)
  # clean | grid | organic | pixel | paper
  texture: clean

  # 情绪 (Mood)  
  # professional | warm | macaron | cool | vibrant | dark | neutral
  mood: professional

  # 排版 (Typography)
  # geometric | humanist | handwritten | editorial | technical
  typography: geometric

  # 密度 (Density)
  # minimal | balanced | dense
  density: balanced


## ---------------------------
## 自定义风格 (可选)
## ---------------------------
# 保存自定义维度组合为命名风格，供后续复用
# 自定义风格名可用于 --style 参数
custom_styles:
  # 示例：我的风格 1
  my-style-1:
    texture: grid
    mood: cool
    typography: technical
    density: dense
    description: "技术深度风格 — 网格背景 + 冷色调 + 技术字体 + 高密度"

  # 示例：我的风格 2  
  my-warm-style:
    texture: organic
    mood: warm
    typography: humanist
    density: minimal
    description: "温暖极简风格 — 有机纹理 + 暖色调 + 人文字体 + 极简密度"
```

---

## 默认值（无 EXTEND.md 时使用）

```yaml
style: blueprint
theme: ink
audience: general
language: auto
review: true
review_html: true
dimensions:
  texture: clean
  mood: professional
  typography: geometric
  density: balanced
```

---

## 值约束与校验

加载 EXTEND.md 时，对每个字段进行校验：

| 字段 | 校验规则 | 非法时的处理 |
|------|----------|--------------|
| `style` | 必须是 17 个预设之一、"custom"、或 `custom_styles` 中定义的自定义风格名 | 报错并回退到 `blueprint` |
| `theme` | 必须是 `ink` / `indigo` / `forest` / `kraft` / `dune` 之一 | 报错并回退到 `ink` |
| `audience` | 必须是 `beginners` / `intermediate` / `experts` / `executives` / `general` 之一 | 报错并回退到 `general` |
| `language` | `auto` 或有效的 BCP 47 语言代码 | 报错并回退到 `auto` |
| `review` | `true` 或 `false` | 报错并回退到 `true` |
| `review_html` | `true` 或 `false` | 报错并回退到 `true` |
| `dimensions.texture` | 必须是 `clean` / `grid` / `organic` / `pixel` / `paper` 之一 | 报错并回退到 `clean` |
| `dimensions.mood` | 必须是 `professional` / `warm` / `macaron` / `cool` / `vibrant` / `dark` / `neutral` 之一 | 报错并回退到 `professional` |
| `dimensions.typography` | 必须是 `geometric` / `humanist` / `handwritten` / `editorial` / `technical` 之一 | 报错并回退到 `geometric` |
| `dimensions.density` | 必须是 `minimal` / `balanced` / `dense` 之一 | 报错并回退到 `balanced` |

---

## EXTEND.md 示例

### 示例 1：最简配置（使用所有默认值）

```yaml
# 无需任何配置 — 没有 EXTEND.md 时等价于此
```

### 示例 2：公司模板配置

```yaml
style: corporate
theme: ink
audience: executives
language: zh
review: false
review_html: true
```

### 示例 3：个人偏好 + 自定义风格

```yaml
style: blueprint
theme: indigo
audience: general
language: auto
review: true
review_html: true

custom_styles:
  my-tech-style:
    texture: grid
    mood: cool
    typography: technical
    density: balanced
    description: "我的技术风格"
  
  my-creative-style:
    texture: organic
    mood: vibrant
    typography: humanist
    density: minimal
    description: "我的创意风格"
```

### 示例 4：使用自定义维度

```yaml
style: custom
theme: dune
audience: general
language: zh
review: true
review_html: true

dimensions:
  texture: paper
  mood: warm
  typography: editorial
  density: balanced
```

---

## 命令行参数覆盖

用户通过命令行参数指定的选项覆盖 EXTEND.md 中的值：

| 参数 | 覆盖字段 |
|------|----------|
| `--style corporate` | `style` |
| `--theme indigo` | `theme` |
| `--audience experts` | `audience` |
| `--lang en` | `language` |
| `--slides 20` | 目标页数 |
| `--outline-only` | 仅执行到 Step 3 |
| `--html-only` | 跳过大纲审查和 HTML 审查 |

命令行参数 > EXTEND.md > 内置默认值。
