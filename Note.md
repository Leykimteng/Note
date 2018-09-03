# `Scala`
is a functional programming laguage that use concept REPL(Read eval print and loop) and treat every thing as function  

declare variable need to be assign  
Example  
`var myVar1:Int=0`   
**Integer cannot be Null**  
### __*Other* *Variable* *Type*__  

Type|Example
---|---
Float | `var myFloat = 0.0f`  
Double | `var myDouble:Double=3.14`  
Boolean | `myBoolean:Boolean=true`
String | `myString=""`  

### Operator

__Example 1__  
`var res=myInt1+myInt2`  
This will work because myint1 and myInt2 is premitive type but it will not work if it is object  
__Example 2__  
`var res1=myInt1.+(myInt2)`  
This work for all because it use the + method that have the ability of overloading the operator of premitive type or object value  
>`+()` method is the operator overloading
---
### Array  
__How To Declare Array__  
`var arr=Array(1,2,3,4,5)`  
`var arr1 = new Array[Int](5)`  

#### Foreach Method of array
1. For Println each value of array  
`arr1.foreach(println)` or  `arr1.foreach(println(_)`  
this will print each value 
2. for $array name  
 `arr1.foreach(arr1=>println(s"Array=$arr1"))`  
 print array = and each value  
3. Uppercase  
  `arr1.foreach(Uppercase)`  
  print all vaue with all upercase
  ---
#### Filter
what is _?  
`_` = all for all the value in array  
what is filter  
filter is the array method that use to create new array with condition  
example  
`var nums = arr1.filter(_>30)` create new array name nums with value bigger that 30  
---
#### Abstract Class 
* can use abstract __with the Class only__ not within the Class  
* abstract method in scala is simular to Abstract method in java and also can have paramater  
---
#### Trait
__Trait in Scala = interface in java__  
Traits are used to share interfaces and fields(_Variable_) between classes.   
trait method=abstraction of encapsulates method=
* similar to abstract Class
* Can extend more trait with `with` keyword 
* trait class can only implement by only `trait` keyword only  
example `trait Test{}`  
---

#### Object and Class
##### object 
is use to defind the static var and method.  
`static` keyword doesn't support in scala.  
#### Composive Function
is the function that return the value without the return keyword it return the value or object by put it as the last value directly   
Example  
`def addNum(a:Int,b:Int):Int= a+b`

##### class 
is used to create the instance   
#### Case Class
* A case class is similar to any other classes except that it also creates the Companion Object. In addition, a case class will automatically create the apply(),  toString(), hashCode and equals() methods for you.  
* is syntactic sugar for a class that is immutable and decomposable through pattern matching (because they have an apply and unapply methods).   
* Case classes contain a companion object which holds the apply method. This fact makes possible to instantiate a case class without the new keyword. They also come with some helper methods like the .copy method, that eases the creation of a slightly changed copy from the original.
````
case class MyCaseClass(number: Int, text: String, others: List[Int])

val dto = MyCaseClass(3, "text", List.empty)
dto.copy(number = 5) // will produce an instance equal to the original, with number = 5 instead of 3

val dto2 = MyCaseClass(3, "text", List.empty)

dto == dto2 // will return true even if different references

class MyClass(number: Int, text: String, others: List[Int]) {}

val c1 = new MyClass(1, "txt", List.empty)
val c2 = new MyClass(1, "txt", List.empty)

c1 == c2 // will return false because they are different references
````
>__Note__
* You did not have to use the new keyword when creating instances of the Donut case class.
* The case class will automatically create the Companion Object.

##### Class vs Case Class

#### Singleton
Singleton Pattern is a a fairly common design pattern when you need exactly one instance of an object.  
Singleton object is declare like you declare an object
#### Companion Objects
* to access the private var and method of the class and the object both class or trait and obj have to be the same name   
* Both Companoin Class and Object Can access their private fun or variable   
* The Usage of it is for 
Example 
```
class CompanionTest
 {
   private var id = 20                 //non Static
   private var name = "Ratanak"        //non Static
 
   def print(): Unit ={
     println(id+" : "+name)
     println(CompanionTest.id1+" : "+CompanionTest.name1)  //Access the private static var
   }
 }
 
 object CompanionTest
 {
   private var id1=30                 //Static
   private var name1="Chay"           //Static
   import CompanionTest._             //Import but it doesn't need because it auto import
 
   def print1(): Unit =
   {
     val c = new CompanionTest        //create instance of obj
     c.print()
     println(id1+" : "+name1)
     println(c.id+" : "+c.name)  //Access the Instance Private var
   }
 }
  ```
