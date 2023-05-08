# Finding First Bad Version
```
public class Solution extends VersionControl {
    public int firstBadVersion(int n) {
        int start = 1;
        int end = n;

        int badVersion = Integer.MIN_VALUE;
        while(start <= end)
        {
            int mid = start + (end - start) / 2;
            if(isBadVersion(mid))
            {
                badVersion = mid;
                end = mid-1;
            }
            else if(!isBadVersion(mid))
                start = mid+1;     
        }
        return badVersion;
    }
}
```
