---
title:       "Django - 2 Run Server"
subtitle:    ""
description: ""
date:        2018-11-30
author: Jasper
published: true
image: "/img/Tech/python-django/django-home.png"
tags:        ["Python", "Django"]
categories:  ["Tech" ]
---

## 發布網頁
CMD將路徑指向Django project 的根資料夾，執行 py manage.py runserver 

```sh
py manage.py runserver
```

預設發布路徑為 http://127.0.0.1:8000/

- Python可透過Django套件，開發一個輕量級的web frameworks，在開發模式不需考慮Server的設定，例如 IIS / Apache 

- 預設PORT是8000，可透過CMD 修改要開放的PORT為何

![](/img/Tech/python-django/port-change.png) 

## 發布為多人可共同執行的URL 
- 通過指定一個ip位址，告訴server可以接受非本機電腦的訪問，對於有多人共同開發的需求來說特別有用。
`0.0.0.0` 這個ip位址，告訴server去監聽任意的網路接口

    ```sh
    python manage.py runserver 0.0.0.0:8000
    ```
- 完成這個設定之後，區域網路中的其他電腦就可以透過本機的ip訪問了，例如：`http://192.168.1.103:8000`

## APP V.S. Project 應用程式和專案的差別

- app一個功能模組，projecct為一個具有多功能的整合系統。一個project可以有多個App，一個App可以被多個Project 使用 
![](/img/Tech/python-django/app-vs-project.png) 


