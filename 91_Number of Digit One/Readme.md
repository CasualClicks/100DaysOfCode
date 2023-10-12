# Leetcode 233. Number of digit one

```
//Naive Approach

// class Solution {
//     public int countOne(int num)
//     {
//         int sum=0;
//         while(num>0){
//            if(num%10==1)sum++;
//            num = num/10;
//         }

//         return sum;
//     }
//     public int countDigitOne(int n) {
//         int count=0;
//         for(int i=1; i<=n; i++){
//             count += countOne(i);
//         }

//         return count;
//     }
// }

//Efficient 
class Solution {
  public int countDigitOne(int n) {
    int ans = 0;

    for (long pow10 = 1; pow10 <= n; pow10 *= 10) {
      final long divisor = pow10 * 10;
      final int quotient = (int) (n / divisor);
      final int remainder = (int) (n % divisor);
      if (quotient > 0)
        ans += quotient * pow10;
      if (remainder >= pow10)
        ans += Math.min(remainder - pow10 + 1, pow10);
    }

    return ans;
  }
}

```