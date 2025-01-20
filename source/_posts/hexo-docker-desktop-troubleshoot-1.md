---
title: 誤打誤撞的 Docker Desktop 災情記錄與解決方案
date: 2025-01-19 23:00:00
tags: docker
---
最近想要在 Mac 上安裝 MSSQL，看了朋友推薦的 YouTube 教學影片，第一步就是要安裝 Docker。由於之前已經安裝過，就想說直接用快捷鍵開啟，結果系統竟然告訴我 Docker 已經被丟進垃圾桶了！

抱持著「沒關係，重新安裝就好」的心態，前往官網準備重新下載，沒想到這個決定卻開啟了無止盡的錯誤彈窗轟炸...

<!--more-->

## 🔹 問題調查

![錯誤彈窗](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/hexo-docker-desktop-troubleshoot-1%2F1.png?alt=media&token=6aa2f2c5-6c48-4edc-bc31-a976193ab0cf)

在網路上依照錯誤訊息 『未打開「com.docker.vmnetd」，因為它包含惡意軟體。此動作不會損害你的Mac。』 搜尋相關資料時，
發現這個問題早在 1 月 9 日就已經開始出現。

一開始找到的多是對岸的部落格文章，正當考慮要依照這些文章建議的方法嘗試時，
幸運的發現了國外論壇的相關討論。

<br />
<hr />
<br />

## 🔹 解決方案

解決方案來自於 [Docker Github Issue](https://github.com/docker/for-mac/issues/7527)

### 1. 安裝官方修復版本

首先嘗試安裝官方推薦的修復版本 4.37.2

> 直接從[官方網站](https://docs.docker.com/desktop/release-notes/#4372)下載

![安裝官方推薦的修復版本 4.37.2](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/hexo-docker-desktop-troubleshoot-1%2F2.png?alt=media&token=f63af7b9-df77-43f0-aefd-cde133d7ecb7)

<br />
<hr />
<br />

### 2. 若仍然出現錯誤

如果安裝後持續出現錯誤彈窗，請依照 [Docker 文件](https://docs.docker.com/desktop/cert-revoke-solution/) 建議執行以下步驟：

![Docker 文件](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/hexo-docker-desktop-troubleshoot-1%2F3.png?alt=media&token=3310eab7-3de7-4f4d-b9a5-77252883fa1c)

1. 終止所有無法正常啟動的 Docker 程序

    ```bash
    sudo launchctl bootout system/com.docker.vmnetd 2>/dev/null || true
    sudo launchctl bootout system/com.docker.socket 2>/dev/null || true

    sudo rm /Library/PrivilegedHelperTools/com.docker.vmnetd || true
    sudo rm /Library/PrivilegedHelperTools/com.docker.socket || true

    # (下面這行我沒有使用到) 因為複製貼上到終端機後無法 Enter，我把這行刪掉後，才成功執行 
    ps aux | grep -i docker | awk '{print $2}' | sudo xargs kill -9 2>/dev/null

    ```

2. 確認並永久關閉惡意軟體的彈出視窗
3. (可選) 打開活動監視器，查看是否有 Docker 相關的程序在運行，有的話強制終止

    ![活動監視器](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/hexo-docker-desktop-troubleshoot-1%2F5.png?alt=media&token=5b1ed9ad-f367-42c0-9317-7548f4244457)

4. 重新下載並安裝版本 4.37.2 - [下載連結](https://docs.docker.com/desktop/release-notes/#4372)
5. 嘗試啟動 Docker Desktop

    ![嘗試啟動 Docker Desktop](https://firebasestorage.googleapis.com/v0/b/blog-image-2024.appspot.com/o/hexo-docker-desktop-troubleshoot-1%2F4.png?alt=media&token=ad65d9a4-0c38-4356-97a1-19838420538a)

按照上述步驟操作後，成功解決了這個問題！

<br />
<hr />
<br />

## 🔹 心得總結

這次的經驗讓我學到，遇到軟體問題時：

1. 除了參考部落格文章外，也要多查看官方文件
2. 善用國外論壇資源，因為最新的解決方案可能就在那裡
3. 遇到問題時，保持冷靜並有系統地一步一步排除才是上策