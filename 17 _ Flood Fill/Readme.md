# You are also given three integers sr, sc, and color. You should perform a flood fill on the image starting from the pixel image[sr][sc].
```
class Solution {
    
    public void fillIt(int[][] image, int sr, int sc, int color, int trackColor){
        
        if(sr < 0 || sr >= image.length 
           || sc < 0 || sc >= image[0].length) return;
        
        if(trackColor != image[sr][sc]) return;
        
        image[sr][sc] = color;
        
        fillIt(image,sr-1,sc,color,trackColor);
        fillIt(image,sr+1,sc,color,trackColor);
        fillIt(image,sr,sc-1,color,trackColor);
        fillIt(image,sr,sc+1,color,trackColor);
        
    }
    
    public int[][] floodFill(int[][] image, int sr, int sc, int color) {
        if(image[sr][sc] == color) return image;
        fillIt(image,sr,sc,color,image[sr][sc]);
        return image;
    }
}
```