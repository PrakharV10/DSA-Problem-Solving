[Question Link](https://practice.geeksforgeeks.org/problems/count-the-triplets4615/1)

JAVA SOLUTION - 
- Time Complexity - O(n^2)
- Auxiliary Space: O(1)

```java
class Solution {
    int countTriplet(int arr[], int n) {
        Arrays.sort(arr);
        int count = 0;
        for(int k = n-1; k>=2 ; k--){
            int l = 0;
            int h = k-1;
            while(l<h){
                if(arr[l]+arr[h] > arr[k]){
                    h--;
                }else if(arr[l]+arr[h] < arr[k]){
                    l++;
                }else{
                    count ++;
                    l++;
                    h--;
                }
            }
        }
        return count;
    }
}
```
