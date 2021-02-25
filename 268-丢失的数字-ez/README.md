2021-02-22

```java
class Solution {
    public int missingNumber(int[] nums) {
        int limitNum = nums.length;
        int allTotal = (limitNum + 1) * limitNum / 2;
        int subTotal = 0;
        for(int i = 0; i < limitNum; i++) {
            subTotal += nums[i];
        }
        return allTotal - subTotal;
    }
}
```