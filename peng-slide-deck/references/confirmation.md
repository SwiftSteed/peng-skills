# 确认选项文案

> 在 Step 2 的 `AskUserQuestion` 工具调用中使用以下选项。
> Round 1 始终执行，Round 2 仅在用户选择"自定义维度"时执行。

## Round 1（批量 6 个问题，始终执行）

使用 `AskUserQuestion` 一次性提出以下 6 个问题：

### 问题 1：风格

```
question: "选择幻灯片风格"
header: "风格"
multiSelect: false
options:
  - label: "{推荐预设名}"
    description: "{一行中文描述，如：网格背景 + 冷色调 + 技术字体 + 标准密度 —— 适合架构、系统设计}"
  - label: "{备选预设名 1}"
    description: "{一行中文描述}"
  - label: "{备选预设名 2}"
    description: "{一行中文描述}"
  - label: "自定义维度"
    description: "自行选择纹理、情绪、排版、密度的组合（将触发 Round 2 额外提问）"
```

**代表回退文案**（当分析未产出强信号时）：

```
- label: "blueprint"
  description: "网格背景 + 冷色调 + 技术字体 + 标准密度 —— 适合架构、系统设计"
- label: "corporate"
  description: "纯色背景 + 专业色 + 几何字体 + 标准密度 —— 适合投资者、提案"
- label: "sketch-notes"
  description: "有机纹理 + 暖色调 + 手写字体 + 标准密度 —— 适合教育、教程"
- label: "自定义维度"
  description: "自行选择纹理、情绪、排版、密度的组合（将触发 Round 2 额外提问）"
```

### 问题 2：主题色

```
question: "选择主题色方案"
header: "主题色"
multiSelect: false
options:
  - label: "🖋 墨水经典"
    description: "黑白灰为主调，深色页深沉专业，浅色页干净利落。通用 / 商业发布 / 默认选择"
  - label: "🌊 靛蓝瓷"
    description: "蓝色系为主调，深色页深蓝如瓷，浅色页清亮明快。科技 / 研究 / 数据"
  - label: "🌿 森林墨"
    description: "绿棕色系为主调，深色页沉静如林，浅色页温柔自然。自然 / 可持续 / 文化"
  - label: "🍂 牛皮纸"
    description: "暖棕色系为主调，深色页复古厚重，浅色页温暖怀旧。怀旧 / 人文 / 文学"
  - label: "🌙 沙丘"
    description: "暖灰棕为主调，深色页沉稳静谧，浅色页柔和优雅。艺术 / 设计 / 创意"
```

### 问题 3：受众

```
question: "目标受众是谁？"
header: "受众"
multiSelect: false
options:
  - label: "通用"
    description: "混合背景的广泛受众"
  - label: "初学者"
    description: "刚接触该主题，需要清晰解释和循序渐进"
  - label: "中级"
    description: "有一定基础，可以处理一些技术细节"
  - label: "专家"
    description: "深厚背景知识，期望深度和精确度"
  - label: "高管"
    description: "关注结果、ROI 和战略影响"
```

### 问题 4：页数

```
question: "目标页数？"
header: "页数"
multiSelect: false
options:
  - label: "{推荐 N 页}"
    description: "根据内容长度推荐（封面 + N 页内容 + 封底）"
  - label: "{N-2 页}（更少）"
    description: "更紧凑，每页信息密度更高"
  - label: "{N+4 页}（更多）"
    description: "更宽松，每页聚焦一个要点"
```

### 问题 5：是否审查大纲

```
question: "生成大纲后是否审查？"
header: "审查大纲"
multiSelect: false
options:
  - label: "审查"
    description: "生成大纲后先审查再继续（推荐）"
  - label: "跳过"
    description: "直接生成 HTML 幻灯片"
```

### 问题 6：是否审查 HTML

```
question: "生成 HTML 后是否审查？"
header: "审查 HTML"
multiSelect: false
options:
  - label: "审查"
    description: "生成 HTML 后先在浏览器预览再最终确认（推荐）"
  - label: "跳过"
    description: "生成后直接交付"
```

---

## Round 2（批量 4 个问题，仅在用户选择"自定义维度"时执行）

使用 `AskUserQuestion` 一次性提出以下 4 个问题：

### 问题 2-1：纹理

