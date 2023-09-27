


okay the range $a\%M =$\{0--$(M-1)$\} 
so the remainder < M 
so for problem-solving purposes the % will remain this was even though different languages deal it with different ways. 

## Given A & B find any integer $M$ such that $A\%M = B\%M$
#modulerArthamatic

so we know 
$A\%M = B\%M$
- now! we know that the number will range between 0-M;

so 
$A\% M = 0 ->(M-1)$

similarly 
$B\% M = 0 -> (M-1)$

now both of them have a similar concept so we can say congurence 

$A\cong{B} \rightarrow A\%M = B\%M$

so we can write $A = B-B+A$
$A = B-(B-A)$
MATH IS WIERD, man 
so now we can rewrite the above by $\%M \rightarrow OBS$


$$
A\%M \rightarrow (B-(B-A)) \% M \rightarrow B\%M -(B-A)\%M
$$

so now let's try and make $B-A$ needs to become 0 and the M that will do that itself 

so abs(B-A) is the answer. 

## Properties of Modular arithmetic
#modulerArthamaticProperties
1) $(a+b)\%m = (a\%m + b\%m)\%m$ #modAdditionProp
2) $(a-b)\% m = ((a\%m-b\%m)+m)\%m$ (because negation can become 0) #modeSubtractionProp
3) $(a*b)\%m = ((a\%m * b\%m))\%m$ #modMultiplicationProp #modProductProp
5) $((a^{b}) \%m = (a\%m)^{b} \%m)$ #modSquareProp #modPowerProp

#fastPower
```run-cpp 
#include <iostream>
#define MOD 1000000007

class Fp{
public: 
	static long long fast_power(long long base , long long pow){
	long long res = 1; 
	while(pow>0)
	{
		if(pow%2 == 1){
			res = (res * base)%MOD;
		}
		base = (base * base)%MOD; 
		pow = pow/2;  
	}
	return res; 
}
};


std::cout<<"Fast power \n"; 
std::cout<<Fp::fast_power(2,5) << std::endl; 

```
