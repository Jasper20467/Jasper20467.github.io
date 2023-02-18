---
title:       "Dokcer Fit AWS EC2"
subtitle:    "Deploy the Web API on AWS EC2"
description: "Build the Flask Web API on AWS EC2 via docker image"
date:        2021-02-25
author: Jasper
published: true
image:       "/img/Tech/docker/docker-home.jpeg"
tags:        ["Docker","AWS"]
categories:  ["Tech" ]
---

##  建立Python Flask API 

Flask 是一個輕量化的Python 後端API套件，請參考一下Demo code 建立Python API。

```python
from flask import Flask,render_template

app = Flask('__name__')


@app.route('/')
def home():
    return render_template('home.html')

@app.route('/endpoint')
def endpoint():
    return "This is an end point. You can call send or receive requests by calling this end point."

@app.route('/linker')
def linker():
    return render_template('link.html')

if __name__ == "__main__":
    app.run(host="0.0.0.0",port=5000)
    #app.run(debug=True) #can alter host and port number here. Right now the default host is localhost and port is 5000
```
確認本機端可正常連線成功
![](/img/Tech/docker/flask_build.png) 


建立Python 套件 安裝清單 （requirements.txt)
```txt
Click==8.0.4
Flask==2.0.3
itsdangerous==2.0.1
Jinja2==3.0.3
Werkzeug==2.0.3
```

## 建立Docker Image

打包Python Flask API 為Docker Image，請參考如下Dockerfile

```Dockerfile
// 基本映像檔為Python 3.9
FROM python:3.9-buster
// 工作目錄
WORKDIR /app
// 將Python Flask 檔案覆至於/app目錄下
COPY . /app
// 升級環境套件
RUN apt-get update
// 透過requirements.txt安裝需要的Python 套件
RUN pip install -r requirements.txt
// 執行main.py
CMD python3 main.py
```

在共同目錄下，執行Docker Build 指令
```sh
docker build -t flask_test .
```
![](/img/Tech/docker/docker_build.png) 


確認image 打包完成
![](/img/Tech/docker/docker_image_list.png) 


在本機端透過flask_test image建立Docker Container
```sh
docker run -p 5000:5000 -d flask_test
```
確認服務執行成功
![](/img/Tech/docker/flask_server.png) 

將Docker Image 上傳到個人的DockerHub上，透過VS Code執行
![](/img/Tech/docker/DockerHub.png) 

## 建立AWS EC2

在AWS EC2上建立Linux物件實體，透過AWS Ec2 cloudshell 或是SSH 連線進Ec2內部，在AWS上安裝Docker Engine  [(link)](https://docs.aws.amazon.com/zh_tw/AmazonECS/latest/developerguide/create-container-image.html)

## Docker container run on AWS EC2
從Docker Hub拉下image到AWS EC2 內。
![](/img/Tech/docker/ec2_dockerHub.png) 

需要由外部port: 80 轉到內部port: 5000， 因為EC2 的SG是開在http:80上。
![](/img/Tech/docker/ec2_sg.png) 

在EC2上建立Docker Container，指令如下：
```sh
docker run -p 80:5000 -d bb9871bda67e
```
![](/img/Tech/docker/docker_run_ec2.png) 

確認Python Flask 以成功佈署於EC2，並可透過Piblic IPV4 address 連線，如下：
![](/img/Tech/docker/ec2_ipv4.png) 

開啟網頁確認可透過外部正常連線
![](/img/Tech/docker/success.png) 

