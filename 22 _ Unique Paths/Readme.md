# There is a robot on an m x n grid. The robot is initially located at the top-left corner (i.e., grid[0][0]). The robot tries to move to the bottom-right corner (i.e., grid[m - 1][n - 1]). The robot can only move either down or right at any point in time.

# Method - 1
```
private static int uniquePathsUtil(int m, int n, int[][] dp) {
        if(m == 1 || n == 1) return 1;
        if(dp[m][n] != 0)
            return dp[m][n];
        return dp[m][n] = uniquePathsUtil(m-1, n, dp) + uniquePathsUtil(m, n-1, dp);
    }
```

# Method - 2
```
class Solution {
    public static int uniquePaths(int m, int n) {
        int dp[][] = new int[m+1][n+1];
        return uniquePathsUtil(m,n,dp);
    }
    private static int uniquePathsUtil(int m, int n, int[][] dp) {
        if(m == 1 || n == 1) return 1;
        if(dp[m][n] != 0)
            return dp[m][n];
        return dp[m][n] = uniquePathsUtil(m-1, n, dp) + uniquePathsUtil(m, n-1, dp);
    }
    
}
```