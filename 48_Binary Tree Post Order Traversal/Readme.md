# Leetcode 145. Given the root of a binary tree, return the postorder traversal of its nodes' values.
```
class Solution {
    public void postOrderT(TreeNode root, List<Integer> al)
    {
        if(root!=null)
        {
            postOrderT(root.left, al);
            postOrderT(root.right, al);
            al.add(root.val);
        }
    }

    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> al = new ArrayList<>();
        postOrderT(root, al);

        return al;    
    }
}

```