```
question: "选择背景纹理"
header: "纹理 (Texture)"
multiSelect: false
options:
  - label: "clean（纯净）"
    description: "纯色背景无纹理，干净线条和几何形状 —— 适合高管、极简、企业"
  - label: "grid（网格）"
    description: "浅网格叠加(5-10% 透明度)，工程感技术图 —— 适合技术、架构、工程"
  - label: "organic（有机）"
    description: "柔和纹理手绘质感，笔触水彩草图线条 —— 适合创意、教育、友好场景"
  - label: "pixel（像素）"
    description: "块状像素 8-bit 美学，复古游戏元素 —— 适合游戏、开发者"
  - label: "paper（纸张）"
    description: "陈纸纹理（微折痕褪色），复古邮票老化元素 —— 适合历史、遗产、叙事"
```

### 问题 2-2：情绪

```
question: "选择色彩情绪"
header: "情绪 (Mood)"
multiSelect: false
options:
  - label: "professional（专业）"
    description: "冷中性，海军蓝 + 金色 + 结构化灰 —— 适合商务、企业"
  - label: "warm（温暖）"
    description: "暖色，大地色 + 橙色 + 自然色 —— 适合人文、生活"
  - label: "macaron（马卡龙）"
    description: "暖色，马卡龙色块（蓝、薄荷、薰衣草、桃）—— 适合亲子、轻量内容"
  - label: "cool（冷静）"
    description: "冷色，蓝灰青色系 —— 适合技术、数据"
  - label: "vibrant（活力）"
    description: "高饱和，大胆色彩对比强烈 —— 适合营销、创意"
  - label: "dark（暗色）"
    description: "深色背景 + 亮色点缀 —— 适合娱乐、游戏、夜场"
  - label: "neutral（中性）"
    description: "极简灰度，白底黑字 —— 适合极简、学术"
```

### 问题 2-3：排版

```
question: "选择排版风格"
header: "排版 (Typography)"
multiSelect: false
options:
  - label: "geometric（几何）"
    description: "现代几何无衬线，完美圆形 O，一致笔画宽度 —— 适合现代、科技"
  - label: "humanist（人文）"
    description: "友好无衬线，微妙笔画变化，开放式字谷 —— 适合人文、温暖内容"
  - label: "handwritten（手写）"
    description: "手写马克笔/笔刷风格，有机边缘非均匀基线 —— 适合教育、创意"
  - label: "editorial（编辑）"
    description: "高对比衬线/无衬线混合，粗/细笔画对比杂志级 —— 适合发布会、主题演讲"
  - label: "technical（技术）"
    description: "干净无衬线 + 等宽数字，清晰数字区分 —— 适合技术文档、数据"
```

### 问题 2-4：密度

```
question: "选择内容密度"
header: "密度 (Density)"
multiSelect: false
options:
  - label: "minimal（极简）"
    description: "每页一个焦点，大量留白（边距 15%+）—— 适合高管简报、主题演讲"
  - label: "balanced（均衡）"
    description: "每页 2-3 个要点，标准留白（边距 10%）—— 适合通用展示"
  - label: "dense（密集）"
    description: "多个数据点，紧凑留白（边距 5-8%）—— 适合数据密集、技术评审"
```

---

## 确认流程控制

### 初始确认

在 Step 2 开始时，调用 `AskUserQuestion` 批量输出 Round 1 的 6 个问题。
等待所有答案后再进入接下来的逻辑。

### Round 2 触发条件

当且仅当用户在 Round 1 的"风格"问题中选择了 **"自定义维度"** 时，
紧接着触发 Round 2，用第二个 `AskUserQuestion` 批量输出 4 个问题。
等待所有答案后再进入 Step 3。

### 跳过确认

用户可通过以下表述跳过确认：
- "直接生成"
- "不用确认"
- "跳过确认"
- "按默认出幻灯片"

跳过后，所有选项使用 EXTEND.md 配置值或内置默认值（blueprint + 墨水经典 + general + 推荐页数 + 审查）。

### 局部覆盖

用户可在初始请求中指定部分参数，其余仍通过确认收集：

```
"用 corporate 风格和沙丘主题做 PPT"
→ 风格和主题色已确定，其余 4 个问题仍需确认
```

### 确认后行为

确认完成后，输出确认摘要并继续执行 Step 3：

```
确认摘要：
- 风格: blueprint（默认）
- 主题色: 墨水经典
- 受众: 通用
- 页数: 14 页
- 审查大纲: 是
- 审查 HTML: 是
```
