---
title:       "Django - 3 Create initial project"
subtitle:    ""
description: ""
date:        2020-12-03
author: Jasper
published: true
image: "/img/Tech/python-django/django-home.png"
tags:        ["Python", "Django"]
categories:  ["Tech" ]
---


## 初始專案建立

- 透過Django -1 設定 建立一個Django專案資料夾 

## 建立 app

- 在manage.py 同資料夾層別下執行`py manage.py startapp polls` ，此條指令可建立一個APP，作為一個模組程式，可以重複使用 

    ```sh
    py manage.py startapp polls
    ```
- ![](/img/Tech/python-django/create-app.png) 

## 建立 view

- 編輯polls/views.py ，建立一個基本的視圖(顯示網頁的內容)

- ![](/img/Tech/python-django/create-view.png)


## 編輯 router

- 編輯urls路徑，並將其引用到網頁Config的引用參考

- ![](/img/Tech/python-django/modify-url-config.png)

> 除了admin.site.urls 其餘的urls都是加入上述的include中

## 建立網頁

- 執行`py manage.py runserver`可建立網頁

```sh
py manage.py runserver
```

- ![](/img/Tech/python-django/run-server.png)


