---
type: MOC
status: 🌱 孵化中
created: 2026-04-04
tags:
  - "#AI"
  - 认知
---
> [!abstract] 核心论点/导言
> AI正在改变稀缺的定义。工业革命让物质极大丰富，AI 则正在让数字资产极大丰富，让当代白领赖以为生的技能迅速贬值。面向未来，我们必须重塑认知，在里面打上 AI 的思想钢印，借助 AI 寻找下一个可持续增长的资产，创造新的价值。

---

# 📂 自动索引 (Dataview)
*下方将自动列出所有关联了本页面的闪念或笔记，方便你“打捞”素材*
### 闪念
```dataview
TASK
FROM "闪念"
WHERE contains(text, this.file.name)
AND !completed
GROUP BY file.link
```

### 笔记
```dataview
TABLE status AS "进度", created AS "创建日期"
FROM [[#]] AND -"闪念"
WHERE type != "MOC"
SORT file.ctime DESC
```

