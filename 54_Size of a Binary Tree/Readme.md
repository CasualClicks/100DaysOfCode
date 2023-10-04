# Calculate number of nodes in a binary tree

```
int getSize(Node root)
{
    if(root==null)return 0;

    return getSize(root.left)+getSize(root.right)+1;
}    

```