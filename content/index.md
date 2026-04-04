---
title: 欢迎
---
# 设计

```
📁 
 ├── 📁 00_闪念 (Input Buffer / 消息队列)
 │    ├── 📄 2026-04-01.md
 │    └── 📄 2026-04-04.md
 │
 ├── 📁 10_MOC_地图 (API Gateway / 路由分发)
 │    ├── 📄 🗺️ AI 时代认知重塑 MOC.md
 │    └── 📄 🗺️ 思维模式 MOC.md
 │
 ├── 📁 20_原子笔记 (Microservices / 核心知识库)
 │    ├── 📄 系统的生命力源于设计的简洁性.md
 │    ├── 📄 终局思维与技术解决路径的挥发性.md
 │    └── 📄 手动复制型笔记在 AI 时代失去意义.md
 │
 ├── 📁 30_当前项目 (Active Processes / 正在执行的工程)
 │    ├── 📁 MySoul小程序开发
 │    └── 📁 Kafka_TLS改造与源码研读
 │
 ├── 📁 40_博客输出 (Build & Deploy / 发布产物)
 │    ├── 📄 草稿：为什么 AI 时代提问比记录更重要.md
 │    └── 📄 已发布：...
 │
 └── 📁 50_外部资源 (Dependencies / 静态依赖)
      ├── 📁 Aswath_Damodaran_估值课程笔记
      ├── 📁 商业英语沟通积累
      └── 📁 模板库 (Templates)
```


# 闪念
```dataview
TASK
FROM "闪念"
WHERE !completed 
GROUP BY file.link
SORT file.name desc
```