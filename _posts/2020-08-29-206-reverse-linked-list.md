---
layout: post
title:  206. Reverse Linked List
date:   2020-08-29 21:15:57 -0400
categories: leetcode
---

https://leetcode.com/problems/reverse-linked-list/ 

> Reverse a singly linked list.
>
> **Example:**
>
> ```python
> Input: 1->2->3->4->5->NULL
> Output: 5->4->3->2->1->NULL
> ```



```python
class Solution:
    def reverseList_iter(self, head: ListNode) -> ListNode:
        if not head: return None

        curr = head
        rev = None
        while curr:
            temp = curr.next
            curr.next = rev
            rev = curr
            curr = temp

#         return rev
        return ListNode.printListNode(rev)

    def reverseList_rec(self, head: ListNode) -> ListNode:
        if not head or not head.next: return head
        p = self.reverseList(head.next)
        head.next.next = head
        head.next = None
        return ListNode.printListNode(p)
    
so = Solution()

indata = [1,2,3,4,5,6]
head = ListNode.list2ListNode(indata)

print(so.reverseList_iter(head))
print(so.reverseList_rec(head))
```



2020/08/29:

- 这题好深刻，好难，都好几刷了，还是没刷对！加油！今天要交MDD，不再像往年那样在乎了，安心刷题
- iterate 的方法因该是会了，recursion时抄的好好体会
- 今天blog开张，准备把刷的题都放上来。

