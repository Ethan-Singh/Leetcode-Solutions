# 27. Remove Element

URL: https://leetcode.com/problems/remove-element/

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int count = 0;
        for(int i = 0; i<nums.length; i++){
            if(nums[i] != val){
                nums[count] = nums[i];
                count++;
            }
        }
        return count;
        
    }
}
```

So like, you have a counter which essentially returns the ‘count’ of good numbers. If you find a good number the counter goes up. If you find a bad number the counter stays where it is, until you find another good number, you then replace the bad number with the good number and keep going.