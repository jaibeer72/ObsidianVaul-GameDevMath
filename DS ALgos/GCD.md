Greatest Common devisor 

#GCD #GreatestCommonDevisor

Brute force 
```cpp 
#include<iostream> 

class sol{ 
public: 
   static int GCD ( int a , int b){
	   for(int i = std::min(a,b); i>=1 ;i--){
	   if(a%i==0)
		   return i; 
	   }
   }
}

std::cout<<sol::GCD(25,)

```

Properties of GCS 
	1) GCD(a,b) = GCD(b,a)
	2) GCD(0,a) = a
	3) GDC(1,a) = 1