---
title: 我的 AI 知识库搭建
date: 2026-03-25
tags:
  - AI
  - Architecture
---

**我询问了Google如何创建 “AI-Native” 博客，以下是它给我的答案：**

---

这个组合之所以被称为“AI-Native”，是因为 **Obsidian** 负责知识的**深度关联（双向链接）**，而 **Quartz 4.0** 负责将这些关联**结构化地发布**。

以下是实现这一方案的具体步骤：

---

## 第一步：环境准备

你需要安装 **Node.js (v18.14 或更高)** 和 **Git**。

1. **克隆 Quartz 模板：**
    
    在终端执行以下命令，将 Quartz 源码同步到本地：
    
    Bash
    
    ```
    git clone https://github.com/jackyzha0/quartz.git
    cd quartz
    npm install
    ```
    
2. **初始化配置：**
    
    执行 `npx quartz create`。
    
    - 选择 **"Empty"**（如果你想从头开始）。
        
    - 选择 **"Link"**（将你的 Obsidian 库文件夹链接到 Quartz）。
        

---

## 第二步：配置 Obsidian 库 (Vault)

这是你的“知识工厂”。

1. **目录规范：** 在 Obsidian 中，确保你的笔记包含 **YAML Frontmatter**。这是 AI 识别内容的“身份证”。
    
    Markdown
    
    ```
    ---
    title: 我的 AI 知识库搭建
    date: 2026-03-25
    tags:
      - AI
      - Architecture
    ---
    ```
    
2. **利用双向链接：** 写作时大量使用 `[[相关概念]]`。Quartz 会自动将这些链接转化为 HTML 中的跳转，并生成**关系图谱 (Graph View)**，这有助于未来 AI Agent 爬取时理解知识的拓扑结构。
    
3. **附件处理：** 在 Obsidian 设置中，将附件（图片）存放路径设为“当前文件所在文件夹下的子文件夹”，方便 Quartz 索引。
    

---

## 第三步：定制 Quartz (使之更 AI-Friendly)

修改 `quartz.config.ts` 文件，优化其性能和输出：

- **启用全文搜索：** 确保 `PageSearch` 插件开启。Quartz 会生成一个 `static/index.json`，这是未来给 AI 做 **RAG（检索增强生成）** 的现成语料索引。
    
- **优化组件：** 在 `quartz.layout.ts` 中，保留 `Component.Graph()`（关系图）和 `Component.Backlinks()`（反向链接）。
    

---

## 第四步：推送至 GitHub 并自动渲染

Quartz 4.0 自带了 GitHub Actions 的工作流，实现“写完即发布”。

1. **创建 GitHub 仓库：** 在 GitHub 上新建一个私人或公开仓库。
    
2. **关联远程仓：**
    
    Bash
    
    ```
    git remote add origin https://github.com/你的用户名/仓库名.git
    git add .
    git commit -m "Initialize my AI Garden"
    git push -u origin v4
    ```
    
3. **配置 GitHub Pages：**
    
    - 进入仓库 **Settings > Pages**。
        
    - 在 **Build and deployment** 下，将 **Source** 改为 **"GitHub Actions"**。
        
    - Quartz 会自动触发构建，几分钟后你的博客就上线了。
        

---

## 为什么这个组合对你（AI 知识库）最有效？

|**特性**|**对 AI 的价值**|
|---|---|
|**Markdown 原生**|AI 处理纯文本的效率远高于 PDF 或 HTML。|
|**双向链接图谱**|模拟神经元连接，方便 LLM 递归检索相关上下文。|
|**`index.json` 输出**|不需要复杂的爬虫，AI 脚本可以直接读取这个文件获取全站目录。|
|**Git 版本管理**|AI 可以通过 Commit 历史追踪你知识进化的过程。|

