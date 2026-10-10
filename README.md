# Reverse-Linked-List-II
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseBetween(self, head: Optional[ListNode], left: int, right: int) -> Optional[ListNode]:
        if head is None or head.next is None:
            return head
        d=ListNode(0)
        d.next=head
        temp1=d
        for i in range(left-1):
            temp1=temp1.next
        temp2=temp1.next
        for j in range(right-left):
            temp=temp2.next
            temp2.next=temp.next
            temp.next=temp1.next
            temp1.next=temp
        return d.next
