## 3SUM Problem
```cpp
//以某個點為target並用雙指針2SUM Problem的方式去做
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        int n = nums.size();
        vector<vector<int>> ans;
        map<int,int> mp;
        for(int i = 0 ; i < n ; i++){
            int target = -nums[i];
            if(mp[target]) continue;
            mp[target] = 1;
            int left = i + 1;
            int right = n - 1;
            while(left < right){
                if(left <= i || right <= i + 1) break;
                if(nums[left] + nums[right] == target){
                    int flag = 0;
                    vector<int> tmp = {nums[i],nums[left],nums[right]};
                    for(int k = 0 ; k < ans.size() ; k++){
                        if(ans[k][0] == nums[i] && ans[k][1] == nums[left] && ans[k][2] == nums[right]){
                            flag = 1;
                            break;
                        }
                    }
                    if(!flag) ans.push_back(tmp);
                    right--;
                }
                else if(nums[left] + nums[right] > target){
                    right--;
                }
                else{
                    left++;
                }
            }
        }
        return ans;
    }
};
```
