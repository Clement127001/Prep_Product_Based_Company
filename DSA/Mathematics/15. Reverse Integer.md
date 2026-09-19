```java
class Solution {
    public int reverse(int x) {
        long rev = 0;
        while (x != 0) {
            rev = rev * 10 + x % 10;
            x /= 10;
            // we need this check because while reversing the number can overflow
            if(rev<Integer.MIN_VALUE || rev>Integer.MAX_VALUE) return 0;
        }
        return (int)rev;
    }
}
```
