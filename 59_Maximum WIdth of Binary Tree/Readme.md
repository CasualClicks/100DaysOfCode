# Maximum width of a Binary tree

```

int maxWidth(Node root)
{
    if(root==null)return 0;
    Queue<Node> q = new LinkedList<>();

    q.push(root);
    int res = 0;
    
    while(!q.isEmpty()){
        int count = q.size;
        res = Math.max(res, count);

        for(int i=0; i<count; i++){
            Node curr = q.poll();
            if(curr.left!=null)q.add(curr.left);
            if(curr.right!=null)q.add(curr.right);
        }
    }
}

```