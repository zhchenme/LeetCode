超时
```java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        if (nums.length <= 3) {
            return new ArrayList<>();
        }
        List<List<Integer>> res = new ArrayList<>();
        Set<String> strSet = new HashSet<>();
        for (int i = 0; i < nums.length; i++) {
            for (int j = i+1; j < nums.length; j++) {
                for (int k = j+1; k < nums.length; k++) {
                    if (nums[i] + nums[j] + nums[k] == 0) {
                        List<Integer> list = Arrays.asList(nums[i], nums[j], nums[k]);
                        list.sort(Comparator.naturalOrder());
                        String str = list.stream().map(Object::toString).collect(Collectors.joining(","));
                        if (strSet.contains(str)) {
                            continue;
                        }
                        strSet.add(str);
                        res.add(list);
                    }
                }
            }
        }
        return res;
    }
}
```

```java
    public List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        for (int i = 0; i < nums.length; i++) {
            // 防止数字重复使用
            if (i > 0 && nums[i] == nums[i - 1] || nums[i] > 0) {
                continue;
            }
            int target = -nums[i];
            for (int j = i + 1; j < nums.length; j++) {
                if (j > i + 1 && nums[j] == nums[j - 1]) {
                    continue;
                }
                int k = nums.length - 1;
                while (k > j && nums[j] + nums[k] > target) {
                    k--;
                }
                if (j == k) {
                    break;
                }
                if (nums[j] + nums[k] == target) {
                    List<Integer> list = new ArrayList<>();
                    list.add(nums[i]);
                    list.add(nums[j]);
                    list.add(nums[k]);
                    res.add(list);
                }
            }
        }
        return res;
    }
```