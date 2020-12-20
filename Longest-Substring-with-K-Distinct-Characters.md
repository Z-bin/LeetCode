### 链接: https://www.educative.io/courses/grokking-the-coding-interview/YQQwQMWLx80

### 题意 :给定一个字符串 s ，找出 至多 包含 k 个不同字符的最长子串 T

#### 解法: 滑动窗口

```c++
using namespace std;

#include <iostream>
#include <string>
#include <unordered_map>

class LongestSubstringKDistinct {
 public:
  static int findLength(const string& str, int k) {
    int maxLength = 0;
    int start = 0;
    unordered_map<char, int> uniqueMap;
    for (int end = 0; end < str.length(); end ++) {
      uniqueMap[str[end]]++;
      while(uniqueMap.size() > k) {
        uniqueMap[str[start]]--;
        if (uniqueMap[str[start]] == 0) {
          uniqueMap.erase(str[start]);
        }
        start++;
      }
      maxLength = max(maxLength, end - start + 1);
    }
    return maxLength;
  }
};

```

