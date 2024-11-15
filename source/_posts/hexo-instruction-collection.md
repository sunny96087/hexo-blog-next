---
title: Hexo 指令合集
date: 2024-05-17 13:00:00
tags: hexo
---
這裡集合了 hexo 常用的指令

<!--more-->

### 安裝 Hexo (全域)

```bash
sudo npm install -g hexo-cli
```

### 檢查版本 (若有顯示版本號代表安裝成功)

```bash
hexo -v
```

### 快速建立新專案

```bash
hexo init <web name>

# 範例：建立一個叫做 2fish-blog 的專案
hexo init 2fish-blog
```

### 執行專案

```bash
hexo server
```

### 新增文章

```bash
hexo new <post name>

# 範例：建立一個叫做 firstPost 的文章
hexo new firstPost
```

### 新增頁面

```bash
hexo new page <page name>

# 範例：建立一個叫做 about 的文章
hexo new page about
```

### 打包生成靜態文件

```bash
hexo generate
```

### 清除快取 <small>( 有時候修改內容後沒有顯示，可以使用此指令清除快取 )</small>

```bash
hexo clean
```

### 部署

```bash
hexo deploy
```

<br />
<hr />
<br />

## 當你今天忘記指令 🤦🏻‍♀️

_可以到專案目錄下的 `package.json` 查看指令_

```bash
  "scripts": {
    "build": "hexo generate",
    "clean": "hexo clean",
    "deploy": "hexo deploy",
    "server": "hexo server"
  }
```
這裡面的指令是預設包裝好的，舉例我們剛剛使用的 `hexo clean`，
你也可以輸入 `npm run clean` 會執行同樣的操作哦！
