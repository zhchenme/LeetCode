```java
class Solution {
    public int maxSatisfied(int[] customers, int[] grumpy, int X) {
        int init = 0;
        for (int i = 0; i < customers.length; i++) {
            if (grumpy[i] == 0) {
                init += customers[i];
            }
        }
        int max = init;
        for (int i = 0; i < customers.length - X + 1; i++) {
            int tempMaxStatisfield = init;
            for (int j = i; j < X + i; j++) {
                if (grumpy[j] == 1) {
                    tempMaxStatisfield += customers[j];
                }
            }
            max = Math.max(tempMaxStatisfield, max);
        }
        return max;
    }
}
```

滑动窗口：

```java
    public int maxSatisfied(int[] customers, int[] grumpy, int X) {
        int total = 0;
        for (int i = 0; i < customers.length; i++) {
            if (grumpy[i] == 0) {
                total += customers[i];
            }
        }
        int slidingWindow = 0;
        // 计算一个窗口内的值
        for (int i = 0; i < X; i++) {
            slidingWindow += customers[i] * grumpy[i];
        }
        // 移动窗口
        int maxSlidingWindow = slidingWindow;
        for (int i = X; i < customers.length; i++) {
            slidingWindow = slidingWindow - customers[i - X] * grumpy[i - X] + customers[i] * grumpy[i];
            maxSlidingWindow = Math.max(maxSlidingWindow, slidingWindow);
        }
        return total + maxSlidingWindow;
    }
```