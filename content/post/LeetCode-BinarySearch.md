---
title:       "Leet Code Binary Search"
subtitle:    "堆疊 vs 遞迴"
date:        2024-10-23
author: Jasper
published: true
image: "/img/Tech/LeetCode/home.png"
tags:        ["Python", "LeetCode"]
categories:  ["Tech" ]
---

# 遞迴和堆疊的關係

在演算法中，使用堆疊（stack）和使用遞迴（recursion）有著密切的關聯，因為遞迴本質上是使用系統堆疊來管理函數調用。以下是它們之間的差別和關聯：

### 差別
1. **實現方式**：
   - **遞迴**：通過函數自我調用來實現。每次遞迴調用都會在系統堆疊中創建一個新的函數調用框架。
   - **堆疊**：通過顯式地使用數據結構（如列表或棧）來模擬遞迴調用過程。

2. **控制權**：
   - **遞迴**：由系統自動管理函數調用和返回，開發者不需要手動管理堆疊。
   - **堆疊**：開發者需要手動管理堆疊的推入（push）和彈出（pop）操作。

3. **可讀性**：
   - **遞迴**：代碼通常更簡潔和易讀，特別是對於自然遞迴問題（如樹遍歷、分治算法）。
   - **堆疊**：代碼可能更複雜，但更靈活，特別是在需要避免遞迴深度限制的情況下。

### 關聯
1. **等價性**：
   - 遞迴和堆疊在功能上是等價的。任何遞迴算法都可以轉換為使用顯式堆疊的迭代算法，反之亦然。

2. **堆疊模擬遞迴**：
   - 遞迴調用過程中，每次調用都會將當前狀態（如變量值和返回地址）推入系統堆疊。這與顯式使用堆疊來保存狀態並進行迭代處理的過程相同。

3. **性能考量**：
   - 遞迴的性能取決於系統堆疊的深度限制和管理開銷。對於深度較大的遞迴，可能會導致堆疊溢出。
   - 使用顯式堆疊可以避免系統堆疊的深度限制，並且在某些情況下可以更有效地管理內存。

### 示例
以下是使用遞迴和堆疊實現二叉樹前序遍歷的示例：

**遞迴實現**：
```python
def preorder_recursive(node):
    if node:
        print(node.val)
        preorder_recursive(node.left)
        preorder_recursive(node.right)


def preorder_stack(root):
    if not root:
        return 
    stack = [root]
    while stack:
        node = stack.pop()
        print(node.val)
        if node.left:
            stack.append(node.left)
        if node.right:
            stack.append(node.right)

```

### 總結
- **遞迴：** 簡潔、易讀，但受限於系統堆疊深度。
- **堆疊：** 靈活、可控，但代碼較複雜，適合處理深度較大的問題。