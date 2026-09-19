```java
class PrimeFactorizer {
    static void printPrimeFactors(int n) {

        // Step 1: Handle the number of 2s that divide n
        while (n % 2 == 0) {
            System.out.print(2 + " ");
            n /= 2;
        }

        // Step 2: n must be odd at this point.
        // Iterate from 3 to sqrt(n) in steps of 2
        for (int i = 3; i * i <= n; i += 2) {
            // While i divides n, print i and divide n
            while (n % i == 0) {
                System.out.print(i + " ");
                n /= i;
            }
        }

        // Step 3: If n is a prime number greater than 2
        if (n > 2) {
            System.out.print(n);
        }
    }
}
```

## MY approach - I don't want to retire with my solution, so I have come up with my same solution as we are finding the prime number

```java
class Solution {
    ArrayList<Integer> primeFactors(int n) {
      ArrayList<Integer> res = new ArrayList<>();

      while(n % 2 == 0)
      {
          res.add(2);
          n /= 2;
      }

      while( n % 3 == 0)
      {
          res.add(3);
          n /= 3;
      }

      for(int i = 5 ; i * i <= n ; i += 6)
      {
          while(n % i == 0)
          {
              res.add(i);
              n = n / i;
          }

          while(n % (i + 2) == 0)
          {
              res.add(i+2);
              n = n / (i+2);
          }
      }

      if(n > 4)
      {
          res.add(n);
      }

      return res;
    }
}

```
