---
title: github 自定義個人頁面 ✨
date: 2024-05-18 20:33:45
tags: github
---

快跟我一起來自訂義獨一無二的個人 github 頁面吧！

<!--more-->

#### 1. 先打開 github 首頁

#### 2. 建立一個新專案

專案名稱要跟使用者名稱相同，正確的話會發現跳出特殊提示框！
這邊記得 ✅ `Add a README file`，等等要用來輸入自訂義內容。
![建立專案配置](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/github-personal-page%2F1.png?alt=media&token=1299f9cc-ba05-4b62-a5d9-e15234e37505)

#### 3. 專案建立成功畫面

![專案建立成功畫面，會包含一個 README.md 檔案](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/github-personal-page%2F2.png?alt=media&token=db009008-c82b-4715-9190-09518ad12301)

#### 4. 點擊右上角的 🖊️ 編輯 `README.md` 檔案，自訂義專屬的個人介紹吧！

以下提供我的範例，跟我使用的 Markdown 語法說明

- `## h2`
    ## 👋 Hi there, I'm 2fish
    ```
    ## 👋 Hi there, I'm 2fish
    ```
    <br />

- `#### h4`
    #### 🌱 Junior Full-Stack Web Developer
    ```
    #### 🌱 Junior Full-Stack Web Developer
    ```
    <br />

- `[Email](mailto:yourEmail@gmail.com) [放置顯示文字](幫前面的文字加上連結)`
    <p>點擊這個連結將會打開電子郵件客戶端，並將收件人的地址設置為 yourEmail@gmail.com</p>
    <p>加上 mailto: 是用來打開電子郵件客戶端的，若是一般的超連結則不需要添加哦</p>

    📮 [Email](mailto:yourEmail@gmail.com)
    ```
    📮 [Email](mailto:yourEmail@gmail.com)
    ```
    <br />

- `- ul 無序清單`
    <p>可以在每個項目前添加兩個空格來創建嵌套的無序清單</p>

    - skill
        - CSS, SCSS
        - JavaScript

    ```
    - skill
        - CSS, SCSS
        - JavaScript
    ```
    <br />

- `table 表格`
    <p>使用表格來整齊呈現資料，詳細範例可以參考下方完整程式碼</p>

    | Project | Description | Links |
    |---------|-------------|-------|
    |   #1    |   描述內容   |  連結  |

    ```
    | Project | Description | Links |
    |---------|-------------|-------|
    |   #1    |   描述內容   |  連結  |
    ```
    <br />

