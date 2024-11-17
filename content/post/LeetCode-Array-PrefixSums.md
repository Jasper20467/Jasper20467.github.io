---
title:       "Leet Code DFS"
subtitle:    "Q724. Find Pivot Index"
description: "Prefix Sum"
date:        2024-10-23
author: Jasper
published: true
image: "/img/Tech/LeetCode/home.png"
tags:        ["Python", "LeetCode"]
categories:  ["Tech" ]
---

## Tips:

* Prefix sum 又可以稱為 cumulative sum 或是 inclusive scan，核心的概念其實蠻直覺簡單，就是將陣列中每個元素的位置上，儲存該位置之前所有元素、或是特定條件下的總和。

    ```csharp
    const arr = [2, 4, 6, 8, 10];

    // prefix_sum[i] 表示 arr[0] 到 arr[i] 的總和
    const prefixSum = [2, 6, 12, 20, 30]; 
    ```

* 當我們遇到想要計算 arr[1] 到 arr[3] 的總和，我們只需使用我們計算好的前綴和陣列 prefixSum ，使用 prefixSum[3] — prefixSum[0] 就可以拿到 arr 1~3 的總和了，而不需要去使用迴圈再重新計算。

    ```csharp
    const result = prefixSum[3] - prefixSum[0]; // 20 - 2 = 18
    ```

* 建立 prefixSum 的 function
    ```javascript
    function generatePrefixSum(arr) {
        let prefixSum = new Array(arr.length);
        prefixSum[0] = arr[0];
        
        for (let i = 1; i < arr.length; i++) {
            prefixSum[i] = prefixSum[i - 1] + arr[i];
        }

        return prefixSum;
    }
    ```


## Problem:
[724. Find Pivot Index](https://leetcode.com/problems/find-pivot-index/description/)

```python
class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        if(len(nums) == 1 ):
            return 0        
        prefix = {}
        prefix[0] = 0

        for i in range(1,len(nums)):
            prefix[i] = prefix[i-1] + nums[i-1]
        
        total = sum(nums)

        for i in range(0 ,len(nums)):
            right = total - prefix[i] - nums[i]
            if(prefix[i] == right):
                return i        
        return -1

```


## Reference: 


https://medium.com/%E6%8A%80%E8%A1%93%E7%AD%86%E8%A8%98/%E6%BC%94%E7%AE%97%E6%B3%95%E7%AD%86%E8%A8%98%E7%B3%BB%E5%88%97-prefix-sum-ed325ffb2906
