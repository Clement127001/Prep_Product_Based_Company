```java
class Solution {
    public void nextPermutation(int[] arr) {
        for(int i=arr.length-2;i>=0;i--) {
            if(arr[i]<arr[i+1]) {
                for(int j=arr.length-1;j>=(i+1);j--) {
                    if(arr[j]>arr[i]) {
                        int t = arr[i];
                        arr[i] = arr[j];
                        arr[j] = t;
                        reverse(arr, (i+1), arr.length-1);
                        return;
                    }
                }
            }
        }
        reverse(arr, 0, arr.length-1);
    }
    void reverse(int[] arr, int l, int r) { // [4, 3, 2] -> [2, 3, 4] : It's will not in increasing order
        while(l<r) {
            int t = arr[l];
            arr[l++] = arr[r];
            arr[r--] = t;
        }
    }
}
```

## More readable solution

```java
class Solution {
     public static void swap(int[] input,int start,int end)
     {
          int temp = input[start];
          input[start] = input[end];
          input[end] = temp;
     }

     public static void reverse(int[] input,int start,int end)
     {
          while(start<end)
          {
               swap(input,start,end);
               start++;
               end--;
          }
     }

    public void nextPermutation(int[]  input){
        int length = input.length;

        int indx1=-1, indx2=-1;

        // finding the index that is changing
        for(int i=length-1;i>0;i--)
        {
          if(input[i-1]<input[i])
          {
               indx1 = i-1;
               break;
          }
        }

        if(indx1==-1)
        {
          reverse(input,0,length-1);
          return;
        }
        else
        {
          // find the element just greater than element found at indx1
          for(int i=length-1;i>0;i--)
          {
               if(input[i]>input[indx1])
               {
                    indx2 = i;
                    break;
               }
          }
        }

        swap(input,indx1,indx2);
        reverse(input,indx1+1,length-1);
    }
}
```
