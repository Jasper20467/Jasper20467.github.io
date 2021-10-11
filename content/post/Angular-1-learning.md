---
title:       "Angular Learning - 1"
subtitle:    "NgModule -1 "
description: ""
date:        2020-12-05
author: Jasper
published: true
image:       "/img/Tech/angular/angular-home.jpg"
tags:        ["Angular"]
categories:  ["Tech" ]
---


## Module

- Angular 中Module 為功能模組，用意為邏輯的處理
- 透過NgModule  實現模組化 
    - 通常根模組(Root Module) 會取名為 AppModule  => ```app.module.ts```

- ![](/img/Tech/angular/ngmodule-1.jpg) 

##  Module 檔案結構

- 模組檔案通常可分為三個部分： (**import** / **declarator** / **class**) 
    - Import 資源區：
    ![](/img/Tech/angular/ngmodule-2-import.png) 

    - Decorator 裝飾器： 
    ![](/img/Tech/angular/ngmodule-3-decorator.png.png)

        - 功能為各訴Angular 如何處理接下來的Class 內容。 
        ![](/img/Tech/angular/ngmodule-4-dec-2.png)

        - declarations : 屬於此NgModule的Component/Directive/Pipe 皆要放置於此 
        - Imports: 此NgModule需要用到的，依賴的其他NgModule 放置於此 
    - Class 類別:   
        - 每個檔案都會有一個要export給別人使用的類別 
![](/img/Tech/angular/ngmodule-5-class.png)

    


