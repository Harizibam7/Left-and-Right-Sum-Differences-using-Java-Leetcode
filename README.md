# Left-and-Right-Sum-Differences-using-Java-Leetcode

    class Solution {
        public int[] leftRightDifference(int[] nums) {
            int n = nums.length;
            int leftSum[] = new int[nums.length];
            int rightSum[] = new int[nums.length];
            int answer[] = new int[nums.length];
            leftSum[0]=0;
            rightSum[n-1] = 0;
            for(int i =1; i< nums.length;i++){
                leftSum[i] = leftSum[i-1]+nums[i-1];
            }
            for(int j = n-2;j>=0;j--){
                rightSum[j] = rightSum[j+1]+nums[j+1]; 
            }
            for(int k = 0;k<n;k++){
                answer[k] = Math.abs(leftSum[k]-rightSum[k]);
            }
            return answer;
        }
    }
