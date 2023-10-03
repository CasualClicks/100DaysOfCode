# Leetcode 349. Intersection of two arrays
```
class Solution {
    public String mergeAlternately(String word1, String word2) {
        int pointer1=0;
        int pointer2=0;
        StringBuilder sb = new StringBuilder();

        while(pointer1<word1.length() && pointer2<word2.length())
        {
            sb.append(Character.toString(word1.charAt(pointer1++)));
            sb.append(Character.toString(word2.charAt(pointer2++)));
        }

        if(pointer1 == word1.length() && pointer2 == word2.length())
            return sb.toString();
        else if(pointer1 <word1.length() && pointer2 == word2.length())
            while(pointer1 != word1.length())
                sb.append(Character.toString(word1.charAt(pointer1++)));
        else if(pointer2 <word2.length() && pointer1 == word1.length())
            while(pointer2 != word2.length())
                sb.append(Character.toString(word2.charAt(pointer2++)));

        return sb.toString();
    }
}

```