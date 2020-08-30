---
layout: post
title: 82 Remove dups from sorted list
date: 2020-08-29 21:32 -0400
categories: leetcode
---

https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/



```python
class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        import collections
        
        if not head: return
        root = ListNode(0)
        root.next = head
        stat = []
        while head:
            stat.append(head.val)
            head = head.next
        
        counter = collections.Counter(stat)
        
        head = root
        
        while head and head.next:
            if counter[head.next.val] != 1:
                head.next = head.next.next
            
            else:
                head = head.next
                
#         return root.next
        return ListNode.printListNode(root.next)    

so = Solution()

indata = [1,1,2,3,3,3,4,4,5,6]
head = ListNode.list2ListNode(indata)

so.deleteDuplicates(head)
```

2020-08-29:

- 感觉还有更好的解法，二刷再说吧