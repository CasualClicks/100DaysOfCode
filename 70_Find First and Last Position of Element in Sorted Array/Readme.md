# Leetcode 34. Find first and last position of element in sorted array

```
class Solution {

    public int searchFirst(int x, int[] nums){
        int low = 0;
        int high = nums.length-1;

        while(low<=high){
            int mid = (low+high)/2;

            if(nums[mid] <  x)
                low = mid+1;
            else if(nums[mid]>x)
                high = mid-1;
            else{
                if(mid==0 || nums[mid]!=nums[mid-1])
                    return mid;
                else
                    high = mid-1;
            }
        }
        return -1;
    }

    public static int searchLast(int x, int[] nums){
        int low = 0;
        int high = nums.length-1;

        while(low<=high){
            int mid = (low+high)/2;
            if(nums[mid]<x)
                low = mid+1;
            else if(nums[mid]>x)
                high = mid-1;
            else{
                if(mid==nums.length-1 || (nums[mid]!=nums[mid+1]))
                    return mid;
                else
                    low = mid+1;
            }
        }
        return -1;
    }
    public int[] searchRange(int[] nums, int target) {
        int arr[] = new int[2];
        arr[0] = searchFirst(target, nums);
        arr[1] = searchLast(target, nums);

        return arr;
    }
}

```