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

[Final Value of Variable After Performing Operations](https://leetcode.com/problems/final-value-of-variable-after-performing-operations/description/)

    public int finalValueAfterOperations(String[] operations) {
		int num = 0;
		for (String o : operations) {
			num += (44 - o.charAt(1));
		}
		return num;
	}
