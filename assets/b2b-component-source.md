---
name: 中后台组件规范
description: 中后台系统完整设计与开发规范，包含全局 Design Tokens（色彩、字体、圆角、间距、阴影）及30个组件的样式矩阵、状态映射、尺寸规范与CSS代码示例。覆盖：按钮、分页、Tabs、导航菜单、下拉菜单、锚点、步骤条、输入框、表单容器、上传、日期时间选择器、选择器、单选框、复选框、表格、树选择、搜索框、开关、穿梭框、描述列表、标签、徽标、文字提示、气泡卡片、加载、对话框、进度条、全局提示、警告信息、结果。当用户提到"中后台组件"、"设计规范"、"Design Tokens"或需要生成符合中后台规范的组件代码（CSS/HTML）时触发使用。
---

# 中后台组件规范

本规范定义了中后台系统的全局底层基础设施（Design Tokens）及所有组件的样式矩阵。全团队在跨产品线协作时，必须严格基于本规范定义的 Tokens（变量名）进行交付与代码编写，严禁在代码中直接硬编码（Hardcode）任何像素值或颜色值。

---

## 一、全局色彩系统 (Global Color System)

色彩体系采用 **12级色阶分布体系**（从浅到深：10 ~ 120）。

- **浅色阶 (10 - 30)**：用于容器背景、悬浮/点击底色、轻量标签及边框
- **中色阶 (40 - 60)**：用于状态过渡、非文本元素的禁用态
- **深色阶 (70 - 120)**：用于文本、核心状态背景、聚焦边框及深度交互态

### 1. 功能语义色调色板

#### 蓝色系 (Blue) —— 品牌主色、链接与交互态

| 色阶 | 变量名 | HEX | 标准用途描述 |
|------|--------|-----|-------------|
| 浅-1 | blue-10 | #F7FBFF | 强调色次要按钮悬浮状态默认、轻微警告背景色 |
| 浅-2 | blue-20 | #E0EEFF | 下拉菜单选项选中态背景、导航选中背景 |
| 浅-3 | blue-30 | #D6E8FF | 强调色标签边框默认 |
| 中-1 | blue-40 | #BAD8FF | 预留过渡色 |
| 中-2 | blue-50 | #69A0FF | 预留过渡色 |
| 中-3 | blue-60 | #3D79F2 | 强调色禁用状态默认 |
| **深-1** | **blue-70** | **#1553E5** | **[基准主色]** 强调色边框聚焦、主文字、链接、开关选中、标签强调等 |
| 深-2 | blue-80 | #093ED1 | 强调色点击状态、链接文字点击状态 |
| 深-3 | blue-90 | #002499 | 预留深度色 |
| 深-4 | blue-100 | #001773 | 预留深度色 |
| 深-5 | blue-110 | #000D4D | 预留深度色 |
| 深-6 | blue-120 | #000526 | 预留深度色 |

#### 红色系 (Red) —— 错误、警告与危险破坏性操作

| 色阶 | 变量名 | HEX | 标准用途描述 |
|------|--------|-----|-------------|
| 浅-1 | red-10 | #FFF1F0 | 轻微危险背景，错误标签背景 |
| 浅-2 | red-20 | #FFDAD6 | 幽灵按钮点击态背景 |
| 浅-3 | red-30 | #FFCCC7 | 标签边框色 |
| 中-1 | red-40 | #FCB5B1 | 预留过渡色 |
| 中-2 | red-50 | #F08381 | 预留过渡色 |
| 中-3 | red-60 | #E35659 | 功能色危险色悬浮状态默认 |
| **深-1** | **red-70** | **#D63038** | **[错误基准色]** 危险背景色、边框色、文字色默认 |
| 深-2 | red-80 | #C2212E | 功能色危险色点击状态 |
| 深-3~6 | red-90~120 | - | 预留深度色 |

#### 橙色系 (Orange) —— 提醒、警示与注意

| 色阶 | 变量名 | HEX | 标准用途描述 |
|------|--------|-----|-------------|
| 浅-1 | orange-10 | #FFFAF2 | 轻微警告背景色，标签背景色 |
| 浅-3 | orange-30 | #FFE0B5 | 标签边框色 |
| **深-1** | **orange-70** | **#F57A12** | **[警告基准色]** 功能色警告背景色、边框色、文字色 |
| 深-2 | orange-80 | #DB5D04 | 预留交互态 |

#### 绿色系 (Green) —— 成功、通过与安全

| 色阶 | 变量名 | HEX | 标准用途描述 |
|------|--------|-----|-------------|
| 浅-1 | green-10 | #F5FFF2 | 功能色成功浅背景默认、徽标成功背景默认 |
| 浅-3 | green-30 | #B5F5A6 | 标签边框色 |
| **深-1** | **green-70** | **#10C107** | **[成功基准色]** 成功背景色，成功文字色 |
| 深-2 | green-80 | #03B300 | 预留交互态 |

#### 紫色系 (Purple) & 黄色系 (Yellow)

