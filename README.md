# leetcode

[ Shuffle the Array](https://leetcode.com/problems/shuffle-the-array/description/)

    public int[] shuffle(int[] nums, int n) {
  		int[] ans = new int[nums.length];
  		int index = 0;
  
  		for (int i = 0; i < n; i++) {
  			ans[index++] = nums[i];
  			ans[index++] = nums[i + n];
  		}
  		return ans;
  	}
