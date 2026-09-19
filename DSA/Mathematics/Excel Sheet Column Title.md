```java
class Solution {
    public String convertToTitle(int n) {
        StringBuilder res = new StringBuilder();
        while(n>0) {
            for(int i=26;i>=1;i--){
                if((n-i)%26==0) {
                    char character = (char)(64+i);
                    res.insert(0, String.valueOf(character));
                    n -= i;
                    n /= 26;
                    break;
                }
            }
        }
        return res.toString();
    }
}
```

## Better approach

```java
 public String convertToTitle(int n) {
       String res = "";

        while(n>0)
        {
            n--;
            char ch = (char) ('A'+ (n % 26));
            res = ch + res;
            n /= 26;
        }

        return res;
    }
```
