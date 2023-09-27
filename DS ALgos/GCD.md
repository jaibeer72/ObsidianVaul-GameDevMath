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
	6) GCD(a,b) = GCD(b%a,a)
	7) GCD(a,b,c) = GCD(GCD(a,b),C)

a backtrcking algo for GCD and LCM 
#LCM #LowestCommonMultiple 
```run-cpp 
#include<iostream>

class sol{ 
public: 
	static int gcd(int a, int b){ 
		if(b < a) std::swap(a, b); 
		if(a == 0) return b; 
		return gcd(b % a, a); 
	} 
	static long long lcm(int a, int b){
	return (long long) (a * b) / gcd(a, b); 
	} 
};


std::cout<<sol::lcm(25,15); 

```

$$LCM(a,b)=\frac{a \cdot b}{GCD(a,b)}
$$
