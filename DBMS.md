X|Y|X
---|---|---
1|4|2
1|5|3
1|6|3
3|2|2

1. xy -> z && Z -> X     not hold good  
2. yz -> x && y -> Z     hold good
3. yz -> X && Y -> Z     not hold good  
4. XZ -> Y && Y -> Z     not hold good  

A|B|C
---|---|---
1|2|4
3|5|4
3|7|2
1|4|2

1. A -> B && BC -> A    not hold good  
2. C -> b && CA -> B    not hold good  
3. B -> C && AB -> C    hold good  
4. A -> C && BC -> A    not hold good  

####Attribute Closure
(F+)
    R(A B C)  
    A -> B  
    B -> C  
->(A+) = A B C  
   (B+)=BC  
   (C+)=c  
   
   R(A B C D E F)  
   A + B  
   C + DE  
   AC + F  
   D + AF  
   E + CF  
   
   (A+)=AB  
   (D+)=DAF  
        DABF  
   (E+)=ECF 
   (DE+)= DABFCE
   
   