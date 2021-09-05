---
title: <Leetcode>Subrectangle Queries
author: Dayoungle
date: 2021-09-06 08:30:00 +0900
categories: [Leetcode,medium]
tags: [Leetcode]
---

## Subrectangle Queries with Java

문제를 처음 봤을 때 테스트에서 인자로 받는 내용이 복잡해서 잘 이해되지 않았다. 자세히 살펴보니 Update()와 getValue()를 호출하는 순서도 다 인자로 주기 위함인데, 굳이 저 내용을 다 설명했어야 했나 싶기도 하다. 설명이 복잡도를 올려서 그렇지 풀이의 난이도는 Easy of Easy 했다.

**[References]**
[Leet code problems](https://leetcode.com/problems/subrectangle-queries)

### 최초의 행렬 구조
```
// The initial rectangle (4x3) looks like:
// 1 2 1
// 4 3 4
// 3 2 1
// 1 1 1
```
### update를 호출하면 인자로 받은 (row1, col1) 부터 (row2, col2) 까지의 행렬 값을 모두 newValue로 교체
```
subrectangleQueries.updateSubrectangle(0, 0, 3, 2, 5);
// After this update the rectangle looks like:
// 5 5 5
// 5 5 5
// 5 5 5
// 5 5 5
```

너무 쉬워서 오히려 내가 놓친게 있는지 고민하게 되는 상황이었고, 테스트 돌려보려고 하는 몇분을 제외하면 로직 짜는데는 1분도 안 걸린 것 같다.

```java

public void updateSubrectangle(int row1, int col1, int row2, int col2, int newValue) {
        for (int i = row1; i <= row2; i++) {
            for (int j = col1; j <= col2; j++) {
                this.rectangle[i][j] = newValue;
                //System.out.println("row:"+i+", col:"+j+",val:"+this.rectangle[i][j]);

            }
            //System.out.println("");
        }

    }
```
