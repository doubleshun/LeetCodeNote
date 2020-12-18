# \#83 Remove Duplicates from Sorted List

### Easy:star:

 Given a sorted linked list, delete all duplicates such that each element appear only _once_.

```text
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        current = head
        if current == None :
            return head
        else:
            while current.next != None :
                if current.val == current.next.val :
                    current.next = current.next.next
                else:
                    current = current.next
            return head
```

