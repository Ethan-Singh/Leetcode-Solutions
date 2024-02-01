# 80. Remove Duplicates from Sorted Array II

URL: https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/?envType=study-plan-v2&envId=top-interview-150

So you have an index and a count. The index keeps track of the ‘true’ array, while the ‘count’ is how many times you’ve run into that number. Essentially you want to start and i = 1, and then compare the previous so nums[i-1]. If they are equal you want the counter to go up, else, you want the counter to go back to 1. After these you have an if that confirms the counter is ≤2, to make sure the triples don’t catch. It’s okay because they’ll cycle back to 1 eventually. Then you just return index.

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int index = 1;
        int count = 1;
        
        
        for(int i = 1; i<nums.length; i++){
            if(nums[i] == nums[i-1]){
                count++;
            }
            else {
                count = 1;
            }
            if(count <=2){
                nums[index++] = nums[i];
            }
        }
        
        return index;
        
    }
}
```