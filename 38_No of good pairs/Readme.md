# Leetcode 1512. Number of Good Pairs
```
class Solution {
    public int numIdenticalPairs(int[] nums) {
        int arr[] = new int[101];

        int ans =0;
        for(int i=0; i<nums.length; i++)
        {
            ans += arr[nums[i]]++;
        }

        return ans;
    }
}

```