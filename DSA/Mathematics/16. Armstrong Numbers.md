```java
class Solution {
    static boolean armstrongNumber(int n) {
        int original = n;
        int sum = 0;
        // good approach, but take TC : O(Digits)
        int digits = String.valueOf(n).length();

        // can be found in  TC : O(1)
        int digits = math.log10(n);

        int temp = n;
        while (temp > 0) {
            sum += Math.pow(temp % 10, digits);
            temp /= 10;
        }

        return sum == original;
    }
}
```
