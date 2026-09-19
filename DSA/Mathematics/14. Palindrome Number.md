```java
class Solution {
    public boolean isPalindrome(int x) {
        int temp = x, rev = 0;
        while(temp > 0) {
            int lastDigit = temp % 10;
            rev = rev * 10 + lastDigit;
            temp /= 10;
        }
        return rev == x;
    }
}
```
