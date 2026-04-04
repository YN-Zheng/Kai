---
type: MOC
status: 🌱 孵化中
created: 2026-04-04
tags: #MOC #ContextMap
---
> [!abstract] 核心论点/导言
> 没什么好说的，用代入的方式（一人公司）学习投资

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