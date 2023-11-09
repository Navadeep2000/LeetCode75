# Intuition
- The current *ListNode* "**head**" has two common nodes: "***value***" and "***next***". 
- Add a previous node "***prev***" with "**previous_pointer**" that points to "*None*".
- To access a *ListNode*, we iterate the *current_pointer* until it points to **None** object.
-  Similarly, We can iterate the *previous_pointer* in reverse i.e., from the end, till it reaches the start "*None*" object.

## Watch this video for the Visual Understanding:
[Animated Explanation of Reversing a LinkedList](https://drive.google.com/file/d/1RojuSGrO11lcgcvnMgRSJMXJn45UMKQR/view?usp=drive_link)
 
# Complexity
- Time complexity: $$O(n)$$

# Code
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]: 
        current_pointer = head  # Current pointer pointed to the ListNode "head"
        previous_pointer = None  # Creating a Previous pointer 

        # Note these points of observation:
        # To access a ListNode, we iterate the pointer until it points to None object
        # We are creating a pointer "previous_pointer" pointing to the object "prev" that starts with the None object, 
        # So that we can iterate the pointer in reverse from the end

        while current_pointer:  # This loop ends when current_pointer reaches None object

            next = current_pointer.next  # "next" object which is the current node's next
            
            current_pointer.next = previous_pointer  # The current node's next points to the previous pointer of the same node

            previous_pointer = current_pointer  # Previous pointer points towards the current node

            current_pointer = next  # This is the iteration increment through the ListNode

        return previous_pointer

```
