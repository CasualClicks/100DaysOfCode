# Find Pivot Index

```
class Solution 
{
    public int pivotIndex(int[] nums) 
    {
        int sum = 0;
        int sumTotal = 0;
        for(int i=0; i<nums.length; i++)
            sumTotal+=nums[i];
        for(int i=0; i<nums.length;i++)
        {
            if(sum==sumTotal-sum-nums[i])
                return i;
            sum+=nums[i];
        }
        return -1;
    }
}
```
<h3>Time Complexity: <em>O(n)</em></h3>