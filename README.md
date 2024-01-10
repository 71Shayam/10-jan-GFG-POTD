	int longSubarrWthSumDivByK(int arr[], int n, int k)
	{
	    int sum = 0;
	    unordered_map<int,int> mp;//we use map to store remainders
	    mp[0] = n;
	    
	    int ans = 0;
	    
	    for(int i = n - 1; i > -1; i--){
	        sum = (sum + (arr[i] % k) + k) % k;
	        
	        if(!mp.count(sum))
	            mp[sum] = i;//update
	        else
	            ans = max(ans, mp[sum] - i);
	    }
	    
	    return ans;
	}
