```java
class Solution {
    public String getPermutation(int n, int k) {
        List<Integer> availableNumbers = new ArrayList<>();
        for(int i=1;i<=n;i++) availableNumbers.add(i);
        StringBuilder res = new StringBuilder();
        int totalRange = fac(n);
        int segment = totalRange/n;
        while(k>0) {
            int i=1;
            while(i*segment<k) i++;
            res.append(availableNumbers.get(i-1).toString());
            availableNumbers.remove(i-1);

            k -= (i*segment>k) ? (segment*(i-1)) : k;
            if(k==0) break;

            totalRange = segment;
            segment /= availableNumbers.size();
        }
        if(availableNumbers.size()>0) {
            for(int i=availableNumbers.size()-1;i>=0;i--) res.append(availableNumbers.get(i).toString());
        }
        return res.toString();
    }
    int fac(int n) {
        if(n==1 || n==2) return n;
        return n*fac(n-1);
    }
}
```

## More readable solution

```java
public String getPermutation(int n, int k) {
        ArrayList<Integer> nums = new ArrayList<>();
        int fact = 1;

        for(int i = 1; i < n ; i++)
        {
            nums.add(i);
            fact *= i;
        }

        nums.add(n);
        k = k - 1;

        String res = "";

        while(true)
        {
            res += nums.get(k/fact);
            nums.remove(k/fact);

            if(nums.size() == 0)
            {
                break;
            }

            k = k % fact;
            fact = fact / nums.size();
        }

        return res;
    }
```
