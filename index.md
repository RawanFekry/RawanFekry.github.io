# Const and & Report

# 1- Const Keyword usages:

![Screenshot (25)](https://user-images.githubusercontent.com/93431157/145729171-78c46ccf-8342-40f0-81e7-89c8d49a7ecb.png)



Const keyword stands for constant. In C++ it is used to make some values constant throughout the program. If we make an artifact of a C++ program as constant then its value cannot be changed during the program execution.

# 1.1- Cost variables:
The const keyword describe that a variable's value is constant and tells the compiler to prevent the user from change it's value during next lines of the code .
Example 1 :

```ruby
 int main() {
   const int num = 20;
  num= 15;   // compile time error
}
```
In (example 1) a variable ‘num’ is declared as const and initialized  with a value  20 at the same time
if you try to change its value later ,  C++ compiler will raise an error as shown.
##error C3892: ‘num’ : you cannot assign to a variable that is const

Example 2 :

```ruby
 int main() {
   const int num = 20;
  num--; // compile time error  
}
```
In (example 2) C++ compiler will raise an error as shown.
##error C2105: ‘num’ :  you cannot decrement that is const
**Size of an arrary can be  specified  with a const variable :

Example 3:

```ruby
 int main() {
 const int myarray = 255;
char store_char[myarray];   
}
```

# 1.2: Const Pointers:

# 1.2.1: Pointer to a const variable:

This means that the pointer is pointing to a const variable

Example 4 :

```ruby
 const int* ptr;  
```
when ,ptr is a pointer that can point to a const int type variable

In this operation:
- ptr can point to anyvariable  (The pointer can be changed).
- The value that ptr points to cannot be changed,(The value of the int cannot be changed).


# 1.2.2:  Const Pointer to a variable:
Example 5 :

```ruby
int i = 1;
int* const ptr = &i;
```
when, ptr is a constant pointer that points to an int (that in is not necessary to be const )
In this operation:
- ptr always point to the variable i (The pointer cannot be changed).
- The value that ptr points to can be changed, by changing the value of i.
 Example 6 :

```ruby
int i = 1;
int* const ptr = &i;
i=i+10; // that is right
*prt=*ptr+10; // compilation error
```
# 1.2.3: const pointer to a const variable :

Example 7 :

```ruby
const int* const i;
```
In this operation:
- ptr always point to the variable i (The pointer cannot be changed).
- The value that ptr points to cannot be changed,too.

# 1.3- Const Function Arguments and return type :
# 1.3.1- const function arguments:
 If an argument is declared as const then the function will not be allowed to change its value.

 Example 8 :

```ruby
int Task (const int x){
x+=100; // error
return x;
}
```
# 1.3.2- const function return type:
 If a return type is declared as const then the function will not be allowed to change its value.

 Example 9 :

```ruby
const int Task()
{
    return 1;
}
int main()
{
    const int x = Task();
    int y = Task();
}
```
** note: in example 9 Both x and y will be assigned the value 1. No error will occur.

# 1.4- const class data members:

 If we define a const data member of a class then we must have to initialize that data member through the constructor of the class. The value of const data members cannot be changed through the object of the variable .

  Example 10:

```ruby
 class Task{
 public:
 const int x;
 Task(int i) : x(i){}; // initialization by the constructor
 };
 Void main(){
  Task t(50);
 t.x=100; // error
 }
```

# 1.5- const class object :

When  we declare an object of class as const then the values of data members can never be changed later on

Example 11:

```ruby
 class Task{
 public:
 int x;
 Task(int i){
 x=i;
 }
 };
 Void main(){
 const Task t(50);
 t.x=100; // error
 }
```


 # 2- & usages :


![Screenshot (27)](https://user-images.githubusercontent.com/93431157/145733151-92a912a7-a7f5-4249-a41a-9ae45baeb03a.png)


# 2.1- & :

# 2.1.1- : Bitwise AND :

-Bitwise AND is an infix operator taking two numbers as inputs and doing an AND on each of the bit pairs of the inputs
-It compares each bit of the first operand to that bit of the second operand. If both bits are 1, the bit is set to 1. Otherwise, the bit is set to 0. 
-Both operands to the bitwise AND operator must be of integral types. 

Example 1 :

 ```ruby
 int main() {  
   unsigned short x = 0x5555;      // pattern 0101 ...  
   unsigned short y = 0xAAAA;      // pattern 1010 ...  
   cout << hex << ( x & y ) ;
}
```
In the prevoius example the output will be :

 ```ruby
0
```

# 2.1.2-  Address Of operators :

Example 2 :

 ```ruby
 nt main () {
   int  var;
   int  *ptr;
   int  val;
   var = 3000;
   // take the address of var
   ptr = &var;
   cout << "Value of var :" << var << endl;
   cout << "Value of ptr :" << ptr << endl;  // where I used & to get the adress that pointer ptr point to 
  
   return 0;
}
```
In the prevoius example the output will be :

```ruby
Value of var :3000
Value of ptr :0xbff64494    
```
# 2.1.3: Declare a refrence to a type:

-using & in the left-hand side of a variable declaration meaning that you expect to have a reference to the declared type.
-It can be used in any type of declarations (local variables, class members, method parameters).

Example 3 :

 ```ruby
string mrSamberg("Andy");
string& theBoss = mrSamberg;
```
 the previous code maening that :
both mrSamberg and theBoss will have the same value ang  actually point to the same place in the memory.

# 2.2- && :
#logical expression (AND):

- (&&) is used when evaluating two expressions to obtain a single relational result.
- The operator && corresponds to the Boolean logical operation AND, which yields true if both its operands are true, and false otherwise.

Example 4 :

 ```ruby
( (5 == 10) && (2 < 5) )  // evaluates to false ( false && true )
( (10== 10) && (2 > 5) )  // evaluates to false ( true && false )
( (5 == 10) && (2 > 5) )  // evaluates to false ( false && true )
( (10== 10) && (2 < 5) )  // evaluates to true ( true && true )
```

# 2.3- &= :
 Bitwise AND assignment :

- It is a compound assignment operator that is modify the current value of a variable by performing a Bitwise operation (&) on it.

 for example :

  ```ruby
// x&=y 
// that is the same as :
// x=x&y
```
