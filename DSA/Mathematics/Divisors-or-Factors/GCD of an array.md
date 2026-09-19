```java
class Solution {
    public int findGCD(int[] nums) {
        int result = nums[0];
        for (int i = 1; i < nums.size; i++) {
            result = gcd(result, nums[i]);

            // Optimization: If GCD becomes 1, it will stay 1
            if (result == 1) return 1;
        }
        return result;
    }

    private int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
}
```

## when we require only the largest and the smallest

```java
    public int gcd(int a, int b)
    {
        while(b != 0)
        {
            int rem = a % b;
            a = b;
            b = rem;
        }

        return a;
    }

    public int findGCD(int[] nums) {
      int max = 0, min = 1001;

      for(int num : nums)
      {
        max = Math.max(max,num);
        min = Math.min(min,num);
      }

      return gcd(min,max);
    }
```
