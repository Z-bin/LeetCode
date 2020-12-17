### 链接: https://practice.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1

### 题意:Given an array of integers Arr of size **N** and a number **K**. Return the maximum sum of a subarray of size K.

#### 解法:滑动窗口

```C++
class Solution{   
public:
    int maximumSumSubarray(int K, vector<int> &Arr , int N){
        // code here 
        
        int res = 0;
        int temp = 0;
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < K; j++) {
                if (i + j < N) {
                    temp += Arr[i + j];
                }
            }
            res = max(temp, res);
            temp = 0;
        }
        return res;
    }
};
```

