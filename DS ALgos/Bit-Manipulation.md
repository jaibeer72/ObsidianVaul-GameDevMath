now we have a problme where a number appears 3 times except one in an array which appers only 2 times. 

so let's write an algorithm for that 
#bitmanipulation #repeatedNumbers 
```run-cpp
#include<vector> 
#include<iostream>
using namespace std; 

vector<int> test = {1,2,1,3,1,2,2,3,4}

class Solution{
public: 
	int sol(vector<int> t){
		int ones =0 , two=0 , three=0; 
		for(int i =0; i<t.size(); i++){
			// keeping track of twos by tracking if the bit exists 
			two |= ones & t[i]; // or will keep it active and will check if the bit is activated. 
			ones ^= t[i]; // toggle on and off for the intiger
			three = ones & two; // keeps track of it if it occurs 3 times 
			// clear using complament if it occurs 3 times 
			ones &= ~three; 
			two &= ~three;  
		}
		return ones;
	}
};

Solution so; 
cout<< so.sol(test); 
```

