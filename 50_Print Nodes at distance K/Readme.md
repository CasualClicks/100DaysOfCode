# Given a binary tree, Print the nodes at a given distance K
```
void printKDistance(Node root, k)
{
    if(root==null)return
    if(k==0)System.out.print(root.value+" ");
    else{
        printKDistance(root.left, k-1);
        printKDistance(root.right, k-1);
    }
}

```