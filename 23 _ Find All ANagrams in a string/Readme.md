# Find all anagrams in a String

## Method 1
```
class Solution {
    public boolean isAnagram(String s, String t){
        int arr[] = new int[26];
        for(int i=0; i<s.length(); i++)
        {
            arr[s.charAt(i)-97] += 1;
            arr[t.charAt(i)-97] -= 1;
        }
        for(int i: arr)
            if (i != 0)
                return false;
        return true;
        
    }
    public List<Integer> findAnagrams(String s, String p) {
        List<Integer> lst = new ArrayList<Integer>();
        int len = p.length();
        StringBuilder sb = new StringBuilder();


        for(int i=0; i<s.length()-len+1; i++)
        {
            sb.setLength(0);
            sb.append(s.charAt(i));
            for(int j=i+1; j<len+(i); j++)
            {
                sb.append(s.charAt(j));
            }

            if(isAnagram(sb.toString(), p))
                lst.add(i);
        }

        return lst;
    }
}
```

## Method 2
```
class Solution {
    public List<Integer> findAnagrams(String s, String p) {
        List<Integer> rst = new ArrayList<>();
        if (s == null || s.length() == 0 || s.length() < p.length()) {
            return rst;
        }

        int[] map_p = new int[26];
        int[] map_s = new int[26];
        // Initialize the map / window
        for (int i = 0; i < p.length(); i++) {
            map_p[p.charAt(i) - 'a']++;
        }
        for (int i = 0; i < p.length(); i++) {
            map_s[s.charAt(i) - 'a']++;
        }

        for (int i = 0; i < s.length() - p.length(); i++) {
            if (isMatch(map_p, map_s)) {
                rst.add(i);
            }
            // if don't match, we move the sliding window
            // remove the preceding character and add a new succeeding character to the new window
            map_s[s.charAt(i+p.length()) - 'a']++;
            map_s[s.charAt(i) - 'a']--;
        }
        if (isMatch(map_p, map_s)) {
            rst.add(s.length() - p.length());
        }
        return rst;
    }

    public boolean isMatch(int[] arr1, int[] arr2) {
        for (int i = 0; i < arr1.length; i++) {
            if (arr1[i] != arr2[i]) {
                return false;
            }
        }
        return true;
    }
}
```