
## 64 [Minimum Path Sum](https://leetcode.com/problems/minimum-path-sum/)
Given a _m_ x _n_ grid filled with non-negative numbers, find a path from top left to bottom right which _minimizes_ the sum of all numbers along its path.
You can only move either down or right at any point in time.

**Explanation:**
The input is an 2D vector , so we also use a 2D vector to establish our DP solution.
For any elements not on the border, there are only two ways to reach it because we are only allowed to move either down or right. So the optimal solution for `Grid[i][j]` would be determined by `solution[i-1][j]` and `solution[i][j-1]`. `solution[i][j]` represents the optimal solution for reaching `Grid[i][j]` from `Grid[0][0]`

So, we can characterize the structure like 

 - `solution[i][j] = min(solution[i-1][j],solution[i][j-1])+Grid[i][j]` normal case
 - `s[0][j] = s[0][j-1] + v[0][j] corner case 1`  border 
 - `s[i][0] = s[i-1][0] + v[i][0] corner case 2`  border
 - `s[0][0] = v[0][0] corner case 3` initial point

**Codes:**
```
#include<iostream>
#include<vector>
#include<array>

// DP
// s[i][j] = min(s[i-1][j] , s[i][j-1]) + v[i][j] normal case
// s[0][j] = s[0][j-1] + v[0][j] corner case
// s[i][0] = s[i-1][0] + v[i][0] corner case
// s[0][0] = v[0][0] corner case
using namespace std;
class Solution {
public:
    int minPathSum(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        
        vector<vector<int>> s(m,vector<int>(n));

        for(int i = 0; i < m; ++i){
            for(int j = 0; j < n; j++){
                find_solution(grid,s,i,j);
            }
        }
        return s[m-1][n-1];
    }

    void find_solution(vector<vector<int>>& grid,vector<vector<int>>& s, int m,int n){
        if(m==0 && n==0){
            s[0][0] == grid[0][0];
        }
        if(m == 0){
            s[0][n] = s[0][n-1] + grid[0][n];
            return;
        }
        if(n == 0){
            s[m][0] = s[m-1][0] + grid[m][0];
            return;
        }
        s[m][n] = min(s[m-1][n],s[m][n-1]) + grid[m][n];
        return;
    }
};
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQxNjQ0NTc4M119
-->