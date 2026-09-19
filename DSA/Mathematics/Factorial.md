```java
// this is recursion solution, this will take extra space for stack call trace
class Solution {
    int factorial(int n) {
        if(n==0 || n==1) return 1;
        if(n==2) return 2;
        return n*factorial(n-1);
    }
}
```

## Better solution -> using recursion

```java
int factorial(int n)
    {
        int fact = 1;

        for(int i = 2 ; i <= n ; i++)
        {
            fact *= i;
        }

        return fact;
    }
```
