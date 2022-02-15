# LEETCODE day 01

## Problem Description

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

Example 1:

Input: nums = [2,2,1]
Output: 1
Example 2:

Input: nums = [4,1,2,1,2]
Output: 4
Example 3:

Input: nums = [1]
Output: 1

Constraints:

1 <= nums.length <= 3 _ 104
-3 _ 104 <= nums[i] <= 3 \* 104
Each element in the array appears twice except for one element which appears only once.

## Knowledge gained.

    1. Since problem is asking for a linear solution ,cannot use more than one for loop.
    2.Since space should be constant, cannot use a hashset/hashmap to solve the problem. (ESY: use to computeifpresent)
    3. The solution is to use the XOR , because xor returns 0 for similar values:
        1. 1^1=0
        2. 0^0=0
        3. 1^0=1
        4. 0^1=1

## Code

```java
    class Solution {
    public int singleNumber(int[] nums) {
       int c=0; //c will be the result.
        for(int i=0;i<nums.length;i++){
            c^=nums[i];
            }

        return c;

         }

        }

```

## Alternative solution

```java
class Solution {
    public int singleNumber(int[] nums) {
        int result=0;
       HashSet<Integer> set = new HashSet();
        for( int i=0;i<nums.length;i++){
            if(set.contains(nums[i])){
                set.remove(nums[i]);
            }else{
                set.add(nums[i]);
            }
        }
        Object[] arr = set.toArray();
       int i= (Integer) arr[0];
        result= i;
        return result;


}
}


```
