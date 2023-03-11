---
title:       "C# Unit Testing"
subtitle:    "C# Moq 教學"
description: ""
date:        2023-03-11
author: Jasper
published: true
image: "/img/Tech/csharp-unittest/home.png"
tags:  ["CSharp", "Moq"]
categories:  [Tech]
---

Moq 是一個 C# 的單元測試框架，它可以讓你輕鬆地創建和管理模擬對象。本教學將介紹如何使用 Moq 來進行單元測試。

## **安裝 Moq**

在開始之前，你需要先安裝 Moq。你可以通過 NuGet 包管理器在 Visual Studio 中安裝它，也可以在命令提示符中使用以下命令：

```csharp
Install-Package Moq
```
安裝完成後，你就可以開始使用 Moq 進行單元測試。

## **創建模擬對象**

在 Moq 中，你可以使用 Mock 類創建模擬對象。以下是一個創建模擬對象的示例：

```csharp
// 創建模擬對象
var mock = new Mock<IFoo>();

// 設置模擬行為
mock.Setup(foo => foo.DoSomething("ping")).Returns(true);
```
在上面的代碼中，我們創建了一個 IFoo 的模擬對象，並設置了當調用 DoSomething 方法時，傳遞 "ping" 參數時返回 true。

## **驗證方法調用**

Moq 還允許你驗證模擬對象上的方法是否被調用。以下是一個驗證方法是否被調用的示例：

```csharp
// 創建模擬對象
var mock = new Mock<IFoo>();

// 調用方法
mock.Object.DoSomething("ping");

// 驗證方法是否被調用
mock.Verify(foo => foo.DoSomething("ping"), Times.Once());
```

在上面的代碼中，我們創建了一個 IFoo 的模擬對象，調用了它的 DoSomething 方法並通過 Verify 方法驗證了它是否被調用了一次。

## **模擬異常**

Moq 還允許你模擬方法拋出異常的情況。以下是一個模擬方法拋出異常的示例：

```csharp
// 創建模擬對象
var mock = new Mock<IFoo>();

// 設置模擬行為
mock.Setup(foo => foo.DoSomething("invalid")).Throws<ArgumentException>();

// 呼叫方法並期望拋出異常
Assert.Throws<ArgumentException>(() => mock.Object.DoSomething("invalid"));
```

在上面的代碼中，我們創建了一個 IFoo 的模擬對象，設置了當傳遞 "invalid" 參數時，拋出 `ArgumentException異常。然後，我們使用 Assert.Throws 方法來測試當傳遞 "invalid" 參數時是否會拋出 ArgumentException。


## **模擬屬性**

在 Moq 中，你可以使用 Setup 方法來設置模擬屬性的值。以下是一個模擬屬性的示例：

```csharp
// 創建模擬對象
var mock = new Mock<IFoo>();

// 設置模擬屬性
mock.Setup(foo => foo.Value).Returns(10);

// 獲取模擬屬性的值
int value = mock.Object.Value;

// 驗證模擬屬性的值
Assert.AreEqual(10, value);
```

在上面的代碼中，我們創建了一個 IFoo 的模擬對象，設置了它的 Value 屬性的返回值為 10，然後我們獲取了 Value 屬性的值並驗證了它是否等於 10。

## **模擬事件**

在 Moq 中，你可以使用 event 關鍵字來創建模擬事件。以下是一個創建模擬事件的示例：


```csharp
// 創建模擬對象
var mock = new Mock<IFoo>();

// 設置模擬事件
mock.Setup(foo => foo.ValueChanged += null).Verifiable();

// 觸發模擬事件
mock.Object.ValueChanged += (sender, args) => { };

// 驗證模擬事件
mock.Verify(foo => foo.ValueChanged += null, Times.Once());
```

在上面的代碼中，我們創建了一個 IFoo 的模擬對象，設置了當 ValueChanged 事件訂閱時，會進行驗證。然後，我們觸發了 ValueChanged 事件，最後通過 Verify 方法驗證了 ValueChanged 事件是否訂閱了一次。

## **總結**

本教學介紹了 Moq 單元測試框架的基礎知識，包括創建模擬對象、驗證方法調用、模擬異常、模擬屬性和模擬事件等。使用 Moq 可以大大簡化單元測試的開發工作，使開發者能夠更快地構建高質量的代碼。
