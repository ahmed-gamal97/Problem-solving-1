1) https://leetcode.com/problems/merge-two-sorted-lists

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
            head = tail = ListNode(0)
        
            while(l1 and l2):
                if (l1.val < l2.val):
                    tail.next = l1
                    l1 = l1.next

                elif (l1.val >= l2.val):
                    tail.next = l2
                    l2 = l2.next
                tail = tail.next
                
            tail.next = l1 or l2
            return head.next
```
  complexity: o(n+m) , space: o(1)
  ------------------------------------------------------------------------------

2) https://leetcode.com/problems/reverse-linked-list

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        previous = None
        current = head
        while (current != None):
            next_temp = current.next
            current.next = previous
            previous = current
            current = next_temp
        return previous 
    
```
  complexity: o(n) , space: o(1)
  ------------------------------------------------------------------------------
3) https://leetcode.com/problems/middle-of-the-linked-list
```python
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def middleNode(self, head: ListNode) -> ListNode:
        A = [head]
        while A[-1].next:
            A.append(A[-1].next)
        return A[round(len(A)/2)]
```
  complexity: o(n) , space: o(n)
  ------------------------------------------------------------------------------

```python
class Solution(object):
    def middleNode(self, head):
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        return slow

```
  complexity: o(n) , space: o(1)
  ------------------------------------------------------------------------------
4) https://leetcode.com/problems/delete-node-in-a-linked-list
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def deleteNode(self, node):
        """
        :type node: ListNode
        :rtype: void Do not return anything, modify node in-place instead.
        """
        node.val = node.next.val
        node.next = node.next.next
```
5) https://leetcode.com/problems/remove-duplicates-from-sorted-list
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        curr = head
        while curr and curr.next:
            if curr.next.val == curr.val:
                curr.next = curr.next.next
            else:
                curr = curr.next
        return head
            
```