---
#### Lamda Expression
is use to create the function and assign to the var the val variable will become a function  
Syntax  
`val FunName = (parameter) => {}`  
val is Immutable variable aka val is the read only variable and can assign only one
#### Recursive Function
function that call function it self  
Syntax
`def a(i:Int){ a(i-1) }`
#### Nested Function
function inside Function  
Syntax  
`def outer():Unit={ def inner():Unit={...} b()}`  
>___Note___  
The inner function can access only in side the outer function  
The Outer Function can access anywhere  

#### Composive Function
Function that call as the parameter  
syntax
```
def addNum(a:Int,b:Int):Int= return a+b
def subNum(a:Int,b:Int):Int= return a-b
def main(args: Array[String]): Unit = {
    println(addNum(subNum(30,10),subNum(100,50)))
  }
```
#### Currying Function
function that will assign later  
syntax  
```
def test(a:Int) = (b:Int)=> a+b 
main(args Array[String]):Unit={
var a= test(5)(_)      // _ mean any and a is not complete variable
var b= a(10)           // 10 will go to apply _ and b is become the complete value
println(b)}            // Output: 15 
```  
#### Function Signature
is use the function as the parameter by using the lambda expression   
Syntax  
```
def test(a:()=> Unit, other parameter):Unit=
{
a()         //can call function from the parameter
}
```
>___Note___  
The Lambda Function doesn't work with return keyword

#### Closure
Creating or Passing variable in anonymous function of the same scope to another function parameter is call Clouser.  
That can be done only by Lambda Expression.  
```
object MoinObj {
  def main(args: Array[String]): Unit = {
    var name="KimTeng"
    var o = () =>
    {
      print(name)
    }
    var tc = new TestClass
    tc.test2(o)

    name = "\nHongCH"
    tc.test2(o)
  }
}

```
>__Note__  
This is use when you want to pass function like a variable

#### Free variables
The variables that are used in function but are neither local variables nor formal parameters to the function are called free variables.  
Example  
`def fun(m1:Int){// NO USE OF m1
}`
so if the m1 is not use it call Free variable
#### Bound variable
A bound variable is a variable that was previously free, but has been bound to a specific value or set of values.  
Example
`val result = (i:Int) => i * 6`  
>__Note__   
__i__ is bound to a new value each time the result is called.

#### Return Function of Lambda
Lambdo function doesn't need the return keyword to return the value it can pass by only put the value directly.  
example   
* `var a = ()=> return 12 `   
This will show error
* `var a = ()=> 12 `  
This doesn't show error and return value 12
##### How to get the value of lambda expression
* The value of lambda is access by put the parentheses in front of the variable and if that have the parameter just put inside the parentheses and you will get the value from it and the Return type of it is `:String`.    
* if you put only the variable name without parentheses it will return with lambda function like this `:()=>String`  

Example Program   
````
object MoinObj {
  def resFun()=
  {
    var s = ()=> "Hello"       //create the function
    s                          // if you put only that var name that you declare as fun it will return that lambda expression 
    //s()                         if you declare with () it will return the value of that lambda expression
  }
  /*
   ()=>"Hello"                    this will return same as s without parenthese does
  */
  def main(args: Array[String]): Unit = {
    var s= resFun()
    var str = s
    print(str)
    }
}
````

#### STRING INTERPOLATION


### Collection
#Immutable
![pic](https://i.stack.imgur.com/jJ9Pj.png)
#Mutable
![pic](https://www.scala-lang.org/docu/files/collections-api/collections.mutable.png)

hashTree

bitset allow negative values  

Immutable
list `:+`=append `+:`=prepend  `::`=Add 2 list `:::`=combline 2 list  
set & &- + ++ -
listset can use with ++ - +  
Map id  + - ++  
Hashmap = map   
sequence = list  
hashset = set   
Treeset = set with unique and ordering  
Sortedset triat = treeset  
Vector simular to list  

mutable += -+ ++= --=