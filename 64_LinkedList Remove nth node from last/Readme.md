# Leetcode 19. Remove nth node from the last of a singly Linked List

```
class Solution {

    public int length(ListNode head){
        ListNode curr = head;
        int sum=0;
        if(head==null)return 0;
        while(head!=null){
            sum++;
            head = head.next;
        }
        return sum;
    }
    public ListNode removeNthFromEnd(ListNode head, int n) {
        int NodeToRemove = length(head)-n+1;

        if(length(head)==1)
            return null;

        if(length(head)==n)
        {
            return head.next;
        }
        

        ListNode curr = head;
        for(int i=0; i<NodeToRemove-2; i++)
        {
            curr = curr.next;
        }

        ListNode next = curr.next;
        curr.next = next.next;

        return head;
    }
}

```