- **purple-70** (#7A1CED)：链接主文字访问后
- **yellow-10~120**：留作特定业务待处理、高亮信息提示等拓展储备

### 2. 中性色系调色板 (Neutral Palette)

承载系统 90% 以上的文字、边框、背景、分割线。

| 色阶 | 变量名 | HEX | 界面语义应用场景 |
|------|--------|-----|----------------|
| 白 | white | #FFFFFF | 浮层背景默认、反色文字/图标默认、开关背景 |
| 浅-1 | gray-10 | #F9FBFE | 容器背景悬浮态（按钮悬浮/页签选中/表格斑马线） |
| 浅-2 | gray-20 | #F2F5FA | 容器背景点击态 |
| 浅-3 | gray-30 | #E4E8F0 | 容器背景禁用态、最下层布局背景、默认分割线 |
| 浅-4 | gray-40 | #D1D6E0 | 默认容器边框颜色 |
| 浅-5 | gray-50 | #BEC3CE | 图标禁用色 |
| 中-1 | gray-60 | #A7ACB7 | 次要辅助文本 |
| 中-2 | gray-70 | #8F949F | 禁用态文字色、辅助图标颜色 |
| 中-3 | gray-80 | #777C87 | 中性色次要图标默认 |
| 中-4 | gray-90 | #606570 | 次要标题、次要正文、表头文本、默认图标颜色 |
| 深-1 | gray-100 | #494E59 | Tooltip气泡背景、侧边导航栏背景 |
| 深-2 | gray-110 | #313641 | 预留深度文本色 |
| **深-3** | **gray-120** | **#212630** | **标题/主文字颜色** |

---

## 二、全局字体系统 (Global Typography System)

### 1. 字体基础属性

- **中文字体族**：Microsoft YaHei (微软雅黑)
- **英文字体族**：Arial
- **基础字重**：400 (Regular) / 700 (Bold)
- **CSS变量**：`--font-family-base: Arial, "Microsoft YaHei", sans-serif;`

### 2. 字体排版矩阵 (Typography Matrix)

| 字号 | 字重 | 核心应用场景说明 |
|------|------|----------------|
| 12px | 400 | 辅助说明文本、页签 |
| 14px | 400 | 系统正文、常规字体（表格内容、普通表单） |
| 14px | 700 | 正文小标题 |
| 16px | 400 | 需要突出的正文 |
| 16px | 700 | 页面子标题、弹框子标题 |
| 18px | 700 | 页面一级标题、弹窗一级标题 |
| 22px / 24px | 700 | 其他需要醒目展示的标题 |
| 32px | 700 | 重点数字（数据大屏、关键核心指标） |

### 3. 字高行间距规则

- **单行文字 (135%)**：`--line-height-single: 1.35` — 按钮文字、表格单行内容、标签页名称等
- **双行及以上文字 (160%)**：`--line-height-multi: 1.60` — 多行段落说明、长文本公告

---

## 三、全局圆角系统 (Global Radius System)

| 圆角尺寸 | 变量名 | 适用组件与场景描述 |
|----------|--------|-------------------|
| 0px | `--radius-none` | 大型结构化容器：外层页面大布局框架、通栏大卡片 |
| 2px | `--radius-sm` | 微型/紧凑型组件：Tag、Radio、Checkbox、排序图标 |
| 4px | `--radius-md` | 标准业务组件：Button、Input、Select、Message、Table |
| 50% | `--radius-round` | 特殊动态与核心控件：纯图标圆形按钮、进度条 |

---

## 四、全局间距系统 (Global Spacing System)

基于 **4倍/8倍网格**，严格遵循"亲近疏远原则"。

| 间距尺寸 | 变量名 | 空间关系特征 | 核心适用场景 |
|----------|--------|-------------|-------------|
| 0px | `--spacing-none` | 完全紧贴 | 组件、容器间的无缝拼接 |
| 4px | `--spacing-xs` | 极紧凑/原子亲密 | 分页器页码间距、icon与hint文本间距 |
| 8px | `--spacing-sm` | 超紧凑/紧密组件关系 | 按钮组、下拉选项 |
| 12px | `--spacing-md` | 紧凑/容器内边距 | 带分割线小容器的内边距 |
| 16px | `--spacing-lg` | 常规/块内并列关系 | 表单内元素间距、小模块卡片内边距 |
| 24px | `--spacing-xl` | 宽松/区块分割关系 | 同一容器内信息区块的分割 |
| 32px | `--spacing-xxl` | 较宽松/呼吸感与强调 | 大看板指标、突出关键信息 |

---

## 五、全局阴影与高度系统 (Global Shadow System)

阴影基色统一采用中性偏冷色调 `rgba(117, 130, 156, Alpha)`：

| 级别 | CSS定义 | 用途 |
|------|---------|------|
| 1级 | `--shadow-lvl1: 0 1px 6px rgba(117, 130, 156, 0.1)` | 直铺在页面上的元素，如卡片 |
| 2级 | `--shadow-lvl2: 0 2px 12px rgba(117, 130, 156, 0.2)` | 有连接点的弹出层，如下拉菜单、日期选择器 |
| 2级分支 | `--shadow-lvl2-dir: 0 0 12px 2px rgba(117, 130, 156, 0.2)` | 单向裁剪阴影（吸底按钮、表格固定列投影） |
| 3级 | `--shadow-lvl3: 0 4px 16px rgba(117, 130, 156, 0.3)` | 悬浮态、Toast反馈 |
| 4级 | `--shadow-lvl4: 0 10px 24px rgba(117, 130, 156, 0.3)` | 独立大弹窗等最高阻断层 |

---

## 六、CSS Design Tokens 完整定义

```css
:root {
  /* ========== 颜色系统变量 ========== */
  /* 蓝色系 */
  --color-blue-10: #F7FBFF; --color-blue-20: #E0EEFF; --color-blue-30: #D6E8FF;
  --color-blue-40: #BAD8FF; --color-blue-50: #69A0FF; --color-blue-60: #3D79F2;
  --color-blue-70: #1553E5; --color-blue-80: #093ED1; --color-blue-90: #002499;
  --color-blue-100: #001773; --color-blue-110: #000D4D; --color-blue-120: #000526;

  /* 红色系 */
--color-red-60: #E35659; --color-red-70: #D63038; --color-red-80: #C2212E;

  /* 橙色系 */
  --color-orange-10: #FFFAF2; --color-orange-30: #FFE0B5; --color-orange-70: #F57A12;

  /* 绿色系 */
  --color-green-10: #F5FFF2; --color-green-30: #B5F5A6; --color-green-70: #10C107;

  /* 紫色系 */
  --color-purple-70: #7A1CED;

  /* 中性色系 */
  --color-neutral-white: #FFFFFF;
  --color-neutral-gray-10: #F9FBFE;  --color-neutral-gray-20: #F2F5FA;
  --color-neutral-gray-30: #E4E8F0;  --color-neutral-gray-40: #D1D6E0;
  --color-neutral-gray-50: #BEC3CE;  --color-neutral-gray-60: #A7ACB7;
  --color-neutral-gray-70: #8F949F;  --color-neutral-gray-80: #777C87;
  --color-neutral-gray-90: #606570;  --color-neutral-gray-100: #494E59;
  --color-neutral-gray-120: #212630;

  /* ========== 字体与排版变量 ========== */
  --font-family-base: Arial, "Microsoft YaHei", sans-serif;
  --line-height-single: 1.35;
  --line-height-multi: 1.60;

  /* ========== 圆角变量 ========== */
  --radius-none: 0px;  --radius-sm: 2px;  --radius-md: 4px;  --radius-round: 50%;

  /* ========== 间距变量 ========== */
  --spacing-none: 0px;  --spacing-xs: 4px;  --spacing-sm: 8px;  --spacing-md: 12px;
  --spacing-lg: 16px;   --spacing-xl: 24px;  --spacing-xxl: 32px;

  /* ========== 阴影变量 ========== */
  --shadow-lvl1: 0 1px 6px rgba(117, 130, 156, 0.1);
  --shadow-lvl2: 0 2px 12px rgba(117, 130, 156, 0.2);
  --shadow-lvl2-dir: 0 0 12px 2px rgba(117, 130, 156, 0.2);
  --shadow-lvl3: 0 4px 16px rgba(117, 130, 156, 0.3);
  --shadow-lvl4: 0 10px 24px rgba(117, 130, 156, 0.3);
}
```

---

## 七、组件规范

### 7.1 按钮组件 (Button & Dropdown Button)

#### 尺寸矩阵

| 尺寸等级 | 高度 | 最小宽度 | 水平内边距 | 字号 | 字重 | 行高 | 圆角 |
|----------|------|---------|-----------|------|------|------|------|
| Large | 36px | 80px | 16px (`--spacing-lg`) | 16px | 400 | 1.35 | `--radius-md` |
| Medium | 32px | 72px | 12px (`--spacing-md`) | 14px | 400 | 1.35 | `--radius-md` |
| Small | 24px | 64px | 8px (`--spacing-sm`) | 12px | 400 | 1.35 | `--radius-md` |

- **特殊圆角**：纯图标圆形按钮使用 `--radius-round` (50%)
- **图标与文本间距**：固定 4px (`--spacing-xs`)

#### 按钮类型与状态样式

**主要按钮 (Primary)**：
- Default: 背景 `--color-blue-70` | 文字 `--color-neutral-white`
- Hover: 背景 `--color-blue-60`
- Active: 背景 `--color-blue-80`
- Disabled: 背景 `--color-neutral-gray-30` | 文字 `--color-neutral-white`

**次要按钮 (Secondary) —— 蓝色系**：
- Default: 背景 `--color-neutral-white` | 边框 `--color-blue-70` | 文字 `--color-blue-70`
- Hover: 背景 `--color-blue-10` | 边框 `--color-blue-70` | 文字 `--color-blue-70`
- Active: 背景 `--color-blue-20` | 边框 `--color-blue-80` | 文字 `--color-blue-80`
- Disabled: 背景 `--color-neutral-gray-30` | 边框 `--color-blue-60` | 文字 `--color-blue-60`

**描边按钮 (Stroke) —— 中性灰色系**：
- Default: 背景 `--color-neutral-white` | 边框 `--color-neutral-gray-40` | 文字 `--color-neutral-gray-120`
- Hover: 背景 `--color-neutral-gray-10`
- Active: 背景 `--color-neutral-gray-20`
- Disabled: 背景 `--color-neutral-gray-30` | 文字 `--color-neutral-gray-70`

**文字按钮 (Text) —— 蓝色系**：
- Default: 背景 transparent | 文字 `--color-blue-70`
- Hover: 背景 `--color-blue-10`
- Active: 背景 `--color-blue-20` | 文字 `--color-blue-80`
- Disabled: 背景 transparent | 文字 `--color-blue-60`

**主要风险按钮 (Danger Primary)**：
- Default: 背景 `--color-red-70` | 文字 `--color-neutral-white`
- Hover: 背景 `--color-red-60`
- Active: 背景 `--color-red-80`
- Disabled: 背景 `--color-red-30` | 文字 `--color-neutral-white`

**描边风险按钮 (Danger Stroke)**：
- Default: 背景 `--color-neutral-white` | 边框 `--color-red-70` | 文字 `--color-red-70`
- Hover: 背景 `--color-red-10`
- Active: 背景 `--color-red-20` | 边框 `--color-red-80` | 文字 `--color-red-80`
- Disabled: 背景 `--color-neutral-white` | 边框 `--color-red-30` | 文字 `--color-red-30`

**文字风险按钮 (Danger Text)**：
- Default: 背景 transparent | 文字 `--color-red-70`
- Hover: 背景 `--color-red-10`
- Active: 背景 `--color-red-20` | 文字 `--color-red-80`
- Disabled: 背景 transparent | 文字 `--color-red-30`

**幽灵按钮 (Ghost)**：任何状态下背景保持透明。
- Default: 边框 `--color-blue-70` | 文字 `--color-blue-70`
- Hover: 边框 `--color-blue-60` | 文字 `--color-blue-60`
- Active: 边框 `--color-blue-80` | 文字 `--color-blue-80`
- Disabled: 边框 `--color-neutral-gray-50` | 文字 `--color-neutral-gray-50`

**链接按钮 (Link)**：完全遵循蓝色系文字按钮规范。

**下拉按钮 (Dropdown)**：
- 组合按钮：左侧行动点与右侧下拉三角区通过 1px 分割线切分，分割线颜色 `--color-neutral-gray-40`
- 折叠按钮：整体点击块，样式复用对应描边按钮与文字按钮规范
- 右侧文本与向下箭头间距固定 4px (`--spacing-xs`)

#### CSS 示例（中尺寸主要按钮）

```css
.btn-primary-md {
  height: 32px; min-width: 72px;
  padding: 0 var(--spacing-md);
  font-size: 14px; font-family: var(--font-family-base);
  line-height: var(--line-height-single);
  border-radius: var(--radius-md);
  background-color: var(--color-blue-70);
  color: var(--color-neutral-white);
  border: none; cursor: pointer;
  transition: background-color 0.2s ease;
}
.btn-primary-md:hover { background-color: var(--color-blue-60); }
.btn-primary-md:active { background-color: var(--color-blue-80); }
.btn-primary-md:disabled { background-color: var(--color-neutral-gray-30); cursor: not-allowed; }
```

---

### 7.2 分页组件 (Pagination)

- **统一高度**：24px
- **字号**：所有数字与标签文本统一 14px
- **圆角**：`--radius-md` (4px)
- **页码间距**：8px (`--spacing-sm`)
- **结构级间距**：页码组与每页条数下拉菜单之间 16px (`--spacing-lg`)
- **每页条数文案**：`[X] / page`（如 `10 / page`）
- **快捷跳转文案**：`Go to [输入框] Page`
- **省略号**：静态文本，不可点击，无交互状态

**页码项与箭头状态**：
- Default: 背景 `--color-neutral-white` | 边框 1px solid `--color-neutral-gray-40` | 文字 `--color-neutral-gray-120`
- Hover: 背景 `--color-neutral-gray-10`
- Active: 背景 `--color-neutral-gray-20`
- Selected: 背景 `--color-neutral-white` | 边框 `--color-blue-70` | 文字 `--color-blue-70`
- Disabled: 背景 `--color-neutral-gray-30` | 边框 `--color-neutral-gray-40` | 图标 `--color-neutral-gray-70`

**底部通栏布局**：`justify-content: space-between`，左侧 `Total ${total} items`，右侧分页组件。

---

### 7.3 Tabs 标签页组件

| 场景类型 | 容器高度 | 字号 | 选中字重 | 默认字重 | 标签项间距 |
|----------|---------|------|---------|---------|-----------|
| Header Tabs | 48px | 18px | 500 (Medium) | 400 (Regular) | 24px (`--spacing-xl`) |
| Container Tabs | 40px | 16px | 500 (Medium) | 400 (Regular) | 24px (`--spacing-xl`) |

**线条版 (Line Tabs)**：
- 选中态：文字 `--color-blue-70`，下方 Active Bar 2px 高，颜色 `--color-blue-70`
- 默认：文字 `--color-neutral-gray-120`，无下划线
- Hover：文字 `--color-blue-60`，不显示下划线
- Disabled：文字 `--color-neutral-gray-50`，`cursor: not-allowed`
- 底部通栏分割线：1px，颜色 `--color-neutral-gray-40`

**分隔符版 (Divider Tabs)**：
- 标签项之间使用垂直线 `|` 切分，颜色 `--color-neutral-gray-40`，任何状态下常亮不消失
- 色彩映射同线条版

---

### 7.4 导航菜单组件 (Navigation Menu)

#### 侧边导航 (Sidebar)

- **菜单项高度**：40px（Level 1/2/3 统一）
- **字号**：14px
- **Level 1 字重**：展开/激活态 500 (Medium)
- **Level 2/3 字重**：400 (Regular)
- **缩进规则**：Level 1 `padding-left: 16px` → Level 2 `padding-left: 32px` → Level 3 `padding-left: 48px`
- **右侧安全边距**：统一 16px (`--spacing-lg`)

**收起状态**：
- Icon-Only：侧边栏缩窄至仅图标，Hover 弹出 Tooltip 显示 "Menu item"
- Flyout：Hover 弹出悬浮面板级联菜单

**收藏星标**：已收藏态全局锁定金黄色 `--color-gold-60`，未收藏态 `--color-neutral-gray-70`

#### 顶部导航 (Top Header)

- **统一高度**：48px
- **水平内边距**：16px (`--spacing-lg`)
- **Dark Theme**：背景 `--color-neutral-dark-90`，默认文字 `--color-neutral-gray-60`
- **Light Theme**：背景 `--color-neutral-white`

#### 全局状态映射

| 状态 | 文字/图标 | 背景 |
|------|----------|------|
| Normal | `--color-neutral-gray-120` | transparent |
| Hover | `--color-blue-70` | `--color-neutral-gray-10` |
| Active/Selected | `--color-blue-70` | `--color-blue-10`（左侧 3px 蓝色指示线） |
| Disabled | `--color-neutral-gray-50` | - |

---

### 7.5 下拉菜单组件 (Dropdown)

- **单项高度**：32px
- **字号**：14px
- **横向内边距**：12px (`--spacing-md`)
- **弹窗纵向留白**：顶部与底部各 4px (`--spacing-xs`)
- **圆角**：`--radius-md` (4px)
- **取消 Selected 选中态**（点击即触发回调并关闭）

**状态映射**：
- Normal: 文字 `--color-neutral-gray-120` | 背景 transparent
- Hover: 文字 `--color-neutral-gray-120` | 背景 `--color-neutral-gray-10`
- Active: 文字 `--color-neutral-gray-120` | 背景 `--color-neutral-gray-20`
- Disabled: 文字 `--color-neutral-gray-50` | 背景交互锁定 | `cursor: not-allowed`

**分组分割线**：1px，颜色 `--color-neutral-gray-40`，上下 margin 4px

**Popover 定位**：支持 Bottom Left/Right、Top Left/Right，自适应视口边界

---

### 7.6 锚点组件 (Anchor)

- **单项高度**：36px
- **字号**：14px
- **轨道线宽度**：2px，颜色 `--color-neutral-gray-40`
- **激活状态条**：2px 高亮蓝色线段，颜色 `--color-blue-70`
- **轨道与文本间距**：8px (`--spacing-sm`)
- **多级缩进**：二级子项向右缩进 16px (`--spacing-md`)

**状态映射**：
- Normal: 文字 `--color-neutral-gray-120` | 字重 400
- Hover: 文字 `--color-blue-60` | 背景 `--color-neutral-gray-10`
- Active: 文字 `--color-blue-70` | 字重 **700** | 左侧 2px 蓝色激活条亮起
- Pressed: 文字 `--color-blue-70` | 字重 700 | 背景 `--color-neutral-gray-20`

---

### 7.7 步骤条组件 (Steps)

| 类型 | 节点尺寸 | 连接线 |
|------|---------|--------|
| Base/Icon Steps | 32px 直径 | 1px 贯穿连接线 |
| Dot Steps | 8px 直径 | - |
| 标题字号 | 14px | - |
| 描述字号 | 12px | - |
| 节点与文本间距 | 8px (`--spacing-sm`) | - |

**状态体系**：
- **Finished**：节点背景 `--color-blue-60`，内部勾选图标白色，连接线变蓝，标题文字 `--color-neutral-gray-120` 字重 400
- **In Progress**：节点背景 `--color-blue-60`，内部数字/图标白色，标题 `--color-blue-70` 字重 **700**，描述 400
- **Waiting**：节点 `--color-neutral-gray-50`，连接线 `--color-neutral-gray-40`，标题/描述 `--color-neutral-gray-60` 字重 400，**锁定所有交互**（`pointer-events: none`）
- **Error**：节点、标题及描述全量转为 `--color-red-60`，标题字重 700
- **Hover（仅导航步骤的已完成项）**：标题变 `--color-blue-70`，字重 400，**不加下划线**

---

### 7.8 输入框组件 (Input)

#### 尺寸矩阵

| 尺寸 | 高度 | 字号 | 水平内边距 | 行高 |
|------|------|------|-----------|------|
| Large (默认) | 32px | 14px | 12px | - |
| Medium | 28px | 14px | 12px | 强制 18px |
| Small | 24px | 12px | 8px | - |

- **圆角**：统一 2px (`--radius-xs`)
- **默认宽度**：320px
- **文本域 (Textarea)**：固定高度 96px，`resize: none`，`overflow-y: auto`

**状态映射**：
- Default: 边框 `--color-neutral-gray-40` | placeholder `--color-neutral-gray-60`
- Hover: 边框 `--color-blue-60`
- Focus: 边框 `--color-blue-70`
- Filled: 文字 `--color-neutral-gray-120` 字重 400
- Disabled: 背景 `--color-neutral-gray-20` | `cursor: not-allowed`
- Success: 边框 `--color-green-60` | 后缀绿色成功图标
- Error: 边框 `--color-red-60` | 下方红色提示文字（字重 400）
- Warning: 边框 `--color-orange-60` | 下方橙色提示文字（字重 400）

**金额输入框**：前轴锁死币种选择器，后轴允许清除图标或金额单位标签，数值右对齐。

---

### 7.9 表单容器组件 (Form)

#### 布局模式

| 布局 | 说明 |
|------|------|
| Vertical | 标签位于控件正上方，默认通用布局 |
| Horizontal | 标签与控件同一水平行，标签列宽 **160px**，文字强制右对齐 |
| Two-Column Grid | 双列网格布局，列间距 40px |

#### 间距矩阵

| 控制项 | 间距 |
|--------|------|
| 表单标题到首行 | 20px (`--spacing-xl`) |
| 行间距 | 20px (`--spacing-xl`) |
| 标签到控件（垂直） | 4px (`--spacing-xs`) |
| 标签到控件（水平） | 8px (`--spacing-sm`) |
| 列间距 | 40px (`--spacing-xxl`) |
| 操作栏边距顶部 | 16px (`--spacing-lg`) |
| 按钮间距 | 16px (`--spacing-lg`) |

**字段标签**：14px，颜色 `--color-neutral-gray-100`，字重 400，严禁加粗。必填前置红星 `*` 颜色 `--color-red-60`。

**校验提示**：最大两行显示，超出省略号 `...`。双列布局下报错时整行高度同步拉伸。

**操作栏**：一律右靠齐 (`justify-content: flex-end`)。

---

### 7.10 上传组件 (Upload)

| 控制项 | 值 |
|--------|-----|
| 上传按钮高度 | 32px |
| 按钮到列表间距 | 8px (`--spacing-sm`) |
| 文件列表行高 | 32px |
| 文件列表最大行数 | 5 Rows |
| 文件列表最大高度 | 160px（超出滚动） |
| 图片墙盒尺寸 | 120px × 120px |
| 网格项目间隙 | 12px (`--spacing-md`) |

**拖放区域**：初始 500px × 292px，首文件上传成功后动画收缩为 32px 按钮。

**图片墙悬停**：60% 不透明度遮罩，居中显示预览图标 + 删除图标（白色，16px，间距 16px）。

---

### 7.11 日期时间选择器 (Date/Time Picker)

| 控制项 | 值 |
|--------|-----|
| 触发输入高度 | 32px |
| 边界半径 | 2px (`--radius-xs`) |
| 日历单元格大小 | 24px × 24px |
| 时间滚动条最大高度 | 240px |
| 输入模式 | `readonly`（禁止键盘手动输入） |
| 弹出策略 | Smart Flip（默认向下，靠边自动向左展开） |

**面板标题**：14px，字重 700
**日期单元格**：12px，字重 400

**核心补丁**：
1. 零键盘安全沙箱：`readonly` 属性强制绑定
2. 右外沿智能逃逸：宽度 ≥ 640px 时自动右对齐展开
3. 悬停动态区间预渲染：范围选择时实时平涂 `--color-blue-15` 淡蓝连绵带
4. 时间滚动列隐藏滚动条但保留滚轮事件

---

### 7.12 选择器组件 (Select)

| 控制项 | 值 |
|--------|-----|
| 触发框高度 | 32px（硬性锁死） |
| 边界半径 | 2px (`--radius-xs`) |
| 选项项高度 | 32px |
| 表格下拉面板最小宽度 | 520px |
| 多选流控 | `white-space: nowrap`，超出截断显示 `+N` |

**右侧挂件热区**：位置死锁固定，图标互斥替换（Clear Icon × > Search/Arrow Icon）

**级联 Smart Flip**：子菜单默认向右展开，触壁时逆向向左展开。

---

### 7.13 单选框组件 (Radio)

**Base Radio**：
- 圆点与文字间距：8px
- 横向选项间距：16px

**Button Radio 三级尺寸**：

| 尺寸 | 高度 | 横向内衬 | 字号 |
|------|------|---------|------|
| Large | 32px | 0 12px | 16px |
| Medium | 28px | 0 12px | 14px |
| Small | 24px | 0 8px | 12px |

**业务逻辑铁律**：
1. 对立相反选项（同意/不同意、是/否）必须用 Radio 或 Switch，严禁 Checkbox
2. 平铺选项上限 4 个，≥5 个自动降级为 Select
3. 默认选中第 1 个选项（法律合规协议除外）
4. 支持 6 种状态：Default / Hover / Focus / Selected / Disabled-未选 / Disabled-已选

---

### 7.14 复选框组件 (Checkbox)

**方框尺寸**：16px × 16px，2px 微圆角
**方框与文字间距**：8px（与 Radio 拉齐）
**横向项间距**：16px
**纵向项间距**：8px

**三级行高集装箱矩阵**：

| 尺寸 | 行高 | 字号 | 适用上下文 |
|------|------|------|-----------|
| Large | 32px | 14px/16px | L 码输入框、大表单行 |
| Medium | 28px | 14px | M 码标准表单行 |
| Small | 24px | 12px | 高密输入框、筛选匹配 |

**7 种状态**：Default / Hover / Selected / Disabled（未选）/ SelectedDisabled（选中禁用）/ Indeterminate（半选）/ IndeterminateDisabled（半选禁用）

**半选熔断控制链**：半选状态点击时，强制跳过中间状态直接进入全选（Selected），并全量勾选所有子代节点。

**CSS 示例**：
```css
.checkbox-base-item { display: inline-flex; align-items: center; cursor: pointer; user-select: none; }
.checkbox-base-item.size-large { height: 32px !important; }
.checkbox-base-item.size-medium { height: 28px !important; }
.checkbox-base-item.size-small { height: 24px !important; }
.checkbox-inner-square { width: 16px; height: 16px; border: 1px solid var(--color-neutral-gray-30); border-radius: 2px; background-color: var(--color-neutral-white); flex-shrink: 0; }
.checkbox-label-text { padding-left: 8px; color: var(--color-neutral-gray-90); }
/* Selected */
.checkbox-base-item.is-selected .checkbox-inner-square { background-color: var(--color-blue-60); border-color: var(--color-blue-60); }
.checkbox-base-item.is-selected .checkbox-inner-square::after { content: ""; position: absolute; left: 5px; top: 2px; width: 4px; height: 8px; border: 2px solid var(--color-neutral-white); border-left: 0; border-top: 0; transform: rotate(45deg); }
/* Indeterminate */
.checkbox-base-item.is-indeterminate .checkbox-inner-square { background-color: var(--color-blue-60); border-color: var(--color-blue-60); }
.checkbox-base-item.is-indeterminate .checkbox-inner-square::after { content: ""; position: absolute; left: 3px; top: 7px; width: 8px; height: 2px; background-color: var(--color-neutral-white); }
/* Disabled */
.checkbox-base-item.is-disabled { cursor: not-allowed !important; }
.checkbox-base-item.is-disabled .checkbox-inner-square { background-color: var(--color-neutral-gray-10) !important; border-color: var(--color-neutral-gray-30) !important; }
.checkbox-base-item.is-disabled .checkbox-label-text { color: var(--color-neutral-gray-40); }
```

---

### 7.15 表格组件 (Table)

**结构概览**：表头 (Header) + 内容区 (Body) + 分割线 (Divider) + 底部区 (Footer)

**核心视觉 Tokens**：

| 视觉元素 | Token |
|----------|-------|
| 表头背景 | `--color-neutral-gray-30` |
| 斑马线（隔行） | `--color-neutral-gray-10` |
| 行悬浮态 | `--color-neutral-gray-20` |
| 行选中态 | `--color-blue-20` |
| 默认边框 | `--color-neutral-gray-40` |
| 表头文本 | `--color-neutral-gray-90` |
| 次要辅助文本 | `--color-neutral-gray-60` |
| 微型组件圆角 | `--radius-sm` |
| 行间距 | `--spacing-md` / `--spacing-lg` |

**布局与交互规则**：
- **行高**：单行 40px，多行折行 58px（行高 `--line-height-single` 135%）
- **斑马线**：行数 > 8 时开启，`:nth-child(even)` 实现，交互态优先级高于斑马线。斑马线单元格不显示边框，仅保留表格整体外边框。
- **响应式**：内容未占满时列宽按比例拉伸；超出容器时启用横向滚动，右侧固定列施加 `--shadow-lvl2-dir`
- **对齐**：文字左对齐；金额/数值右对齐；操作列自适应

**CSS 示例**：
```css
.table-component { border: 1px solid var(--color-neutral-gray-40); }
.table-header { background-color: var(--color-neutral-gray-30); color: var(--color-neutral-gray-90); font-weight: 700; }
.table-row { height: 40px; }
.table-row:nth-child(even) { background-color: var(--color-neutral-gray-10); }
.table-row:hover { background-color: var(--color-neutral-gray-20); }
.table-row.is-selected { background-color: var(--color-blue-20); }
.action-btn { color: var(--color-blue-70); }
.action-btn.danger { color: var(--color-red-70); }
```

---

### 7.16 树选择组件 (TreeSelect)

| 视觉元素 | Token/值 |
|----------|---------|
| 层级缩进 | `--spacing-lg` (16px) 每层递进 |
| 行高 | 32px（固定） |
| 组件圆角 | `--radius-md` (4px) |
| 内容左边距 | `--spacing-md` (12px) |
| 图标间距 | `--spacing-xs` (4px) |

**状态映射**：
- Default: 文字 `--color-neutral-gray-120`
- Hover: 背景 `--color-neutral-gray-10`
- Active: 背景 `--color-neutral-gray-20`
- Selected: 背景 `--color-blue-20` | 文字及选框 `--color-blue-70`
- Disabled: 颜色 `--color-neutral-gray-70`

**交互规则**：点击展开图标触发节点收起/展开，点击节点行触发选中逻辑。在表格中使用时树节点必须与表格行对齐。

**CSS 示例**：
```css
.tree-node { height: 32px; padding-left: var(--spacing-md); border-radius: var(--radius-md); transition: background-color 0.2s; }
.tree-node:hover { background-color: var(--color-neutral-gray-10); }
.tree-node:active { background-color: var(--color-neutral-gray-20); }
.tree-node.is-selected { background-color: var(--color-blue-20); color: var(--color-blue-70); }
.tree-node-level-1 { padding-left: calc(var(--spacing-md) + (0 * 16px)); }
.tree-node-level-2 { padding-left: calc(var(--spacing-md) + (1 * 16px)); }
.tree-node-level-3 { padding-left: calc(var(--spacing-md) + (2 * 16px)); }
.tree-icon { margin-right: var(--spacing-xs); }
```

---

### 7.17 搜索框组件 (Search)

| 视觉元素 | Token/值 |
|----------|---------|
| 容器圆角 | `--radius-md` (4px) |
| 默认边框 | `--color-neutral-gray-40` |
| 聚焦边框 | `--color-blue-70` |
| 输入文字 | `--color-neutral-gray-120` |
| 占位符 | `--color-neutral-gray-70` |
| 内部间距 | `--spacing-md` / `--spacing-sm` |

**状态交互**：
- Default: 边框 `--color-neutral-gray-40`，背景白色
- Hover: 边框 `--color-neutral-gray-70`（带 transition 动效）
- Focus: 边框 `--color-blue-70`，可选触发 `--shadow-lvl1`
- Filled: 文字 `--color-neutral-gray-120`

**下拉联想面板**：
- 面板背景 `--color-neutral-white`
- Hover 项背景 `--color-neutral-gray-10`
- 选中项背景 `--color-blue-20`，文字 `--color-blue-70`
- 无结果："No result"，颜色 `--color-neutral-gray-70`
- 加载态：Loading 动画，主色调 `--color-blue-70`

**CSS 示例**：
```css
.search-container { border-radius: var(--radius-md); border: 1px solid var(--color-neutral-gray-40); transition: border-color 0.2s; }
.search-container:hover { border-color: var(--color-neutral-gray-70); }
.search-container:focus-within { border-color: var(--color-blue-70); box-shadow: 0 0 0 2px rgba(21, 83, 229, 0.1); }
.search-input::placeholder { color: var(--color-neutral-gray-70); }
.search-input { color: var(--color-neutral-gray-120); }
.search-dropdown { background: var(--color-neutral-white); box-shadow: var(--shadow-lvl2); }
```

---

### 7.18 开关组件 (Switch)

| 视觉元素 | Token/值 |
|----------|---------|
| 容器圆角 | `--radius-round` (50%) |
| 打开背景 | `--color-blue-70` |
| 关闭背景 | `--color-neutral-gray-70` |
| 禁用背景 | `--color-neutral-gray-40` |
| 滑块颜色 | `--color-neutral-white` |
| Label 间距 | `--spacing-sm` (8px) |

**尺寸**：
- Large：高度 24px，宽度 44px
- Small：高度 16px，宽度 30px

**状态**：
- Open：背景 `--color-blue-70`
- Close：背景 `--color-neutral-gray-70`
- Disabled：背景 `--color-neutral-gray-40`，禁止任何点击交互

**CSS 示例**：
```css
.switch-base { border-radius: var(--radius-round); cursor: pointer; transition: background-color 0.2s; display: inline-flex; align-items: center; }
.switch-large { height: 24px; width: 44px; }
.switch-small { height: 16px; width: 30px; }
.switch-base.is-open { background-color: var(--color-blue-70); }
.switch-base.is-close { background-color: var(--color-neutral-gray-70); }
.switch-base.is-disabled { background-color: var(--color-neutral-gray-40); cursor: not-allowed; }
.switch-thumb { background-color: var(--color-neutral-white); border-radius: var(--radius-round); }
.switch-with-label { gap: var(--spacing-sm); }
```

---

### 7.19 穿梭框组件 (Transfer)

| 视觉元素 | Token/值 |
|----------|---------|
| 容器外框 | `--color-neutral-gray-40` |
| 表头背景 | `--color-neutral-gray-30` |
| 行悬浮态 | `--color-neutral-gray-20` |
| 行选中态 | `--color-blue-20` |
| 按钮激活色 | `--color-blue-70` |
| 容器圆角 | `--radius-md` (4px) |
| 组件行高 | 32px |

**交互原则**：
- 单向穿梭：仅支持从左至右（简单权限赋予）
- 双向穿梭：支持左右互迁（复杂数据分配）
- Hover：背景 `--color-neutral-gray-20`
- Selected：背景 `--color-blue-20`
- Disabled：文字 `--color-neutral-gray-70`
- 空状态："No result"，颜色 `--color-neutral-gray-70`

**CSS 示例**：
```css
.transfer-container { border: 1px solid var(--color-neutral-gray-40); border-radius: var(--radius-md); }
.transfer-header { background-color: var(--color-neutral-gray-30); height: 32px; }
.transfer-item { height: 32px; transition: background-color 0.2s; }
.transfer-item:hover { background-color: var(--color-neutral-gray-20); }
.transfer-item.is-selected { background-color: var(--color-blue-20); }
.transfer-btn { border: 1px solid var(--color-neutral-gray-40); color: var(--color-neutral-gray-90); border-radius: var(--radius-md); }
.transfer-btn:hover:not(:disabled) { border-color: var(--color-blue-70); color: var(--color-blue-70); }
```

---

### 7.20 描述列表组件 (Description)

| 视觉元素 | Token/值 |
|----------|---------|
| 标题 (Label) | 14px / `--color-neutral-gray-90` |
| 正文-上下排列 | 16px / `--color-neutral-gray-120` |
| 正文-左右排列 | 14px |
| 字段间垂直间距 | `--spacing-md` (12px) |
| 字段间水平间距 | `--spacing-xl` (24px) |
| 容器边框 | `--color-neutral-gray-40`（仅带边框模式） |

**布局规则**：
- 上下排列：适用于重要度高或内容较长的字段
- 左右排列：适用于字段较多、高密度展示，可配置双列或三列
- 行文本行高：`--line-height-single` (135%)
- 标签与内容间距：垂直 8px 或水平 12px
- 区块与区块间距：垂直 20px

**CSS 示例**：
```css
.desc-label { color: var(--color-neutral-gray-90); font-size: 14px; }
.desc-content-vertical { color: var(--color-neutral-gray-120); font-size: 16px; margin-top: 8px; }
.desc-content-horizontal { font-size: 14px; }
.desc-grid-container { display: grid; gap: var(--spacing-xl) 20px; }
.desc-bordered { border: 1px solid var(--color-neutral-gray-40); padding: var(--spacing-md); }
```

---

### 7.21 标签组件 (Tag)

| 视觉元素 | Token/值 |
|----------|---------|
| 标签圆角 | `--radius-sm` (2px) |
| 基础填充 | `--color-neutral-gray-10` |
| 成功填充 | `--color-green-10` |
| 警告填充 | `--color-orange-10` |
| 错误填充 | `--color-red-10` |
| 强调填充 | `--color-blue-10` |

**组件类型**：基础标签、可删除标签（含 × 关闭图标）、带图标标签、复合标签（图标+删除）、不带边框标签

**尺寸**：

| 尺寸 | 高度 |
|------|------|
| Large | 28px |
| Medium | 24px |
| Small | 20px |

**内部间距**：图标与文字 `--spacing-xs` (4px)，左右内边距 `--spacing-sm` (8px)

**CSS 示例**：
```css
.tag-base { border-radius: var(--radius-sm); padding: 0 var(--spacing-sm); display: inline-flex; align-items: center; gap: var(--spacing-xs); }
.tag-lg { height: 28px; }
.tag-md { height: 24px; }
.tag-sm { height: 20px; }
.tag-success { background-color: var(--color-green-10); color: var(--color-green-70); }
.tag-warning { background-color: var(--color-orange-10); color: var(--color-orange-70); }
.tag-error { background-color: var(--color-red-10); color: var(--color-red-70); }
```

---

### 7.22 徽标组件 (Badge)

| 徽标类型 | 尺寸 | 颜色 |
|----------|------|------|
| 小圆点徽标 | 6px × 6px | 默认 `--color-red-70` |
| 状态点徽标 | 6px (点) | 自定义（支持传入任意 Hex/变量） |
| 数字徽标 | 高度 20px | 默认 `--color-red-70` |
| 文字徽标 | 高度 20px | 默认 `--color-red-70` |

**布局规范**：
- 数字/文字徽标内边距：左右统一 6px
- 状态点与宿主间距：4px
- 数字容量：建议最大值展示为 "99+" 或 "999+"
- 文字容量：中文不超过 4 个字，英文不超过 5 个字母

**CSS 示例**：
```css
.badge-status-dot { width: 6px; height: 6px; border-radius: var(--radius-round); background-color: var(--badge-custom-color, var(--color-red-70)); }
```

---

### 7.23 文字提示组件 (Tooltip)

| 视觉元素 | Token/值 |
|----------|---------|
| 背景色 | `--color-neutral-gray-100` |
| 圆角 | `--radius-md` (4px) |
| 阴影 | `--shadow-lvl3` |
| 文本颜色 | `--color-neutral-white` |
| 组件间距 | `--spacing-xs` (4px) |

**使用场景**：
- 指向性文字提示：对图标功能的补充说明，触发后立即显示
- 省略标识的文字提示：内容因空间限制省略时，完整展示全部原始内容

**方位**：支持 12 个方位（上、下、左、右及其组合），首选上方 (Top)

**CSS 示例**：
```css
.tooltip-container { background-color: var(--color-neutral-gray-100); color: var(--color-neutral-white); padding: var(--spacing-sm) var(--spacing-md); border-radius: var(--radius-md); box-shadow: var(--shadow-lvl3); }
```

---

### 7.24 气泡卡片组件 (Popover)

| 视觉元素 | Token/值 |
|----------|---------|
| 容器圆角 | `--radius-md` (4px) |
| 容器内边距 | `--spacing-md` (12px) |
| 标题与正文间距 | 4px |
| 正文与操作栏间距 | 12px |
| 卡片阴影 | `--shadow-lvl3` |
| 最小宽度 | 200px |
| 最大宽度 | 400px |

**组件类型**：基础型（标题+正文+操作按钮）、带图标型（标题左侧图标）、带描述型

**交互逻辑**：Popover 仅用于承载交互型元素，不应仅作静态文本提示使用（与 Tooltip 严格区分）。支持 12 个方向，自动避让边缘。

**CSS 示例**：
```css
.popover-container { min-width: 200px; max-width: 400px; padding: var(--spacing-md); border-radius: var(--radius-md); box-shadow: var(--shadow-lvl3); display: flex; flex-direction: column; }
.popover-header { margin-bottom: 4px; }
.popover-footer { margin-top: 12px; display: flex; justify-content: flex-end; gap: 8px; }
```

---

### 7.25 加载组件 (Loading)

| 视觉元素 | Token/值 |
|----------|---------|
| 主环色 | `--color-blue-70` |
| 轨道颜色 | `--color-blue-20` |
| 圆角 | `--radius-round` (50%) |

**尺寸矩阵**：

| 尺寸 | 图标宽高 | 适用场景 | 文字间距 |
|------|---------|---------|---------|
| Large | 48px | 页面级全屏遮罩加载 | 8px (`--spacing-sm`) |
| Medium | 32px | 容器/区块内部加载 | 8px (`--spacing-sm`) |
| Small | 16px | 按钮内部/行内加载 | 4px (`--spacing-xs`) |

**布局规则**：严格居中于父容器，文字仅支持 12px 或 14px，行高 `--line-height-single` (1.35)

**CSS 示例**：
```css
.comp-loading { display: inline-flex; align-items: center; justify-content: center; border-radius: var(--radius-round); color: var(--color-blue-70); }
.comp-loading--lg { width: 48px; height: 48px; }
.comp-loading--md { width: 32px; height: 32px; }
.comp-loading--sm { width: 16px; height: 16px; }
.comp-loading-text { margin-left: var(--spacing-sm); }
.comp-loading--sm .comp-loading-text { margin-left: var(--spacing-xs); }
```

---

### 7.26 对话框组件 (Dialog)

**尺寸规格**：

| 尺寸 | 宽度 | 适用场景 |
|------|------|---------|
| Large | 1000px | 复杂业务表格、多列数据录入 |
| Medium | 720px | 标准双列表单、复杂详情展示 |
| Small | 400px | 确认二次、简单文本展示 |

**视觉风格**：
- 阴影：`--shadow-lvl4`（体系最高）
- 圆角：`--radius-md` (4px)
- 外部间距：容器内部上下统一 `--spacing-xl` (24px)
- 标题排版：18px / 700 字重，颜色 `--color-neutral-gray-120`
- 高度策略：内容自适应，设置 `max-height`，溢出内部滚动

**语义化类型**：
- 功能类：复杂录入，包含 Input、Select 等组件
- 确认类：二次确认，危险操作按钮使用 `--color-red-70`，普通确认使用 `--color-blue-70`
- 结果类：展示 Success/Error/Warning/Info 状态

**CSS 示例**：
```css
.comp-dialog { width: var(--dialog-width); border-radius: var(--radius-md); box-shadow: var(--shadow-lvl4); background: var(--color-neutral-white); padding: var(--spacing-xl); }
.comp-dialog-footer { display: flex; justify-content: flex-end; gap: var(--spacing-sm); margin-top: var(--spacing-lg); }
.comp-dialog-title { font-size: 18px; font-weight: 700; color: var(--color-neutral-gray-120); margin-bottom: var(--spacing-lg); }
```

---

### 7.27 进度条组件 (Progress)

#### 线形进度条

| 尺寸 | 轨道高度 | 尾部间距 | 文本字号 |
|------|---------|---------|---------|
| 标准型 | 8px | `--spacing-sm` (8px) | 12px (400) |
| 紧凑型 | 4px | `--spacing-xs` (4px) | 12px (400) |

#### 环形进度条

| 尺寸 | 外径 | 内部文本字号 |
|------|------|-------------|
| Large | 80 × 80 px | 14px (700) |
| Medium | 64 × 64 px | 12px (400) |

**状态与语义颜色**：

| 状态 | 激活色 | 轨道背景色 |
|------|--------|-----------|
| Processing | `--color-blue-70` | `--color-neutral-gray-30` |
| Success | `--color-green-70` | `--color-neutral-gray-30` |
| Exception | `--color-red-70` | `--color-neutral-gray-30` |

**CSS 示例**：
```css
.comp-progress-line { display: flex; align-items: center; width: 100%; }
.comp-progress-line__track { flex: 1; background-color: var(--color-neutral-gray-30); border-radius: var(--radius-round); overflow: hidden; }
.comp-progress-line--normal .comp-progress-line__track { height: 8px; }
.comp-progress-line--small .comp-progress-line__track { height: 4px; }
.comp-progress-line__bg { height: 100%; border-radius: var(--radius-round); transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
.comp-progress--processing .comp-progress-line__bg { background-color: var(--color-blue-70); }
.comp-progress--success .comp-progress-line__bg { background-color: var(--color-green-70); }
.comp-progress--exception .comp-progress-line__bg { background-color: var(--color-red-70); }
.comp-progress-line__text { color: var(--color-neutral-gray-90); font-size: 12px; line-height: var(--line-height-single); }
```

---

### 7.28 全局提示组件 (Message/Toast)

**4 种标准提示样式**：

| 类型 | 背景色 | 边框色 | 文字/图标色 |
|------|--------|--------|------------|
| Info | `--color-blue-10` | `--color-blue-30` | `--color-blue-70` |
| Success | `--color-green-10` | `--color-green-30` | `--color-green-70` |
| Warning | `--color-orange-10` | `--color-orange-30` | `--color-orange-70` |
| Error | `--color-red-10` | `--color-red-30` | `--color-red-70` |

**尺寸与排版**：
- 宽度：内容自适应（单行），文本过多建议改用 Notification
- 内边距：`padding: var(--spacing-sm) var(--spacing-lg)`（上下 8px，左右 16px）
- 元素间距：图标、文本、链接、关闭按钮之间固定 `--spacing-sm` (8px)
- 字体：14px / 400，行高 `--line-height-single` (1.35)

**布局与防抖逻辑**：
- 全局定位：内容区域顶部水平居中，距顶部 140px
- 自动关闭：3s 后自动消失
- 手动关闭：带关闭按钮/链接，不会自动消失
- 悬停暂停：Hover 时计时器暂停，移出后重新计算 3s
- 防连击：两次点击间隔 < 500ms 时不重复堆叠，> 500ms 时上一个消失后再出现

**CSS 示例**：
```css
.comp-message { position: fixed; top: 140px; left: 50%; transform: translateX(-50%); display: inline-flex; align-items: center; z-index: 1010; padding: var(--spacing-sm) var(--spacing-lg); border-width: 1px; border-style: solid; border-radius: var(--radius-md); box-shadow: var(--shadow-lvl3); font-size: 14px; font-weight: 400; line-height: var(--line-height-single); }
.comp-message--success { background-color: var(--color-green-10); border-color: var(--color-green-30); color: var(--color-green-70); }
.comp-message--error { background-color: var(--color-red-10); border-color: var(--color-red-30); color: var(--color-red-70); }
.comp-message--warning { background-color: var(--color-orange-10); border-color: var(--color-orange-30); color: var(--color-orange-70); }
.comp-message--info { background-color: var(--color-blue-10); border-color: var(--color-blue-30); color: var(--color-blue-70); }
```

---

### 7.29 警告信息组件 (Alert)

**4 种标准语义样式**：

| 类型 | 背景色 | 边框色 | 文字/图标色 |
|------|--------|--------|------------|
| Success | `--color-green-10` | `--color-green-30` | `--color-green-70` |
| Warning | `--color-orange-10` | `--color-orange-30` | `--color-orange-70` |
| Error | `--color-red-10` | `--color-red-30` | `--color-red-70` |
| Info | `--color-blue-10` | `--color-blue-30` | `--color-blue-70` |

**结构与布局**：
- 宽度：默认 1000px，实际开发 `width: 100%` 自适应父容器
- 内边距：`padding: var(--spacing-sm) var(--spacing-lg)`（上下 8px，左右 16px）
- 单行行高：`--line-height-single` (135%)
- 多行描述：`--line-height-multi` (160%)
- 标题与描述垂直间距：`--spacing-xs` (4px)
- 描述与折叠切换器间距：`--spacing-xs` (4px)
- 对齐：左侧核心图标、主标题、链接依次排列，间距 `--spacing-sm` (8px)；右侧关闭按钮始终右对齐

**交互扩展**：提供"查看更多"与"隐藏"折叠机制，默认显示单行/两行辅助文本

**CSS 示例**：
```css
.comp-alert { display: flex; align-items: flex-start; width: 100%; box-sizing: border-box; padding: var(--spacing-sm) var(--spacing-lg); border-width: 1px; border-style: solid; border-radius: var(--radius-md); box-shadow: none; }
.comp-alert__body { flex: 1; display: flex; flex-direction: column; }
.comp-alert__header { display: flex; align-items: center; font-size: 14px; font-weight: 400; line-height: var(--line-height-single); }
.comp-alert__icon { margin-right: var(--spacing-sm); flex-shrink: 0; }
.comp-alert__link { margin-left: var(--spacing-sm); cursor: pointer; text-decoration: none; }
.comp-alert__description { margin-top: var(--spacing-xs); color: var(--color-neutral-gray-90); font-size: 14px; line-height: var(--line-height-multi); }
.comp-alert__toggle-btn { margin-top: var(--spacing-xs); display: inline-flex; align-items: center; cursor: pointer; }
.comp-alert__close { margin-left: var(--spacing-lg); cursor: pointer; flex-shrink: 0; }
.comp-alert--info { background-color: var(--color-blue-10); border-color: var(--color-blue-30); color: var(--color-blue-70); }
.comp-alert--warning { background-color: var(--color-orange-10); border-color: var(--color-orange-30); color: var(--color-orange-70); }
.comp-alert--success { background-color: var(--color-green-10); border-color: var(--color-green-30); color: var(--color-green-70); }
.comp-alert--error { background-color: var(--color-red-10); border-color: var(--color-red-30); color: var(--color-red-70); }
```

---

### 7.30 结果组件 (Result)

**布局模式**：
- **上下布局 (Centered - 默认)**：所有元素水平居中对齐，适用于独立结果页、全屏遮罩
- **左右布局 (Horizontal)**：状态图标置于左侧顶部，右侧内容依次排列，适用于 Drawer、Dialog

**5 种状态**：

| 状态 | 图标类型 | 核心色 Token |
|------|---------|-------------|
| Success | Check 图标 | `--color-green-70` |
| Info | Info 图标 | `--color-blue-70` |
| Warning | Warning 图标 | `--color-orange-70` |
| Error | Cross 图标 | `--color-red-70` |
| Processing | 动态时钟/加载图标 | `--color-blue-60` |

**间距矩阵（上下布局）**：
```
[状态图标]
     │  <-- --spacing-xl (24px)
[结果主标题] 18px / 700 / --color-neutral-gray-120
     │  <-- --spacing-md (12px)
[结果解释文本] 14px / 400 / --color-neutral-gray-90
     │  <-- --spacing-xl (24px)
[灰色补充信息卡片] 背景 --color-neutral-gray-10，内边距 --spacing-lg (16px)
     │  <-- --spacing-xl (24px)
[操作按钮组] 按钮间距 --spacing-sm (8px)
```

**CSS 示例**：
```css
.comp-result { display: flex; box-sizing: border-box; width: 100%; padding: var(--spacing-xxl) 0; }
.comp-result--vertical { flex-direction: column; align-items: center; text-align: center; }
.comp-result--horizontal { flex-direction: row; align-items: flex-start; }
.comp-result__icon-wrap { display: inline-flex; align-items: center; justify-content: center; border-radius: var(--radius-round); }
.comp-result--vertical .comp-result__icon-wrap { margin-bottom: var(--spacing-xl); }
.comp-result--horizontal .comp-result__icon-wrap { margin-right: var(--spacing-xl); }
.comp-result__title { font-size: 18px; font-weight: 700; color: var(--color-neutral-gray-120); margin: 0 0 var(--spacing-md) 0; line-height: var(--line-height-single); }
.comp-result__description { font-size: 14px; font-weight: 400; color: var(--color-neutral-gray-90); margin: 0 0 var(--spacing-xl) 0; line-height: var(--line-height-multi); }
.comp-result__content-box { width: 100%; max-width: 720px; background-color: var(--color-neutral-gray-10); border-radius: var(--radius-md); padding: var(--spacing-lg); margin-bottom: var(--spacing-xl); text-align: left; }
.comp-result__actions { display: flex; justify-content: center; gap: var(--spacing-sm); }
```

---

## 代码生成指引

当用户要求生成符合中后台组件规范的代码时：

1. **始终引用上述 Design Tokens 变量**，严禁硬编码像素值或颜色值
2. **严格遵循各组件的尺寸矩阵**（高度、内边距、字号、圆角）
3. **完整实现所有交互状态**（Default / Hover / Active / Disabled / Focus / Selected）
4. **遵循全英文 UI 文案标准**（如 `Menu item`、`Go to [X] Page`、`Total ${total} items`）
5. **文本字重严格限制为 400 (Regular) 和 700 (Bold)**，部分组件允许 500 (Medium)
6. **生成完整可用的 CSS 代码**，包含 `:root` 变量定义和组件样式类