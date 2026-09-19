```java
class Solution {
    // this solution is suitable when we are asked to get the gcd between the smallest and largest in an array, otherwise we need to follow as per 23.
    public int findGCD(int[] arr) {
        int smallest = arr[0], largest = arr[0];
        for(int x : arr) {
            if(x>largest) largest = x;
            if(x<smallest) smallest = x;
        }
        return calcGcd(smallest, largest);
    }
    int calcGcd(int a, int b) {
        if (b == 0) return a;
        return calcGcd(b, a % b);
    }
}
```
