Greatest Common devisor 

#GCD #GreatestCommonDevisor

Brute force 
```run-cpp 
#include<iostream> 

class sol{ 
public: 
   static int GCD ( int a , int b){
	   for(int i = std::min(a,b); i>=1 ;i--){
	   if(a%i==0)
		   return i; 
	   }
	   return -1;
   }
};

std::cout<<sol::GCD(25,15);

```

Properties of GCS 
	1) GCD(a,b) = GCD(b,a)
	2) GCD(0,a) = a
	3) GDC(1,a) = 1
	4) GCD(a,b-a) = gcd(a,b) where (b>a)
	5) GCD(a,b) = GCD(a, b%a) where (b>a)