---
title:       "Leet Code BFS / DFS"
subtitle:    "BFS vs. DFS in Flood Fill Algorithm"
date:        2024-10-23
author: Jasper
published: true
image: "/img/Tech/LeetCode/home.png"
tags:        ["Python", "LeetCode"]
categories:  ["Tech" ]
---

## BFS vs. DFS in Flood Fill Algorithm

### Breadth-First Search (BFS)
- **Approach:**
  - BFS uses a queue and explores all neighbors at the present depth level before moving on to nodes at the next depth level.
- **Advantages:**
  - Can be more memory-efficient if the tree/graph is very deep but not very wide.
  - Guarantees the shortest path in an unweighted graph.
- **Disadvantages:**
  - Can consume more memory if the graph is very wide.

### Depth-First Search (DFS)
- **Approach:**
  - DFS uses a stack (or recursion) and explores as far as possible along each branch before backtracking.
- **Advantages:**
  - Can be more memory-efficient if the tree/graph is very wide but not very deep.
  - Can be easier to implement using recursion.
- **Disadvantages:**
  - Can consume more memory if the graph is very deep due to the recursion stack.

### Example Implementation of BFS for Flood Fill
```python

class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, color: int) -> List[List[int]]:
        m = len(image)
        n = len(image[0])
        
        if m == 0 or n == 0:
            return image
        
        originalColor = image[sr][sc]
        if originalColor == color:
            return image
        
        queue = [(sr, sc)]
        directions = [(0, 1), (1, 0), (0, -1), (-1, 0)]
        
        while queue:
            x, y = queue.pop(0)
            if image[x][y] == originalColor:
                image[x][y] = color
                for dx, dy in directions:
                    nx, ny = x + dx, y + dy
                    if 0 <= nx < m and 0 <= ny < n and image[nx][ny] == originalColor:
                        queue.append((nx, ny))
        
        return image
```
### Example Implementation of DFS for Flood Fill
```python
class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, color: int) -> List[List[int]]:
        m = len(image)
        n = len(image[0])
        
        if m == 0 or n == 0:
            return image
        
        originalColor = image[sr][sc]
        if originalColor == color:
            return image
        
        def dfs(x, y):
            if image[x][y] == originalColor:
                image[x][y] = color
                for dx, dy in directions:
                    nx, ny = x + dx, y + dy
                    if 0 <= nx < m and 0 <= ny < n:
                        dfs(nx, ny)
        
        directions = [(0, 1), (1, 0), (0, -1), (-1, 0)]
        dfs(sr, sc)
        
        return image

```

