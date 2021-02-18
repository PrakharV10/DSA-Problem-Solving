[Question Link](https://practice.geeksforgeeks.org/problems/subarray-with-given-sum-1587115621/1)

- Time Complexity: O(N)
- Auxiliary Space: O(1)
```java
class Subarray{
    static ArrayList<Integer> subarraySum(int[] arr, int n, int s) {
        
        int startPos = 0;
        int endPos = 0;
        int sum = arr[startPos];
        ArrayList<Integer> ans = new ArrayList<Integer>();
        while(endPos < n){
            if(sum > s){
                sum = sum - arr[startPos];
                startPos+=1;
            }else if(sum < s){
                endPos+=1;
                if(endPos < n){
                sum = sum + arr[endPos];}
            }else{
                ans.add(startPos+1);
                ans.add(endPos+1);
                return ans;
            }
        }
        ans.add(-1);
        return ans;        
    }
}
```
