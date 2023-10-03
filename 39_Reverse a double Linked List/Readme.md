# Reverse a Double Linked List
```
class Solution {
    public Node reverseDLL(Node head) {
        if(head == null || head.next == null) return head;

        Node prev = null;
        Node curr = head;

        while(curr!=null)
        {
            prev = curr.prev;
            curr.prev = curr.next ;
            curr.next = prev;
            curr = curr.prev; 
        }

        return prev.prev;
    }
}

```