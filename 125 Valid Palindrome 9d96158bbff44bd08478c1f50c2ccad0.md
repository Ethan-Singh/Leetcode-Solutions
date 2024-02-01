# 125. Valid Palindrome

So this one is more conceptually hard than it is hard hard. You pretty much just compare two halves, because a palindrome should be read the same forwards and backwards you meet in the middle. You just need a pointer for the left, and one for the right, and you check every character. Because there are special characters that don’t count you need to use ‘Character.IsLetterOrDigit(someVariable)’ and ‘Character.toLowerCase(someVariable)’. But other than that you are all good.

```java
class Solution {
    public boolean isPalindrome(String s) {
        int left = 0;
        int right = s.length() - 1;
        
        while(left < right){
            char leftChar = s.charAt(left);
            char rightChar = s.charAt(right);
            
            if(!Character.isLetterOrDigit(leftChar)){
                left++;
            } else if (!Character.isLetterOrDigit(rightChar)) {
                right--;
            } else {
                if(Character.toLowerCase(leftChar) != Character.toLowerCase(rightChar)){
                    return false;
                }
                left++;
                right--;
            }
            System.out.println(leftChar + " " + rightChar);
        }
        
        return true;
    }
}
```