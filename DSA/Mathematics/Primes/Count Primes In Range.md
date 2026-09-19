### Sieve algorithm to find the primes

```java
class Solution {
    int countPrimes(int l, int r) {
        boolean[] primes = new boolean[r+1];
        Arrays.fill(primes,true);
        if (r >= 0) primes[0] = false;
        if (r >= 1) primes[1] = false;

        // sieve algorithm to
        for (int i = 2; i * i <= r; i++) {
            if (primes[i]== true) {
                for (int j = i * i; j <= r; j += i) primes[j] = false;
            }
        }

        int ans = 0;
        for(int i=l;i<=r;i++) {
            if(primes[i]== true) ans++;
        }

        return ans;
    }
};
```
