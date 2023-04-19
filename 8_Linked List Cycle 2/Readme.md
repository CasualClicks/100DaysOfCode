# Return The node where cycle begins first
```
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
 ```
 ```
public class Solution 
{

    ```
    public ListNode intersectionPointInCycle(ListNode head)
    {
        if(head == null) return null;
        ListNode slow = head;
        ListNode fast = head;
        
        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
            if(slow == fast){
                return slow;
            }
        }
        return null;
    }
    ```

    ```
    public ListNode detectCycle(ListNode head) 
    {
         if(head == null) return null;
        ListNode slow = head;
        ListNode fast = intersectionPointInCycle(head);
        
        if(fast == null) return null;
        while(slow != fast){
            slow = slow.next;
            fast = fast.next;
        }
        return slow;
    }
    ```
      
}
```
<h3>Time Complexity: <em>O(n)</em></h3>