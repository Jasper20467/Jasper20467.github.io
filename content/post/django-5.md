---
title:       "Django - 5 Migrations"
subtitle:    ""
description: ""
date:        2020-12-05
author: Jasper
published: true
image: "/img/Tech/python-django/django-home.png"
tags:        ["Python", "Django"]
categories:  ["Tech" ]
---

## Models 的概念

- 建立一個可重複性使用，且明確的後端資料的存取/處理行為 
- 實現DRY(Don’t repeat yourself) 

## 在APP中建立一個新的Modle

![](/img/Tech/python-django/create-models.png) 

## 修改setting.py

- 在網頁設定的資料夾中，修改setting.py設定，加入app的相關模組，polls.apps.PollsConfig，使django知道要載入polls app的模組 

![](/img/Tech/python-django/adj-app-files.png)

![](/img/Tech/python-django/setting-files-official.png)

## 載入並複寫models的設定 

![](/img/Tech/python-django/migrations.png)