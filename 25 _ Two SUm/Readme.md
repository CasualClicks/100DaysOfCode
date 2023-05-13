# Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> idxMap = new HashMap<Integer,Integer>();
        idxMap.put(nums[0], 0);
        for(int i = 1; i < nums.length; i++){
            int requiredNum = (target - nums[i]);
            if(idxMap.containsKey(requiredNum)){
                int retNums[] = {idxMap.get(requiredNum), i};
                return retNums;
            }
            idxMap.put(nums[i], i);
        }
        return null;
    }
}
```