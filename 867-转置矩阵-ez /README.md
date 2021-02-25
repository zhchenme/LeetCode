```java
class Solution {
    public int[][] transpose(int[][] matrix) {
        int xLength = matrix.length;
        int yLength = matrix[0].length;
        int[][] newMatrix = new int[yLength][xLength];
        for(int i = 0; i < xLength; i++) {
            for(int j = 0; j < yLength; j++) {
                newMatrix[j][i] = matrix[i][j];
            }
        }
        return newMatrix;
    }
}
```