# Print left view of a Given Binary Tree

```
void printLeft(Node root)
{
    if(root==null)return;
    Queue<Node> q = new LinkedList<>();

    q.add(root);

    while(!q.isEmpty())
    {
        int s = q.size();
        for(int i=0; i<s; i++)
        {
            Node curr = q.poll();
            if(i==0)System.out.print("curr.value");
            if(curr.left!=null)q.add(curr.left);
            if(curr.right!=null)q.add(curr.right);
        }
    }
}

```