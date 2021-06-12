---
layout:     post 

title:       "Hugo Basic"
subtitle:    "Introduce Hugo basic command"
date:        2021-06-04
author: Jasper
published: true
image: "/img/Tech/hugo/hugo_home.png"
tags:        
    - Hugo
categories:  [Tech]
---

# Hugo 介紹
***
Hugo 是一套生成靜態頁面的工具(static site generator)。利用 Markdown 將內容跟樣式外觀完整分開，再利用生成的靜態網頁直接發佈到 server 上。般來說 markdown 語法對應樣式種類會比較少，但是相對的也是幫助在寫作的時候專注在內容而不是樣式上

優點

* 使用Markdown 書寫，且兼容css/html
* 轉換成網頁的速度極快
* 提供模組並且簡單的客製化
* 多元的版型可以使用
* 靜態網頁的免費空間好找

缺點：

* 靜態網頁生成，沒有互動性
* 進階的功能需要高度程式能力
* 模板外的模組，需要自己增建

可參考 [官方文件](https://gohugo.io/getting-started/installing/) 安裝


# Hugo CLI

***

| 功能         | 語法                              |
| ------------ | --------------------------------- |
| 建立新專案   | `hugo new site myblog`            |
| 輸出靜態文件 | `hugo`                            |
| 本地編譯     | `hugo server -D`                  |
| 新增文章     | `hugo new posts/my-first-post.md` |

***