# 1. Two Sum

    Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

    You may assume that each input would have exactly one solution, and you may not use the same element twice.

    You can return the answer in any order.



    Example 1:

    Input: nums = [2,7,11,15], target = 9
    Output: [0,1]
    Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
    Example 2:

    Input: nums = [3,2,4], target = 6
    Output: [1,2]
    Example 3:

    Input: nums = [3,3], target = 6
    Output: [0,1]


    Constraints:

    2 <= nums.length <= 104
    -109 <= nums[i] <= 109
    -109 <= target <= 109
    Only one valid answer exists.

# Answer

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        // understood that need to check all two possible combinations
        // Ex: if array has 4 values then possible combinations as follows.
            // (0,1) (1,2) (2,3) (3,0) (3,1)
        // results will be out put as an array
        int[] res= new int[2];

        // alternative way:
        for(int i=0;i<nums.length;i++){
            for(int j=0;j<nums.length;j++){
                if(i==j){
                    continue;
                }
                if(target-nums[i]==nums[j])
                {
                    res[0]=i;
                    res[1]=j;
                    break;
                }
            }
        }

       return res;
}
}


```
