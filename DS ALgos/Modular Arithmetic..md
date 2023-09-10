


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

## Properties of Modular arthamatic 
#modulerArthamaticProperties
1) $(a+b)\%m = (a\%m + b\%m)$