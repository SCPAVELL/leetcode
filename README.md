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

[Number of Employees Who Met the Target](https://leetcode.com/problems/number-of-employees-who-met-the-target/description/)

	public int numberOfEmployeesWhoMetTarget(int[] hours, int target) {
		int time = 0;
		for (int num : hours) {
			if (num >= target) {
				time += 1;
			}
		}
		return time;
	}


[1480. Running Sum of 1d Array](https://leetcode.com/problems/running-sum-of-1d-array/)

	public int[] runningSum(int[] nums) {
		int[] ans = new int[nums.length];
		ans[0] = nums[0];

		for (int i = 1; i < nums.length; i++) {
			ans[i] = nums[i] + ans[i - 1];
		}
		return ans;
	}


[2114. Maximum Number of Words Found in Sentences](https://leetcode.com/problems/maximum-number-of-words-found-in-sentences/description/)

	public int mostWordsFound(String[] sentences) {
		int count = 0;
		for (String sentence : sentences) {
			count = Math.max(count, sentence.split(" ").length);
		}
		return count;
	}

[771. Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/description/)

	public int numJewelsInStones(String jewels, String stones) {
		HashMap<Character, Integer> map = new HashMap<>();
		for (Character i : stones.toCharArray()) {
			map.put(i, map.getOrDefault(i, 0) + 1);
		}
		int sum = 0;
		for (Character i : jewels.toCharArray()) {
			if (map.get(i) != null)
				sum += map.get(i);
		}

		return sum;
	}

[1672. Richest Customer Wealth](https://leetcode.com/problems/richest-customer-wealth/description/)

	public int maximumWealth(int[][] accounts) {
		int maxSum = Integer.MIN_VALUE;
        for (int i = 0; i < accounts.length; i++) {
            int sum = 0;
            for (int j = 0; j < accounts[i].length; j++) {
                sum += accounts[i][j];
            }
            maxSum = Math.max(maxSum, sum);
        }
        return maxSum;
	}

[1528. Shuffle String](https://leetcode.com/problems/shuffle-string/description/)

	public String restoreString(String s, int[] indices) {
		char[] ans = new char[indices.length];
		for (int i = 0; i < indices.length; ++i) {
			ans[indices[i]] = s.charAt(i);
		}
		return String.valueOf(ans);
	}


[1588. Sum of All Odd Length Subarrays](https://leetcode.com/problems/sum-of-all-odd-length-subarrays/description/)

	public int sumOddLengthSubarrays(int[] arr) {
	        int N = arr.length;
	        int[] PS = new int[N];
	        PS[0] = arr[0];
	        for(int i=1; i<N; i++){
	            PS[i] = arr[i] + PS[i-1];
	        }
	
	        int sum = PS[N-1];
	        for(int len=3; len<=N; len+=2){
	            sum += PS[len-1];
	            for(int i=len; i<N; i++){
	                sum += PS[i] - PS[i - len];
	            }
	        }
	        return sum;
	    }

