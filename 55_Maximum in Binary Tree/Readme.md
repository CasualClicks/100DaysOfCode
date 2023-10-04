# Find maximum value in a binary tree

```
int getMax(Node root)   
{
    if(root==null)
        return Integer.MIN_VALUE;

    return Math.max(root.value, Math.max(getMax(root.left), getMax(root.right)));
} 

```