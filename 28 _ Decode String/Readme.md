# Decode String

```
public class Solution {
    public String decodeString(String s) {
        if (s == null || s.length() == 0) {
            return "";
        }
        Stack<Object> stack = new Stack<>();
        int number = 0;
        for (char c : s.toCharArray()) {
            if (Character.isDigit(c)) {
                number = number * 10 + (c - '0');
            } else if (c == '[') {
                stack.push(Integer.valueOf(number));
                number = 0;
            } else if (c == ']') {
                String str = popStack(stack);
                int num = (Integer) stack.pop();
                for (int i = 0; i < num; i++) stack.push(str);
            } else {
                stack.push(String.valueOf(c));
            }
        }
        return popStack(stack);
    }
    
    private String popStack(Stack<Object> stack) {
        StringBuffer sb = new StringBuffer();
        while (!stack.isEmpty() && (stack.peek() instanceof String)) {
            sb.insert(0, stack.pop());
        }
        return sb.toString();
    }
}
```