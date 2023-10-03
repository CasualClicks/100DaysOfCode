# Leetcode 94. Given the root of a binary tree, return the inorder traversal of its nodes' values.
```
class Solution {

    public void preOrderT(TreeNode root, List<Integer> al)
    {
        if(root!=null)
        {
            al.add(root.val);
            preOrderT(root.left, al);
            preOrderT(root.right, al);
        }
    }
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> al = new ArrayList<Integer>();        
        preOrderT(root, al);

        return al;
    }
}

```