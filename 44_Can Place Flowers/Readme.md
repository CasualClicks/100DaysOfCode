# Leetcode 605. Can Place Flowers
```
class Solution {
    public boolean canPlaceFlowers(int[] flowerbed, int n) {
        int count = 0;
        int first = -2;
        int second = 0;
        while(second < flowerbed.length){
            while(second < flowerbed.length && flowerbed[second] != 1){
                second ++;
            }
            if(second >= flowerbed.length){break;}
            count += (second-first-2)/2;
            
            first = second;
            
            second ++;
        }
        System.out.println(second);
        count += (second-first-1)/2;
        return count >= n;
    }
}

```