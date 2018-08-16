X|Y|X
---|---|---
1|4|2
1|5|3
1|6|3
3|2|2

1. xy → z && Z → X     not hold good  
2. yz → x && y → Z     hold good
3. yz → X && Y → Z     not hold good  
4. XZ → Y && Y → Z     not hold good  

A|B|C
---|---|---
1|2|4
3|5|4
3|7|2
1|4|2

1. A → B && BC → A    not hold good  
2. C → b && CA → B    not hold good  
3. B → C && AB → C    hold good  
4. A → C && BC → A    not hold good  

#### Attribute Closure
(F+)
    R(A B C)  
    A → B  
    B → C  
→(A+) = A B C  
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
   
   
#### Axioms % 
1. if y ⊆ x then x → y
2. x → y , x → yz
3. if x → y && y → z
            x→y
4. if x → y && x → y
        x → YZ
5. if x → yz && x → z
    x → Y && X → Z
6. if x → y && z → w  
      xz → yw    
      x → y   
     #### `ZX → ZY`    
      z → w   
     #### `Zx → wX`  
     #### `XZ → ZYWX`  
      XZ → WY
      
#### Normalization
 It is a process of analysis given selection schema based on their Functional Dependency and primary keys to archieve properties of minimizing the redundancy and minimizing the insertion , deletion and update anomaly.  
 
 R(Name, Course, Mobile, Subject, Professor, Grade)  
 Key = {name, Course}  
 F.O = {Name → Mobile  
        Name → Subject  
        Course → Professor  
        }  
        
 Redundancy is the repeat of extra information.
 
 Why do we need normalization?  
 Example   
 
 Name|Course|Mobile
 ---|---|---
 A|Java|0123456
 A|DBMS|0123456
 
 * Update if you change the Number it will change only the nuber of one subject
 * Insertion unable to insert because of some constrain
 * Deletion if a table have only one tuple and you delete that tuple everything will be delete  
 
 #### First Normal Form
 A relation R in 1NF , If the value in the domain of each attribute of the relation are atomic or only one value is associated with each attribute and the value if not a set of value or list of values.  
 
 e.No|Ename|Contact
  ---|---|---
  1 | A|{98,99}
  2|B|{96,97}
   # ↓↓↓↓↓↓↓↓
  
   e.No|Ename|Contact
    ---|---|---
    1 | A|98
    1 | A|99
    2|B|96
    2|B|97
    
 #### Second Normal Form 
 __Full funchimal Dependency__  
  A relation R is said to be in 2NF, If it is in 1NF & if every non-prime attribute of R is Fully Functional Dependent on the key of R or No Non-Prime Attributes should be determine by the part of the candidate key.  
  R(___A,B___,C,D)  (__Bold__ = Primary key)  
    AB → C  
    AB → D  
    
 Example R(A B C D)  
 ABC → D  
 AB → CD  
 A → BCD  
 
 (ABC+) = ABCD  
 (AC+) = ABCD  
 (A+) = ABCD  
 Key is uniquely identify a tuple in a relation  
 
 If i delete some attribute   
 If there are no problem subtitiute of the key then key is known C.K(Minimal Super Key or candidate key)  
 Example R(A B C D)  
 B→ACD  
 ACD→B  
 
 (B+)= BACD  
 (ACD+) =ACDB  
  both can be superkey base on the sinario  
  
  Example R(A B C D)  
  AB → CD  
  D → A  
  _______  
  ↓     |  
  A B C D  
  | | ↑ ↑  
  ------  
  
  (AB+) = ABCD  
  (D+) = DAC
  (BC+)= BC
  (DB+) = DABC  
  