```java
class Solution {
    public static ArrayList<Integer> primeFac(int n) {
        // build up the boolean array
        ArrayList<Integer> primeFactors = new ArrayList<>();

        if(n < 2)
        {
            return primeFactors;
        }

        boolean primes[] = new boolean[n+1];
        Arrays.fill(primes,true);

        primes[0] = false;
        primes[1] = false;

        for(int i = 2 ; i * i <= n ; i++)
        {
            if(primes[i] == true)
            {
                for(int j = i * i ; j <= n ; j += i)
                {
                    primes[j] = false;
                }
            }
        }

        for(int i = 2; i <= n ; i++)
        {
            if(primes[i] == true && n % i ==0)
            {
                primeFactors.add(i);
            }
        }

        return primeFactors;
    }
}
```
