# \#21 Merge Two Sorted Lists

### Easy:star:

 Merge two sorted linked lists and return it as a new **sorted** list. The new list should be made by splicing together the nodes of the first two lists.

```text
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
            answer = ListNode(0)
            head = answer
            while True :
                if l1 == None:
                    head.next = l2 
                    break
                elif l2 == None:
                    head.next = l1
                    break
                elif l1.val <= l2.val :
                    head.next = l1 
                    l1 = l1.next
                else: 
                    head.next = l2 
                    l2 = l2.next
                head = head.next
            return answer.next
```

