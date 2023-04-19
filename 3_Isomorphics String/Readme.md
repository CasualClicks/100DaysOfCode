# Determine if 2 String are Isomorphic Strings or not

```
import java.util.*;

class Solution 
{
    public boolean isIsomorphic(String s, String t) 
    {
       HashMap<Character, Character> map = new HashMap<>();
       
       for(int i=0; i<s.length(); i++)
       {
           if(map.containsKey(s.charAt(i)))
           {
               if(map.get(s.charAt(i)) != t.charAt(i))
                return false;
           }
           else if(!map.containsValue(t.charAt(i)))
           {
               map.put(s.charAt(i), t.charAt(i));
           }
           else
            return false;
       }
       return true;
    }
    
}
```
<h3>Time Complexity: <em>O(n)</em></h3>