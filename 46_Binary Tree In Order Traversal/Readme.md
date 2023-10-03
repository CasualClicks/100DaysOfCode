# Leetcode 94. Given the root of a binary tree, return the inorder traversal of its nodes' values.
```
class Solution {
    public void inorderTraversal(TreeNode root, List<Integer> al)
    {
        if(root!=null)
        {
            inorderTraversal(root.left, al);
            al.add(root.val);
            inorderTraversal(root.right, al);
        }
    }
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> al = new ArrayList<Integer>();

        inorderTraversal(root, al);

        return al;
    }
}

```