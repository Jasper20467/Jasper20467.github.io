---
title:       "Django - 1 Environment Setup"
subtitle:    ""
description: ""
date:        2018-11-30
author: Jasper
published: true
image: "/img/Tech/python-django/django-home.png"
tags:        ["Python", "Django"]
categories:  ["Tech" ]
---


## 安裝Python後，再安裝Django套件 

- 安裝django套件

    ```sh
    pip install django==2.1.3
    ```

![](/img/Tech/python-django/install_django.png) 


## 環境變數設定

- 安裝完成後透過以下cmd確認功能是否正常

    ```sh
    >>> import django
    >>> print(django.get_version())
    2.1
    ```


- 使用Djano-admin創建web初始django專案資料夾 

    ```sh
    django-admin startproject mysite
    ```

![](/img/Tech/python-django/creating-project.png) 

- 若無法正常執行，顯示“command not found: django-admin”，請先設定環境變數。
- 使用Ananconda 安裝的話，加入路徑如下：C:\Program Files (x86)\Microsoft Visual Studio\Shared\Anaconda3_64\Scripts  

## Django專案資料夾結構

![](/img/Tech/python-django/project-struct.png) 
