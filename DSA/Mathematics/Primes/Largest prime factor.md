```java
class Solution {
    static int largestPrimeFactor(int n) {
        int maxPrime = -1;

        // Step 1: Remove all factors of 2
        while (n % 2 == 0) {
            maxPrime = 2;
            n /= 2;
        }

        // Step 2: n must be odd at this point.
        // Iterate through odd numbers from 3 to sqrt(n)
        for (int i = 3; i * i <= n; i += 2) {
            while (n % i == 0) {
                maxPrime = i;
                n /= i;
            }
        }

        // Step 3: If n is still > 2, then n is prime
        if (n > 2) {
            maxPrime = n;
        }

        return maxPrime;
    }
}
```

### more optimal solution

```java
static int largestPrimeFactor(int n)
    {
        int maxPrime = -1;

        while(n % 2 == 0)
        {
            maxPrime = 2;
            n /= 2;
        }

        while(n % 3 == 0)
        {
            maxPrime = 3;
            n /= 3;
        }

        for(int i = 5 ; i * i <= n ; i += 6)
        {
            while(n % i == 0)
            {
                maxPrime = i;
                n /= i;
            }

            while(n % (i+2) == 0)
            {
                maxPrime = (i+2);
                n /= (i+2);
            }
        }

        if(n > 4)
        {
            maxPrime = n;
        }

        return maxPrime;
    }
```
