# Given a Binary Tree, state whether they foloow children sum property. i.e., sum of children == node
```
boolean childrenSum(Node root)
{
    if(root==null)return true;
    if(root.left==null && root.right==null)
        return true;

    int sum=0;
    if(root.left!=null){sum+=root.left.value;}
    if(root.right!+null){sum+=root.right.value};

    return(root.value==sum) && childrenSum(root.left) && childrenSum(root.right);
}

```