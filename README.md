# 🚀 LeetCode POTD - Day 1

<table>
<tr>
<td align="left" width="400">
  <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*VOQU8CuPG34Gsd1yJCadOQ.png" width="100%"/>
</td>
</tr>
</table>

---

## 🧙‍♂️ Problem: 2016. Maximum Difference Between Increasing Elements

[Link to problem](https://leetcode.com/problems/maximum-difference-between-increasing-elements)

---

## 🛠️ Brute-Force Approach

```cpp
class Solution {
public:
    int maximumDifference(vector<int>& nums) {
        int n = nums.size();
        int maxDiff = -1;

        for(int i = 0; i < n; i++){
            for(int j = i + 1; j < n; j++){
                if(nums[i] < nums[j]){
                    maxDiff = max(maxDiff, nums[j] - nums[i]);
                }
            }
        }
        return maxDiff;
    }
};
```

## 🔥 Optimal Solution

```cpp
class Solution {
    public int maximumDifference(int[] nums) {
        int n = nums.length;
        int minElement = nums[0];
        int maxDiff = -1;

        for (int j = 1; j < n; j++) {
            if (nums[j] > minElement) {
                maxDiff = Math.max(maxDiff, nums[j] - minElement);
            } else {
                minElement = nums[j];
            }
        }

        return maxDiff;
    }
}
```

---

## ⏱️ Time & Space Complexity

| Approach    | Time  | Space |
| ----------- | ----- | ----- |
| Brute-Force | O(n²) | O(1)  |
| Optimal     | O(n)  | O(1)  |

---

> **"The best optimization starts with a clean understanding of brute-force."**
