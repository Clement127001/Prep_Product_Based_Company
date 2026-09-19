## this solution is going to have

## TC: O(n\*logn)

```java
class Solution {
    public static void print_divisors(int n) {
        List<Integer> nums = new ArrayList<>();
        for(int i=1;i*i<=n;i++) {
            if(n%i==0) {
                nums.add(i);
                if(i!=n/i) nums.add(n/i);
            }
        }
        Collections.sort(nums);
        for(int x: nums) System.out.print(x+" ");
    }
}
```

## this is the best solution, TC : O(sqrt(n))

```java
public ArrayList<Integer> getDivisors(int n) {
        ArrayList<Integer> small = new ArrayList<>();
        ArrayList<Integer> large = new ArrayList<>();

        for(int i = 1 ; i * i <= n ; i++)
        {
            if(n % i == 0)
            {
                small.add(i);

                // to avoid duplicates
                if((n/i) != i)
                {
                    large.add((n/i));
                }
            }
        }

        Collections.reverse(large);
        small.addAll(larget);

        return small;
    }
```
