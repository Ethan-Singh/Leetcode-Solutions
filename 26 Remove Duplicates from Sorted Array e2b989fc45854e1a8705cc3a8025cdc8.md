# 26. Remove Duplicates from Sorted Array

URL: https://leetcode.com/problems/remove-duplicates-from-sorted-array/

So you pretty much have two variables. One stores the last number (to check if you are looking at a unique number), and the other stores the count for how many unique numbers you’ve got so far. The lastNumber starts at nums[0] because the first variable is always unique, and therefore the counter starts at 1. You just compare and return counter..

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int lastNumber = nums[0];
        int counter = 1;
        
        for(int i = 0; i < nums.length; i++){
            if(nums[i] != lastNumber){
                nums[counter++] = nums[i];
                lastNumber = nums[i];
            }
        }

        return counter;
    }
}
```