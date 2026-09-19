## Recursive solution

```java
class Solution {
    public static int gcd(int a, int b) {
        if(b==0) return a;
        return gcd(b, a%b); // tail recursion, so it can be converted into iterative solution
    }
}
```

## Iterative solution -> even better, because there will be extra space required

```java
// this algorithm is know as Euclidean algorithm for finding the GCD
class Solution {
    public static int gcd(int a, int b) {
       while(b != 0)
       {
           int temp = b;
           b = a % b;
           a = temp;
       }

       return a;
    }
}
```
