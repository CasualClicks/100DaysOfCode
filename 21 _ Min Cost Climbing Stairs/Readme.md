# Min cost Climbing Stairs
```
class Solution {
    int rec(int i,int n,int [] a,int[] dp)
    {
        
        if(i>=n)
            return 0;
        
        if(dp[i]!=-1)
            return dp[i];
        dp[i]=a[i]+Math.min(rec(i+2,n,a,dp),rec(i+1,n,a,dp));
       
        return (int)dp[i];
            
    }
    public int minCostClimbingStairs(int[] cost) {
         int n=cost.length;
            int[] dp = new int[n+11];
            Arrays.fill(dp, -1); 
            int a=rec(0,n,cost,dp);
            int b=rec(1,n,cost,dp);
            return (int)(Math.min(a,b));
    }
}
```