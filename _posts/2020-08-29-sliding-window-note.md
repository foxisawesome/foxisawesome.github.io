---
layout: post
title: Sliding Window Note
date: 2020-08-29 22:42 -0400
categories: note
---
    
滑动窗口算法的思路是这样：

1、我们在字符串S中使用双指针中的左右指针技巧，初始化left = right = 0，把索引**左闭右开**区间[left, right)称为一个「窗口」。

2、我们先不断地增加right指针扩大窗口[left, right)，直到窗口中的字符串符合要求（包含了T中的所有字符）。

3、此时，我们停止增加right，转而不断增加left指针缩小窗口[left, right)，直到窗口中的字符串不再符合要求（不包含T中的所有字符了）。同时，每次增加left，我们都要更新一轮结果。

4、重复第 2 和第 3 步，直到right到达字符串S的尽头。

这个思路其实也不难，第 2 步相当于在寻找一个「可行解」，然后第 3 步在优化这个「可行解」，最终找到最优解，也就是最短的覆盖子串。左右指针轮流前进，窗口大小增增减减，窗口不断向右滑动，这就是「滑动窗口」这个名字的来历。

[refrence: wx:labuladong](https://mp.weixin.qq.com/s/ioKXTMZufDECBUwRRp3zaA)


**Code Template:**
```python
def slidingWindow(s: str, t: str) -> str:
    target, window = {}, {} 

    for i in t:
        target[i] = target.get(i,0) + 1

    left, right, valid = 0, 0, 0

    while (right < len(s)):
        # expand window right point to contain all t
        c = s[right]
        # move right index
        right += 1
        # 进行窗口内数据的一系列更新
        ...
        # /*** debug 输出的位置 ***/
        print('s: '+s2[left:right]+' window' + str(window) + ' valid: ' + str(valid))
        
        # see if needs to shrink window 
        while (window shrinking condition):
            d = s[left]
            left += 1
            # 进行窗口内数据的一系列更新
            ...
    return ...
```