- `![]() 連結嵌入圖片`
    <p>使用方法跟上面超連結相似，[] 放置圖片說明文字，() 放置圖片連結，最前面記得加一個 ! 哦</p>

    ![軌道漫遊列車之旅](https://firebasestorage.googleapis.com/v0/b/simpleportfolio-64b60.appspot.com/o/img%2Fproject-pic-1.png?alt=media&token=388b6fc4-a863-4d12-9e55-f81de4e8c489)

    ```
    ![軌道漫遊列車之旅](https://firebasestorage.googleapis.com/v0/b/simpleportfolio-64b60.appspot.com/o/img%2Fproject-pic-1.png?alt=media&token=388b6fc4-a863-4d12-9e55-f81de4e8c489)
    ```
    <br />

#### 5. 編輯完成後記得點擊右上角的 Commit changes (按兩次就可以成功更新囉)
更新後回首頁就可以直接看到上方多了剛剛新增的內容

![首頁示意圖](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/github-personal-page%2F4.png?alt=media&token=d361e29a-4c15-48a9-a3fd-e4c36cc8d849)

<br />
<hr />
<br />

<details>
<summary>點擊這裡查看完整範例程式碼</summary>
```
## 👋 Hi there, I'm 2fish

#### 🌱 Junior Full-Stack Web Developer
#### 📮 You can reach me at [Email](mailto:yourEmail@gmail.com)

### 💻 Skills

#### Front-End Development
- HTML
- CSS, SCSS
- JavaScript

#### Back-End Development
- Node.js
- MySQL

### 🗂 Portfolio

| Project | Description | Links |
|---------|-------------|-------|
| ![軌道漫遊列車之旅](https://firebasestorage.googleapis.com/v0/b/simpleportfolio-64b60.appspot.com/o/img%2Fproject-pic-1.png?alt=media&token=388b6fc4-a863-4d12-9e55-f81de4e8c489) | **軌道漫遊列車之旅 (Railway Roaming Train Tour)**<br>這是一個團隊合作開發的網站項目，旨在提供使用者一個互動式的平台，探索和計劃他們的小火車旅行。在這個項目中，我參與了從概念發想到最終產品的全過程。我負責網站的介面設計和前後端開發，使用 Vue.js 和 SCSS 來創建響應式的用戶界面，並透過 JavaScript 增強互動性。後端方面，我使用 PHP 和 MySQL 進行資料庫的規劃和建置，並利用 Ajax 和 Axios 技術實現前後端的資料串接。這個項目不僅鍛鍊了我的全端開發能力，也讓我學習到團隊合作如何溝通及解決問題。 | [GitHub](https://github.com/vicky5645/chd102-g1/tree/dev) \| [Demo](https://tibamef2e.com/chd102/g1/) |
| ![Simple Portfolio](https://firebasestorage.googleapis.com/v0/b/simpleportfolio-64b60.appspot.com/o/img%2F%E4%BD%99%E8%AA%BC%E5%A7%8D%20Sunny%20-%20%E4%BD%9C%E5%93%81%E9%9B%86%20Portfolio.png?alt=media&token=cf0a0add-8f85-4d1d-8c78-cca31301972a) | **個人作品集網站 (Portfolio)**<br>我的個人作品集網站，使用 vue3 + composition API + vite 進行開發，網頁展示了我的經歷、專案和技能。 | [GitHub](https://github.com/sunny96087/simple_portfolio) \| [Demo](https://simpleportfolio-64b60.web.app/portfolio) |
```

<br />
<hr />
<br />

> 範例 demo

## 👋 Hi there, I'm 2fish

#### 🌱 Junior Full-Stack Web Developer
#### 📮 You can reach me at [Email](mailto:yourEmail@gmail.com)

### 💻 Skills

#### Front-End Development
- HTML
- CSS, SCSS
- JavaScript

#### Back-End Development
- Node.js
- MySQL

### 🗂 Portfolio

| Project | Description | Links |
|---------|-------------|-------|
| ![軌道漫遊列車之旅](https://firebasestorage.googleapis.com/v0/b/simpleportfolio-64b60.appspot.com/o/img%2Fproject-pic-1.png?alt=media&token=388b6fc4-a863-4d12-9e55-f81de4e8c489) | **軌道漫遊列車之旅 (Railway Roaming Train Tour)**<br>這是一個團隊合作開發的網站項目，旨在提供使用者一個互動式的平台，探索和計劃他們的小火車旅行。在這個項目中，我參與了從概念發想到最終產品的全過程。我負責網站的介面設計和前後端開發，使用 Vue.js 和 SCSS 來創建響應式的用戶界面，並透過 JavaScript 增強互動性。後端方面，我使用 PHP 和 MySQL 進行資料庫的規劃和建置，並利用 Ajax 和 Axios 技術實現前後端的資料串接。這個項目不僅鍛鍊了我的全端開發能力，也讓我學習到團隊合作如何溝通及解決問題。 | [GitHub](https://github.com/vicky5645/chd102-g1/tree/dev) \| [Demo](https://tibamef2e.com/chd102/g1/) |
| ![Simple Portfolio](https://firebasestorage.googleapis.com/v0/b/simpleportfolio-64b60.appspot.com/o/img%2F%E4%BD%99%E8%AA%BC%E5%A7%8D%20Sunny%20-%20%E4%BD%9C%E5%93%81%E9%9B%86%20Portfolio.png?alt=media&token=cf0a0add-8f85-4d1d-8c78-cca31301972a) | **個人作品集網站 (Portfolio)**<br>我的個人作品集網站，使用 vue3 + composition API + vite 進行開發，網頁展示了我的經歷、專案和技能。 | [GitHub](https://github.com/sunny96087/simple_portfolio) \| [Demo](https://simpleportfolio-64b60.web.app/portfolio) |

> 也可以直接到我 [github](https://github.com/sunny96087) 看效果哦
</details>

<br />
<hr />
<br />

參考文章 > [如何建立獨一無二的 GitHub Profile！](https://medium.com/starbugs/%E5%A6%82%E4%BD%95%E5%BB%BA%E7%AB%8B%E7%8D%A8%E4%B8%80%E7%84%A1%E4%BA%8C%E7%9A%84-github-profile-%E8%88%87%E4%B8%89%E5%80%8B%E5%BE%88%E9%85%B7%E7%9A%84%E8%A8%AD%E8%A8%88%E5%8F%8A%E6%87%89%E7%94%A8-ef1cbb4b42c1)

<br />
<hr />
<br />

> 希望這篇文章有幫助到你，謝謝你的觀看，若有想看的系列也歡迎告訴我 😉