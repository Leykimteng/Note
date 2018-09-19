#### Why do we hate public speaking

#### Public Speaking Anxiety

#### Transaction Management  
- Transaction - collection of operation that from a Single Logical limit of work are call Transaction.  
- All Transaction start with begin keyword and end with End keeyword  
##### Atomicity Either or None of step is executed  
##### Databox 
- must take special action to ensure that transaction operates properly wothout interference from Concurrently execute database statement. __This property is know as _Isolation___  
- After Transaction executed successfully if System get crushed then also transaction must persist. This property know as durability.  
Read(x): Which Tranfer the data x from the database to a variable, also called as x, in a buffer in main memory belonging to Transaction that executes the sead operation.  
Write(x): Which Tranfer the value in the variable x in the main memory buffer of the traansaction, that execute the write of the data item X in the database.  
