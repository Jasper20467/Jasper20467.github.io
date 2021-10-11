---
title:       "Dokcer Learning - 1"
subtitle:    "Introduce Docker "
description: "Docker V.S. Virtual Machine"
date:        2021-02-25
author: Jasper
published: true
image:       "/img/Tech/docker/docker-home.jpeg"
tags:        ["Docker"]
categories:  ["Tech" ]
---

## Docker Features

1. Container 之間的獨立性 

2. Docker Hub 使用來儲存images 

3. Images 是唯讀的映象檔，用於建造container 


## Docker V.S. Virtual Machine



 Features     | Docker  | Virtual Machine 
--------------|:-----:|-----:|
OS    | 直接從docker hub 裡pull 作業系統的image  |  需要安裝作業系統  
BOOT    | 不用開機，啟動速度比VM快  |  VM裡面的OS 開機要花一些時間 
RESOURCE  | 底層還是使用OS的Kernal  | 完全隔離系統的硬體資源 
CAPACITY  | 佔用硬碟的容量較小  | 佔用硬碟的容量較大 