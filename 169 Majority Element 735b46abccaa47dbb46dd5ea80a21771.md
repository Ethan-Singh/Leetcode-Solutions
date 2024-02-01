# 169. Majority Element

URL: https://leetcode.com/problems/majority-element/

If it’s the majority that means it’s more than half, which means that if you were to sort the array, it would occupy the direct middle.

```java
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length/2];
    }
}
```