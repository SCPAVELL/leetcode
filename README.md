# leetcode

[ Shuffle the Array](https://leetcode.com/problems/shuffle-the-array/description/)

    public int[] shuffle(int[] nums, int n) {
  		int[] ans = new int[nums.length];
  		int index = 0;
  		for (int i = 0; i < n; i++) {
  			ans[index++] = nums[i];
  			ans[index++] = nums[i + n];     }
  		return ans;       }

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
		}return time;
	}

 

[2006. Count Number of Pairs With Absolute Difference K](https://leetcode.com/problems/count-number-of-pairs-with-absolute-difference-k/description/)

	public int countKDifference(int[] nums, int k) {
		int count = 0;
		for (int i = 0; i < nums.length; i++) {
			for (int j = i + 1; j < nums.length; j++) {
				if ((Math.abs(nums[i] - nums[j])) == k) {
					count++;
				}
			}
		}
		return count;
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
	        } return sum;}


[1828. Queries on Number of Points Inside a Circle](https://leetcode.com/problems/queries-on-number-of-points-inside-a-circle/description/)

	public int[] countPoints(int[][] points, int[][] queries) {
		int[] nums = new int[queries.length];
		int count;
		for (int i = 0; i < queries.length; i++) {
			count = 0;
			for (int j = 0; j < points.length; j++) {
				if ((queries[i][0] - points[j][0]) * (queries[i][0] - points[j][0]) + (queries[i][1] - points[j][1])
						* (queries[i][1] - points[j][1]) <= queries[i][2] * queries[i][2])
					count++;
			}
			nums[i] = count;
		}	return nums;	}


[807. Max Increase to Keep City Skyline](https://leetcode.com/problems/max-increase-to-keep-city-skyline/description/)

	public int maxIncreaseKeepingSkyline(int[][] grid) {
		int n = grid.length;
		int arr1[] = new int[n];
		int arr2[] = new int[n];

		for (int i = 0; i < n; i++) {
			for (int j = 0; j < n; j++) {
				if (arr2[i] < grid[i][j])
					arr2[i] = grid[i][j];
				if (arr1[j] < grid[i][j])
					arr1[j] = grid[i][j];
			}
		}

		int ans = 0;
		int m = 0;

		for (int i = 0; i < n; i++) {
			for (int j = 0; j < n; j++) {
				m = Math.min(arr2[i], arr1[j]);
				if (grid[i][j] < m)
					ans += (m - grid[i][j]);
			}
		}

		return ans;}


[1720. Decode XORed Array](https://leetcode.com/problems/decode-xored-array/description/)

	public int[] decode(int[] encoded, int first) {
		int[] arr = new int[encoded.length + 1];
		arr[0] = first;
		for (int i = 1; i < encoded.length + 1; i++) {
			arr[i] = arr[i - 1] ^ encoded[i - 1];
		}
		return arr;}

[654. Maximum Binary Tree](https://leetcode.com/problems/maximum-binary-tree/description/)

	public TreeNode constructMaximumBinaryTree(int[] nums) {

		return constructBinarymax(nums, 0, nums.length - 1);
	}

	public TreeNode constructBinarymax(int[] nums, int start, int end) {
		if (start > end) {
			return null;
		}
		int position = maxroot(nums, start, end);
		TreeNode root = new TreeNode(nums[position]);
		root.left = constructBinarymax(nums, start, position - 1);
		root.right = constructBinarymax(nums, position + 1, end);
		return root;
	}

	public int maxroot(int[] arr, int start, int end) {
		int max = Integer.MIN_VALUE, maxidx = 0;
		for (int i = start; i <= end; i++) {
			if (max < arr[i]) {
				max = arr[i];
				maxidx = i;
			}
		}
		return maxidx;
	}


[2574. Left and Right Sum Differences](https://leetcode.com/problems/left-and-right-sum-differences/description/)

	public int[] leftRightDifference(int[] nums) {
		int left = 0;
		for (int i = 0; i < nums.length; i++) {
			left += nums[i];
		}
		int right = 0;
		int arr[] = new int[nums.length];
		for (int i = 0; i < nums.length; i++) {
			left -= nums[i];
			arr[i] = Math.abs(right - left);
			right += nums[i];
		}
		return arr;
	}

[1389. Create Target Array in the Given Order](https://leetcode.com/problems/create-target-array-in-the-given-order/description/)


	 public int[] createTargetArray(int[] nums, int[] index) {
			List<Integer> arr = new ArrayList<Integer>();
			int[] ans = new int[nums.length];
	
			for (int i = 0; i < nums.length; i++) {
				arr.add(index[i], nums[i]);
			}
			for (int j = 0; j < arr.size(); j++) {
				ans[j] = arr.get(j);
			}
			return ans;
	
		}

[1313. Decompress Run-Length Encoded List](https://leetcode.com/problems/decompress-run-length-encoded-list/description/)

	public int[] decompressRLElist(int[] nums) {
		int k = 0;

		for (int i = 0; i < nums.length; i += 2) {
			k += nums[i];
		}

		int[] arr = new int[k];

		int x = 0;
		for (int i = 0; i < nums.length; i += 2) {
			for (int j = 0; j < nums[i]; j++) {
				arr[x++] = nums[i + 1];
			}
		}
		return arr;
	}


[1431. Kids With the Greatest Number of Candies](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/description/)

	public List<Boolean> kidsWithCandies(int[] candies, int extraCandies) {
		List<Boolean> result = new ArrayList<>();
		int maxCandies = 0;
		for (int candy : candies) {
			maxCandies = Math.max(maxCandies, candy);
		}

		for (int i = 0; i < candies.length; i++) {
			result.add(candies[i] + extraCandies >= maxCandies);
		}

		return result;
	}


[1662. Check If Two String Arrays are Equivalent](https://leetcode.com/problems/check-if-two-string-arrays-are-equivalent/description/)

	public boolean arrayStringsAreEqual(String[] word1, String[] word2) {
		String combined1 = String.join("", word1);
		String combined2 = String.join("", word2);
		return combined1.equals(combined2);
	}


[2535. Difference Between Element Sum and Digit Sum of an Array](https://leetcode.com/problems/difference-between-element-sum-and-digit-sum-of-an-array/description/)


	public int differenceOfSum(int[] nums) {
		int sum = 0;
		int digitSum = 0;
		
		for (int i : nums) {
			sum += i;
			
			while (i > 0) {
				digitSum += i % 10;
				i = i / 10;
			}
		}
		return Math.abs(sum - digitSum);
	}

[20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)


		 public boolean isValid(String s) {
		    Stack<Character> stack = new Stack<Character>();
		        for (char c : s.toCharArray()) { 
		            if (c == '(') 
		                stack.push(')'); 
		            else if (c == '{') 
		                stack.push('}'); 
		            else if (c == '[') 
		                stack.push(']'); 
		            else if (stack.isEmpty() || stack.pop() != c) 
		                return false;
		        }
		        return stack.isEmpty();
		    }


[1021. Remove Outermost Parentheses](https://leetcode.com/problems/remove-outermost-parentheses/description/)

	
	      public String removeOuterParentheses(String s) {
	        int count = 0;
	        StringBuilder result = new StringBuilder();
	
	        for (char c : s.toCharArray()) {
	            if (c == '(') {
	                if (count != 0) {
	                    result.append(c);
	                }
	                count++;
	            } else {
	                if (count != 1) {
	                    result.append(c);
	                }
	                count--;
	            }
	        }
	
	        return result.toString();
	    }


[561. Array Partition](https://leetcode.com/problems/array-partition/description/)

		public int arrayPairSum(int[] nums) {
	        int max = 0;
	        Arrays.sort(nums);
	        for(int i = 0;i<nums.length;i = i+2){
	            max = max + Math.min(nums[i],nums[i+1]);
	        }
	        return max;
	    }


[1160. Find Words That Can Be Formed by Characters](https://leetcode.com/problems/find-words-that-can-be-formed-by-characters/description/)

	      public int countCharacters(String[] words, String chars) {
	         HashMap<Character, Integer> myMap = new HashMap<>();
	      int res = 0;
	        
	      for(char ch : chars.toCharArray())
	          myMap.put(ch, myMap.getOrDefault(ch, 0) + 1);
	      
	      for(String word: words)
	      {
	          HashMap<Character, Integer> count = new HashMap<>();
	          int i = 0;
	          
	          for(; i < word.length(); i++)
	          {
	              char ch = word.charAt(i);
	              
	              if(myMap.containsKey(ch)) {
	                  if(count.containsKey(ch) && count.get(ch) + 1 > myMap.get(ch))
	                      break;
	                  count.put(ch, count.getOrDefault(ch, 0) + 1);
	              } else
	                  break;
	          } if(i == word.length())
	              res += word.length();
	      }
	      
	      return res;
	    }



[349. Intersection of Two Arrays](https://github.com/SurikovDA/Automation-of-accounting/blob/main/src/MonthlyReport.java)

		public int[] intersection(int[] nums1, int[] nums2) {
	         HashSet<Integer> set1 = new HashSet<>();
	        HashSet<Integer> set2 = new HashSet<>();
	
	        for (int n : nums1) {
	            set1.add(n);
	        }
	
	        for (int n : nums2) {
	            if (set1.contains(n))
	                set2.add(n);
	        }
	
	        int [] result = new int[set2.size()];
	            int index = 0;
	        for (int n : set2){
	            result[index++] = n;
	        }
	        return result;
	    }



[350. Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/description/)


	 public int[] intersect(int[] nums1, int[] nums2) {
	        Arrays.sort(nums1);
		Arrays.sort(nums2);
		int top = 0;
		int bottom = 0;
		List<Integer> h = new ArrayList<>();
	
		while (true){
			if (top >= nums1.length || bottom >= nums2.length){
				break;
			}
			if (nums1[top] == nums2[bottom]){
				h.add(nums1[top]);
				top ++;
				bottom ++;
			}else if (nums1[top] < nums2[bottom]){
				top ++;
			}else if (nums1[top] > nums2[bottom]){
				bottom ++;
			}
		}
	
		int[] g = new int[h.size()];
		for (int i = 0; i < h.size(); i++) {
			g[i] = h.get(i);
		}
		return g;
	    }


[2325. Decode the Message](https://leetcode.com/problems/decode-the-message/description/)


	public String decodeMessage(String key, String message) {
		StringBuilder ans = new StringBuilder();// Using String Builder to append the string
		key = key.replaceAll(" ", "");
		// Removing the spaces
		HashMap<Character, Character> letters = new HashMap<>();
		// Mapping the key into a hashmap.
		char original = 'a';
		for (int i = 0; i < key.length(); i++) {
			if (!letters.containsKey(key.charAt(i))) {
				letters.put(key.charAt(i), original++);
			}
		}
		
		for (int i = 0; i < message.length(); i++) {
			if (letters.containsKey(message.charAt(i))) {
				// Now replacing the letters of the message with appropriate letter according to
				// the key
				ans.append(letters.get(message.charAt(i)));
			} else {
				ans.append(message.charAt(i));
				// This is for characters other than the letters in the key example a space " "
				// They will not be replaced by any letters hence original letter is appended
				// into the StringBuilder
			}
		}
		return ans.toString();
	}



[2309. Greatest English Letter in Upper and Lower Case](https://leetcode.com/problems/greatest-english-letter-in-upper-and-lower-case/description/)

	public String greatestLetter(String s) {
	        boolean[] seen = new boolean[58];
	        for(char ch : s.toCharArray()){
	            seen[ch-65]=true;
	        }
	        for(int i=57; i>31;i--){
	            if(seen[i] && seen[i-32])
	                return (char)(i+33)+"";
	        }
	        return "";
	    }
 

[2506. Count Pairs Of Similar Strings](https://leetcode.com/problems/count-pairs-of-similar-strings/description/)

	 public int similarPairs(String[] words) {
	       Map<Integer, Integer> group = new HashMap<>();
		for (String word : words) {
			group.merge(convert(word), 1, Integer::sum);
		}

		int count = 0;
		for (int value : group.values()) {
			count += value * (value - 1) / 2;
		}

		return count;
	}

	private int convert(String word) {
		int n = 0;
		for (char c : word.toCharArray()) {
			n |= 1 << (c - 'a');
		}

		return n;
	}


[2824. Count Pairs Whose Sum is Less than Target](https://leetcode.com/problems/count-pairs-whose-sum-is-less-than-target/description/)

		public int countPairs(List<Integer> nums, int target) {
			int count = 0;
			for (int i = 0; i < nums.size(); i++) {
				for (int j = i + 1; j < nums.size(); j++) {
					if (nums.get(i) + nums.get(j) < target)
						count++;
				}
			}
			return count;
	
		}

[1816. Truncate Sentence](https://leetcode.com/problems/truncate-sentence/description/)

	public String truncateSentence(String s, int k) {
		String[] sp = s.split(" ");
		String print = "";

		for (int i = 0; i < k; i++) {
			print += " " + sp[i];
		}
		return print.trim();
	}



[2367. Number of Arithmetic Triplets](https://leetcode.com/problems/number-of-arithmetic-triplets/description/)

	public int arithmeticTriplets(int[] nums, int diff) {
		int count = 0;
		for (int i = 0; i < nums.length - 2; i++) {
			for (int j = i + 1; j < nums.length - 1; j++) {
				for (int k = j + 1; k < nums.length; k++) {
					if (nums[k] - nums[j] == diff && nums[j] - nums[i] == diff) {
						count++;
					}
				}
			}
		}

		return count;
	}


[1732. Find the Highest Altitude](https://leetcode.com/problems/find-the-highest-altitude/description/)

	 public int largestAltitude(int[] gain) {
		int max = 0;
		int sum = 0;

		for (int i = 0; i < gain.length; i++) {
			sum += gain[i];
			max = Math.max(max, sum);
		}
		return max;
	}

[2037. Minimum Number of Moves to Seat Everyone](https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/description/)

 	public int minMovesToSeat(int[] seats, int[] students) {
		Arrays.sort(seats);
		Arrays.sort(students);
		int count = 0;
		for (int i = 0; i < seats.length; i++) {
			count += Math.abs(seats[i] - students[i]);
		}
		return count;
	}


[136. Single Number](https://leetcode.com/problems/single-number/description/)

 	public int singleNumber(int[] nums) {
		Map<Integer, Integer> map = new HashMap<>();
		for (int num : nums) {
			map.put(num, map.getOrDefault(num, 0) + 1);
		}

		for (int num : map.keySet()) {
			if (map.get(num) == 1) {
				return num;
			}
		}

		return 0;
	}


[268. Missing Number](https://leetcode.com/problems/missing-number/description/)

	 public int singleNumber(int[] nums) {
		int n = nums.length;
		int sum = n * (n + 1) / 2;
		for (int i : nums) {
			sum -= i;
		}
		return sum;
	}

[860. Lemonade Change](https://leetcode.com/problems/lemonade-change/description/)

	public boolean lemonadeChange(int[] bills) {
		int five = 0, ten = 0;
		for (int i : bills) {
			if (i == 5)
				five++;
			else if (i == 10) {
				five--;
				ten++;
			} else if (ten > 0 && five >= 1) {
				ten--;
				five--;
			} else
				five -= 3;
			if (five < 0)
				return false;
		}
		return true;
	}



[2760. Longest Even Odd Subarray With Threshold](https://leetcode.com/problems/longest-even-odd-subarray-with-threshold/description/)

	public int longestAlternatingSubarray(int[] nums, int threshold) {
	        int ans = 0;
	        int n = nums.length;
	        for(int i=0; i<n; i++) {
	            if(nums[i]%2==0 && nums[i]<=threshold) {
	                int e = i+1;
	                while(e<n && nums[e]<=threshold && nums[e]%2!=nums[e-1]%2){
	                    e++;
	                }
	                ans = Math.max(ans, e-i);
	            }
	        }
	       	 return ans;
	    }


[1848. Minimum Distance to the Target Element](https://leetcode.com/problems/minimum-distance-to-the-target-element/description/)

	public int getMinDistance(int[] nums, int target, int start) {
		int ans = Integer.MAX_VALUE;

		for (int i = 0; i < nums.length; ++i) {
			if (nums[i] == target) {
				ans = Math.min(ans, Math.abs(i - start));
			}
		}
		return ans;
	}


[2859. Sum of Values at Indices With K Set Bits](https://leetcode.com/problems/sum-of-values-at-indices-with-k-set-bits/description/)

	public int sumIndicesWithKSetBits(List<Integer> nums, int k) {
		int sum = 0;
		for (int i = 0; i < nums.size(); i++) {
			if (Integer.bitCount(i) == k) {
				sum += nums.get(i);
			}
		}

		return sum;
	}


[804. Unique Morse Code Words](https://leetcode.com/problems/unique-morse-code-words/description/)


	public int uniqueMorseRepresentations(String[] words) {
		String[] codes = new String[] { ".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....", "..", ".---", "-.-",
				".-..", "--", "-.", "---", ".--.", "--.-", ".-.", "...", "-", "..-", "...-", ".--", "-..-", "-.--",
				"--.." };
		Set<String> s = new HashSet<>();
		for (String word : words) {
			StringBuilder t = new StringBuilder();
			for (char c : word.toCharArray()) {
				t.append(codes[c - 'a']);
			}
			s.add(t.toString());
		}
		return s.size();
	}


[2176. Count Equal and Divisible Pairs in an Array](https://leetcode.com/problems/count-equal-and-divisible-pairs-in-an-array/description/)

	public int countPairs(int[] nums, int k) {
		int count = 0;
		int sum = 0;
		for (int i = 0; i < nums.length; i++) {
			for (int j = i + 1; j < nums.length; j++) {
				if (nums[i] == nums[j]) {
					sum = i * j;
					if (sum % k == 0) {
						count++;
					}
				}
			}
		}
		return count;
	}

[1464. Maximum Product of Two Elements in an Array](https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/description/)

	public int maxProduct(int[] nums) {
		Arrays.sort(nums);
		return (nums[nums.length - 2] - 1) * (nums[nums.length - 1] - 1);
	}


[1684. Count the Number of Consistent Strings](https://leetcode.com/problems/count-the-number-of-consistent-strings/description/)


	public int countConsistentStrings(String allowed, String[] words) {
		HashSet<Character> set = new HashSet<>();
		for (char ch : allowed.toCharArray()) {
			set.add(ch);
		}
		int count = 0;
		for (String str : words) {
			int i = 0;
			for (char ch : str.toCharArray()) {
				if (!set.contains(ch))
					break;
				i++;
			}
			if (i == str.length())
				count++;
		}
		return count;
	}


[1832. Check if the Sentence Is Pangram](https://leetcode.com/problems/check-if-the-sentence-is-pangram/description/)

	public boolean checkIfPangram(String sentence) {
		HashMap<Character, Integer> map = new HashMap<>();
		for (int i = 0; i < sentence.length(); i++) {
			map.put(sentence.charAt(i), 0);
			if (map.size() == 26) {
				return true;
			}
		}
		return false;
	}


[2657. Find the Prefix Common Array of Two Arrays](https://leetcode.com/problems/find-the-prefix-common-array-of-two-arrays/description/)

	public int[] findThePrefixCommonArray(int[] A, int[] B) {
		Set<Integer> set = new HashSet<Integer>();
		int[] ans = new int[A.length];
		for (int i = 0; i < ans.length; i++) {
			set.add(A[i]);
			set.add(B[i]);
			ans[i] = 2 * (i + 1) - set.size();
		}
		return ans;
	}


[1748. Sum of Unique Elements](https://leetcode.com/problems/sum-of-unique-elements/description/)

	 public int sumOfUnique(int[] nums) {
		Map<Integer, Integer> map = new HashMap<Integer, Integer>();
		for (int num : nums) {
			map.put(num, map.getOrDefault(num, 0) + 1);
		}

		int sum = 0;
		for (int key : map.keySet()) {
			if (map.get(key) == 1) {
				sum += key;
			}
		}
		return sum;
	}

[387. First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/description/)

	public int firstUniqChar(String s) {
		for (int i = 0; i < s.length(); i++) {
			int c = s.charAt(i);
			if (i == s.lastIndexOf(c) && i == s.indexOf(c)) {
				return i;
			}
		}

		return -1;
	}



[1436. Destination City](https://leetcode.com/problems/destination-city/description/)

	public String destCity(List<List<String>> paths) {
	        Set<String> startPoints = new HashSet<>();
	        for(List<String> path : paths){
	            startPoints.add(path.get(0));
	        }
	        String res = null;
	 
	        for(List<String> path : paths){
	            if(!startPoints.contains(path.get(1))){
	                res = path.get(1);
	                break;
	            }
	        }
	        return res;
	    }
