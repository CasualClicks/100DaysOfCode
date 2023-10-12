# Leetcode 383. Ransom Note

```
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        int arr[] = new int[26];

        for(char i: magazine.toCharArray())
            arr[i-97]++;
        for(char i : ransomNote.toCharArray())
            arr[i-97]--;
        for(int c: arr)
            if(c<0)
                return false;
        
        return true;
    }
}

```