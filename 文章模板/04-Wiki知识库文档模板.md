---
# 04 Wiki 知识库文档模板（复制到 source/wiki/项目ID/ 后使用）
# 适合：围绕稳定主题、可反复查询的指南（不是一次性记录）
# 两个现有项目：
#   个人知识管理      → source/wiki/knowledge-management/（collection.id: knowledge-management）
#   Stellar 建站手册  → source/wiki/site-handbook/（collection.id: site-handbook）
# 文件名 = 目录树键 = 网址末段：/wiki/项目ID/文件名/
title: 【文档标题，例如：收集材料时保留上下文】
description: 【一句话摘要，会显示在 Wiki 列表卡片与分享里】
# 本站 Wiki 文档无需写 date 与 categories；归属由目录位置自动判定
permalink: wiki/【项目ID】/【文件名】/   # ← 例如 wiki/knowledge-management/capture/
---

【第一段：直接回答"读者查这篇指南想解决什么问题"，一两句说清适用范围。】

## 【小节标题（从 ## 开始）】

指南正文以"可以照着做"为标准，多用步骤、清单和边界说明：

- 步骤一：【做什么】
- 步骤二：【做什么】
- 边界：【这个方法不适用于什么情况】

需要并列比较时，用标签页：

{% tabs %}
<!-- tab 【方案/场景 A】 -->
【A 的说明。】
<!-- tab 【方案/场景 B】 -->
【B 的说明。】
{% endtabs %}

需要提醒关键点时，用提示框：

{% note color:cyan 【首词标题】 【提示内容。】 %}

{% box color:green 【容器标题】 %}
【一段更完整的最小示例或模板，box 内可继续写 Markdown。】
{% endbox %}

补充说明可以放进折叠面板，避免占版面：

{% folding color:yellow 【折叠标题】 %}
【只有需要时才展开看的细节。】
{% endfolding %}

## 【结尾小节】

指南结尾给出下一步入口（相对链接），让读者继续往下走：

- 下一篇：[【下一篇标题】](../【下一篇文件名】/)
- 本项目的上一节：[【标题】](../【文件名】/)

---

### 需要同步登记（Wiki 文档的固定三步）

1. **正文文件**：放到 `source/wiki/项目ID/`（上面的 `permalink` 要与此目录一致）。
2. **上架列表**：如果这是一个新项目，先在 `source/_data/wiki.yml` 加一行项目 id；
   已有项目不用动这个文件。
3. **登记目录树**：打开 `source/_data/wiki/项目ID.yml`，在 `navigation.tree` 的分组里加一行
   `- 【文件名】`（只写文件名、不带 .md，也不用带项目路径）。分组可新建，例如：

   ```yaml
   navigation:
     tree:
       开始建站:
         - index
         - content
       写作指南:      # ← 示例：分组名可自定义
         - writing-format
   ```

   未登记到目录树的文档不会出现在左侧导航，读者只能靠猜网址进入。

登记片段可直接从 `05-内容登记片段速查.md` 复制，最后用 `npm run doctor` 验证。
