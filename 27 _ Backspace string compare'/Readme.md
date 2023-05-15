# Backspace string compare - 844

```
class Solution {
    public boolean backspaceCompare(String s, String t) {

        StringBuilder sb1 = new StringBuilder("");
        StringBuilder sb2 = new StringBuilder("");

     
        for(int i=0; i<s.length(); i++)
        {
            if(s.charAt(i)!='#')
            {
                sb1.append(s.charAt(i));
          
            }
            else if(s.charAt(i)=='#' && sb1.toString().length() != 0)
                sb1.deleteCharAt(sb1.toString().length()-1);
            
            else
                continue;
        }

        System.out.println(sb1.toString());
  
        for(int i=0; i<t.length(); i++)
        {
            if(t.charAt(i)!='#')
            {
                sb2.append(t.charAt(i));
             
            }
            else if(t.charAt(i)=='#' && sb2.toString().length() !=0)
                sb2.deleteCharAt(sb2.toString().length()-1);
            else
                continue;
        }

        System.out.println(sb2.toString());

        String s1 = sb1.toString();
        String s2 = sb2.toString();

        if(s2.equals(s1))
            return true;
        return false;

    }
}
```