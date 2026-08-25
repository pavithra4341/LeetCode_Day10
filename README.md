# 10. Regular Expression Matching

**LeetCode Hard** | DP | String

## Problem
Given `s` and pattern `p`, implement regex matching with `.` and `*`.

- `.` Matches any single character
- `*` Matches zero or more of the preceding element
- Matching must cover the entire input string

## Solution - DP Approach

We use `dp[i][j]` where `dp[i][j] = true` if `s[0..i-1]` matches `p[0..j-1]`.

### Initialization
```java
dp[0][0] = true
dp[0][j] = dp[0][j-2] if p[j-1] == '*' // a*, a*b* can match empty
