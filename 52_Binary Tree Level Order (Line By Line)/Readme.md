# Binary Tree Level Order Traversal
```
void printLevel(Node root){
    if(root==null)return;
    Queue<Node> q = new LinkedList<>();
    q.add(root);
    q.add(null);
    
    while(q.size()>1)
    {
        Node curr = q.poll();
        if(curr==null){
            System.out.println();
            q.add(null);
            continue;
        }
        System.out.println(curr.value+" ");
        if(curr.left!=null)q.add(curr.left);
        if(curr.right!=null)q.add(curr.right);
    }
}

```


# Method II
```
void printLevel(Node root){
    if(root==null)
        return;
    Queue<Node> q = new LinkedList<>();
    q.add(root);

    while(!q.isEmpty())
    {
        int s = q.size();

        for(int i=0; i<s; i++;)
        {
            Node curr = q.poll();
            System.out.println(curr.value+" ");
            if(curr.right!=null)q.add(curr.right);
        }
        System.out.println();
    }
}

```