---
title: 在 Nuxt.js 導入 phosphor-icons
date: 2024-06-07 19:30:36
tags: 
  - Nuxt.js
  - Icons
  - Vue
---

在 Nuxt.js 中導入和使用 @phosphor-icons/vue 的範例

<!--more-->

#### 1. 連結

- [Phosphor Icons](https://phosphoricons.com/?size=24&q=%22%22)
- [phosphor-icons/vue: A flexible icon family for Vue (github.com)](https://github.com/phosphor-icons/vue)

#### 2. 安裝

```bash
npm install @phosphor-icons/vue
```

#### 3. 找喜歡的 Icon
- [Phosphor Icons](https://phosphoricons.com/?size=24&q=%22%22)
也可以在網頁的測試欄進行調整，可以馬上看到效果哦
![找 icon 示意圖](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/nuxt-icon-phosphor%2F1.png?alt=media&token=a8c519d7-f75d-457f-8e6e-c6df2b2207b2)

#### 4. 在專案內使用

導入和使用 Phosphor Icons
```html
<script setup lang="ts">
// 需要的 icon 再引入即可
import {
  PhUserCircle,
  PhHouse
} from '@phosphor-icons/vue'
</script>

<!-- 引入後就可以在頁面上直接使用囉 -->
<template>
  <PhUserCircle :size="24" />
  <PhHouse :size="24" />
</template>
```

##### 可調整的屬性

- `color(string) 圖標顏色`
    可以接受任何 CSS 顏色字符串，包括hex、rgb、rgba、hsl、hsla、命名顏色，或者特殊的 currentColor 變量；
    若無設定則使用預設值 currentColor。
    使用 currentColor，則圖標的填充顏色將與其父元素的文字顏色相同。
    ```html
    <PhBooks color="#FF0000" />
    <PhBooks color="hotpink" />
    ```
    <br />

- `size(string) 圖標高度和寬度`
    可以是一個數字或者一個帶有單位的字符串，單位可以是 px、%、em、rem、pt、cm、mm、in 等；
    若無設定則使用預設值 1em。
    ```html
    <PhBooks :size="24" />
    <PhBooks :size="2em" />
    ```
    <br />

- `weight(string) 圖標的粗細/風格`
    這個屬性可以是 thin、light、regular、bold、fill 或 duotone 。
    ```html
    <PhStar weight="regular" />
    <PhStar weight="fill" />
    ```
    在上述代碼中，第一行將 PhStar 圖標的風格設定為 regular，這將產生一個空心的星形圖標。
    第二行將 PhStar 圖標的風格設定為 fill，這將產生一個實心的星形圖標。
    <br />

- `mirrored(boolean) 水平翻轉圖標`
    如果設定為 true，則圖標將被水平翻轉。在正常圖示方向不合適的 RTL 語言中非常有用。
    ```html
    <PhBooks :mirrored="true" />
    ```
    <br />

- `一次是可以使用多個屬性的哦！`
    我這邊對 `PhBooks` 設定大小 24px、填滿、水平翻轉、藍色。
    ```html
    <PhBooks :size="24" weight="fill" :mirrored="true" color="blue" />
    ```

<br />
<hr />
<br />

<details>
<summary>等等！ 為什麼有的要 : 有的不用 : 呢 ?</summary>

<h4>基本原理</h4>
<p>在 Vue.js 中，當你使用 v-bind 指令（縮寫為 :）時，你告訴 Vue 這個屬性值是動態的，並且應該被解析為 JavaScript 表達式。如果屬性值是固定的字符串，則不需要使用 :。</p>

<h4>字符串常量 vs. JavaScript 表達式</h4>
- 字符串常量：直接使用固定的字符串值，不需要 `:`。
- JavaScript 表達式：使用變量或計算表達式，需要使用 `:`。

<h4>具體說明</h4>
<h5>字符串常量</h5>

```html
    <PhBooks weight="fill" color="blue" />
```
`weight="fill"` 和 `color="blue"` 是固定的字符串常量，不需要 `:`。

<h5>JavaScript 表達式</h5>
```html
    <PhBooks :size="24" :mirrored="true" />
```
`:size="24"` 和 `:mirrored="true"` 是 JavaScript 表達式，需要使用 `:`。
    
<h4>結合示例</h4>
```html
<template>
    <div>
        <PhBooks :size="24" :mirrored="true" weight="fill" color="blue" />
        <PhBooks :size="iconSize" :mirrored="isMirrored" :weight="iconWeight" :color="iconColor" />
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { PhBooks } from '@phosphor-icons/vue';

const iconSize = ref(24);
const isMirrored = ref(true);
const iconWeight = ref('fill');
const iconColor = ref('blue');
</script>
```

<h4>總結</h4>

- 靜態值 -> 不需要 `:`
    ```html
    <PhBooks weight="fill" color="blue" />
    ```

- 動態值 -> 需要 `:`
    ```html
    <PhBooks :size="24" :mirrored="true" />
    ```
    
希望這樣能幫助你更清楚地理解為什麼某些屬性需要使用 `:` 而其他屬性則不需要！

</details>

<br />
<hr />

> 希望這篇文章有幫助到你，謝謝你的觀看，若有想看的系列也歡迎告訴我 😉