# Third-Maximum-Number
First Try
public class Solution {
    public int thirdMax(int[] nums) {
        if (nums.length==2){
            if(nums[0]<nums[1]){
                return nums[1];
            }
            else return nums[0];
        }
        if (nums.length==1){
            return nums[0];
        }
        int[] threeNums= {nums[0],nums[1],nums[2]};
        Arrays.sort(threeNums);
        for(int i=3;i<nums.length;i++){
            if (nums[i]==threeNums[0]||nums[i]==threeNums[1]||nums[i]==threeNums[2]){
            continue;
            }
            else if (nums[i]>threeNums[0]){
                threeNums[0]=nums[i];
                Arrays.sort(threeNums);
            }
            else if(nums[i]<threeNums[0]&&threeNums[0]==threeNums[1]){
                threeNums[0]=nums[i];
                Arrays.sort(threeNums);
            }
            else if(nums[i]<threeNums[0]&&threeNums[1]==threeNums[2]){
                threeNums[1]=nums[i];
                Arrays.sort(threeNums);
            }
            
        }
        
        if(threeNums[2]>threeNums[1]&&threeNums[1]>threeNums[0]){
            return threeNums[0];
        }
        else return threeNums[2];
        
    }
}
