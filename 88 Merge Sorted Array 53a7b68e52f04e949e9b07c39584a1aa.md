# 88. Merge Sorted Array

URL: https://leetcode.com/problems/merge-sorted-array/

```java
class Solution {
	public void merge(int[] nums1, int m, int[] nums2, int n) {
		for(int i = 0, j = m; i<n; i++){
			nums1[j++] = nums2[i];
		}
		Arrays.sort(nums1);
	}
}
```

So like, you just start at the end of the first array, cause there are just 0’s as placeholders there. You then just iterate from there (m), and use that Arrays.sort, cause big brain. 

>:)