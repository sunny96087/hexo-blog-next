---
title: Hexo 進階 - part 1
date: 2024-05-17 14:00:00
tags: hexo
---
這裡包含更換網站圖示、改完的樣式被吃掉怎麼辦、文章摘要下方顯示"查看更多"按鈕

<!--more-->

## 🔹 更換 Landscape 主題的網站圖示

#### 1. 先找一張圖示
可以到 [flaticon](https://www.flaticon.com/) 下載免費圖示

#### 2. 把圖示放進專案裡
我這邊圖示取做 favicon.png，放在以下路徑：
`themes/landscape/source/css/images`

#### 3. 修改 `_config.yml`
到 `themes/landscape/_config.yml` 修改 favicon 路徑：
```yaml
# Favicon path -> 如果照著我上面放的話會跟範例路徑相同
favicon: /css/images/favicon.png
```

<br />
<hr />
<br />

## 🔹 好不容易改完的樣式被吃掉

#### 解決方案
若你是使用 `style.css` 修改樣式，那就把舊的樣式檔案 `style.styl` 刪掉，路徑如下：
`themes/landscape/source/css`

#### 清除快取並重新生成靜態文件
```bash
hexo clean
hexo generate
```
我這樣執行後樣式就會吃到我的 `style.css` 文件了

<br />
<hr />
<br />

## 🔹 在文章摘要下方顯示 "Read More" 連結

#### 設定 `_config.yml`
在主題裡面的 `_config.yml` 文件中，設定 `excerpt_link` 的值來控制是否在文章摘要下方顯示 "Read More" 連結。

```yaml
# "Read More" link at the bottom of excerpted articles. `false` to hide the link.
excerpt_link: "Read More"

# 如果您希望將 "Read More" 更改為其他文字，例如 "觀看更多"，可以這樣設置：
excerpt_link: "觀看更多"
```

---

#### 設定完後，在文章內需要這樣使用

在 Hexo 中，您可以使用 `<!-- more -->` 分隔符來定義哪些內容要在列表顯示或隱藏。
```markdown
---
title: 我的文章標題
---

這是摘要段落，會顯示在文章列表。

<!-- more -->

這邊開始是我只想在文章內頁顯示的內容，列表不會出現！
```

---

### 自訂按鈕樣式 - 修改 CSS
在 `themes/landscape/source/css/style.css` 中自訂樣式：
```css
/* 可以開啟 f12 查看按鈕屬於哪個 class 控制 */
/* 按鈕預設樣式 */
.article-more-link a {
  display: inline-block;
  line-height: 1em;
  padding: 6px 15px;
  border-radius: 15px;
  background: #eee;
  color: #999;
  text-shadow: 0 1px #fff;
  text-decoration: none;
}

/* 按鈕預設 hover 樣式 */
.article-more-link a:hover {
  background: #258fb8;
  color: #fff;
  text-decoration: none;
  text-shadow: 0 1px #1e7293;
}
```