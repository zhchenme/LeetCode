```java
public int[][] flipAndInvertImage(int[][] A) {
        int xLength = A[0].length;
        int yLength = A.length;
        int[][] inverseArray = new int[xLength][yLength];
        for (int i = 0; i < yLength; i++) {
            for (int j = xLength - 1; j >= 0; j--) {
                inverseArray[i][xLength - j - 1] = A[i][j] == 0 ? 1 : 0;
            }
        }
        return inverseArray;
    }
```