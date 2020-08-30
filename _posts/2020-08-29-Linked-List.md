---
layout: post
title:  “Linked List Notes (First Blog)"
date:   2020-08-29 19:40:57 -0400
categories: leetcode
---

It takes a while for me to get how exactly Linked List works. I used following utility functions to keep my leetcode solutions and run codes locally.

Note:

1. say `head = ListNode(0)`, then `head = head.next` is to iterate to next node on the Linked List. 
2. use `head.next = a` to point to next node. 

```python
# My liked list utility functions: 
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
        
    def list2ListNode(list):
        head = LinkedList = ListNode(0)
        for i in range(len(list)):
            LinkedList.next = ListNode(list[i])
            LinkedList = LinkedList.next
        return head.next
    
    def printListNode(p):
        head = ListNode(0)
        head.next = p
        out = []
        while p:
            out.append(p.val)
            p = p.next
        return out

# e.g.: 
indata = [1,2,3,4,5,6]
head = ListNode.list2ListNode(indata)
ListNode.printListNode(head)
```



- 开始刷Leetcode 好几个月了，今天开始学很多人用blog 记录下自己的notes，也激励自己好好刷题！
- 又是一年最忙季，虽然今天组里人都在线上加班，但我很平静的在刷题。

