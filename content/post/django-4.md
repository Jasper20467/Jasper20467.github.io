---
title:       "Django - 4 Introduce django urls"
subtitle:    ""
description: ""
date:        2020-12-04
author: Jasper
published: true
image: "/img/Tech/python-django/django-home.png"
tags:        ["Python", "Django"]
categories:  ["Tech" ]
---


## Django URLs 說明

- App在建立完成後，需要建立一個urls.py 

- 並將使urls.py 引入到Web的專案中。 

![](/img/Tech/python-django/app-struct.png) 

- 在此專案範例中，HelloWorld為網頁設定主體，polls為App 

- 將app中的view.py作為一個頁面來使用，必須將urls的路徑map到網頁主體中。 

## App 內容

- 建立 `urls.py`
- Import view，並且指定一個function，命名為name 

![](/img/Tech/python-django/urls-files.png)

- 建立 `view.py`

- 建立一個視圖，並新建一個function，叫做index()，當對這個函數發出request的時候，response一組string 

![](/img/Tech/python-django/view-files.png)

## HelloWorld(網頁主體) 內容

- 修改 `urls.py` 
    - 當Django server 建立起來時，需要指定對應的urls 
    - 此步驟是在紅框處，將polls類別中的urls.py引入，並且在urls路徑上加上polls: `http://127.0.0.1:8000/polls/`
    - 如此即可以執行對應的App request，並傳回response 
    ![](/img/Tech/python-django/add-polls-on-urlfile.png)

## Django.urls  -> Path 方法

![](/img/Tech/python-django/path-method.png)
> https://docs.djangoproject.com/en/2.1/intro/tutorial01/ 