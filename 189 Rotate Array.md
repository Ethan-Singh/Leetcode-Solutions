# 189. Rotate Array

URL: https://leetcode.com/problems/rotate-array/

Okay, so this one is a bit more complicated. We make a separate function for this one. Essentially, when “rotating” the array we are really just reversing it. We want to reverse two points. The first half and the second half, then we want to reverse the whole thing.

Think of it like [1,2,3,4,5,6,7] where k =3.

4 is at index 3 so it separates the two.

First reverse

→ [4,3,2,1,7,6,5]

Second reverse]

→ [5,6,7,1,2,3,4].

```java
class Solution {
    public static void reverse(int nums[], int leftIndex, int rightIndex){
        int li = leftIndex;
        int ri = rightIndex;
        
        while (li < ri){
            int store = nums[li];
            nums[li] = nums[ri];
            nums[ri] = store;
            
            li++;
            ri--;
        }
    }
    
    public void rotate(int[] nums, int k) {
        k = k % nums.length;
        if(k < 0){
            k += nums.length;
        }
        
        reverse(nums, 0, nums.length-k-1);
        reverse(nums, nums.length-k, nums.length-1);
        reverse(nums, 0, nums.length-1);
    }

}
```