---
name: b2b-component-specs
description: 依据邓松培的中后台组件规范设计或实现中后台界面，查询全局 Design Tokens、30 类组件的尺寸和状态矩阵、样式规则及 CSS 示例。适用于明确采用该规范的业务系统和组件交付，不用于给无关项目强制更换设计系统。
---

# 中后台组件规范

将全局 Tokens 与组件尺寸、状态规则应用到设计或 HTML/CSS 实现中。先尊重当前任务的组件范围、产品品牌与用户指定语言；本技能本身不授权修改其他项目或发布网站。

## 按任务读取

- 需要基础颜色、字体、圆角、间距、阴影或 CSS 变量时，读取 [全局 Design Tokens](references/design-tokens.md)。
- 需要某个组件时，在 [30 类组件规范](references/components.md) 中查找对应章节，仅加载目标组件及其直接关联规则。
- 首次接入、发现缺失变量或规则冲突时，读取 [接入核对](references/integration-notes.md)。

## 应用流程

1. 明确目标组件、业务场景和尺寸等级。修改现有界面时识别已有变量映射，不把源规范的类名强行覆盖进现有组件库。
2. 先读取组件尺寸矩阵，再匹配语义色、文本层级、边框、圆角、间距及阴影；优先引用原文 Tokens。
3. 使用 `Arial, "Microsoft YaHei", sans-serif`。常规正文 14 px，辅助说明 12 px；字重通常为 400 / 700。单行行高 1.35，多行行高 1.60；组件有明确特例时按对应条款执行。
4. 保持组件的 Default、Hover、Active、Disabled、Focus、Selected 等适用状态完整。不是每个组件都具有全部状态，按实际组件规范选择。
5. 将重复尺寸集中为变量，声明值遵守尺寸矩阵；先补足已记录的变量缺口，再引用 CSS 示例。不要直接复制未定义变量或改用猜测值。
6. 新增 UI 的默认文案遵循源规范的英文约定；用户明确指定语言或正在维护既有中文页面时，以用户要求和现有内容为准。
7. 交付时简要说明使用的尺寸等级、Tokens、状态，以及尚未解决的规范缺口。针对实际组件检查焦点、禁用行为、长文本和布局，不扩展为无关功能。

## 组件索引

| 类别 | 可查组件 |
| --- | --- |
| 操作与导航 | Button / Dropdown Button、Pagination、Tabs、Navigation Menu、Dropdown、Anchor、Steps |
| 数据录入 | Input、Form、Upload、Date/Time Picker、Select、Radio、Checkbox、TreeSelect、Search、Switch、Transfer |
| 信息展示 | Table、Description、Tag、Badge、Tooltip、Popover |
| 状态与反馈 | Loading、Dialog、Progress、Message/Toast、Alert、Result |

## 示例请求

- “使用这套规范实现 32 px 的中尺寸主按钮，包含悬停、按下和禁用态。”
- “根据规范检查客户查询表单中的输入框高度、间距和焦点颜色。”
- “为 Modelbank 业务页面选择表格、分页与筛选组件，说明使用的 Tokens。”

## 来源与适用范围

来源为 Figma「项目内容」的 `101:84` 文本节点。详见 [接入核对](references/integration-notes.md) 中的源链接、读取日期、变量缺口及冲突说明。参考文档保留源规范详细内容，不把未验证示例宣称为已经生产验收的代码。
