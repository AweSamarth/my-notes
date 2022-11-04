Main format of a program:

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cin >> n;
    
    //your code goes here 
    
    
    return 0;
}
```

1. Endl or \n for new line 
    
    eg. cout << "stupid" endl ;
    
    or   cout << "stupid \n" ;
    

 

1. single line comment using // 
2. multi line comment using /* ..... */
3. add variable type before writing variable name
4. `int a,b;`   to define more than two variables in one line
5. use auto to auto detect the type of variable but then also needed to give a value to the variable straight away 
eg. auto x= 23; is correct but auto x; is incorrect
6. x++ means increasing x by 1  (postfix form)
++x also means increasing x by 1 (prefix form) but
prefix increments the value, and then proceeds with the expression and postfix first evaluates the expression and then performs the incrementing

```cpp
//Prefix example:
x = 5;
y = ++x;

// x is 6, y is 6

//Postfix example:
x = 5;
y = x++;

// x is 6, y is 5

/*
The prefix example increments the value of x, and then assigns it to y.
The postfix example assigns the value of x to y, and then increments it.*/

```

1. switch for avoiding multiple if statements
eg. 

    
    ```cpp
    #include <iostream>
    using namespace std;
    int main()
    {
    int age = 42;
    switch (age) {
    case 16:
    cout << "Too young" << endl;
    case 42:
    cout << "Adult" << endl;
    case 70:
    cout << "Senior" << endl;
    default:
    cout <<"This is the default case" << endl;
    }
    return 0;
    }
    ```
    
2. Using **switch** without **break** causes other **case**s to execute as well. This behaviour is called fall- through
3. if else:

```cpp
if (condition1) {
  // block of code to be executed if condition1 is true
} else if (condition2) {
  // block of code to be executed if the condition1 is false and condition2 is true
} else {
  // block of code to be executed if the condition1 is false and condition2 is false
}
```

1. Format for using for loop

```cpp
for ( init; condition; increment ) {
  statement(s);
}
```

```cpp
for
(int x = 0; x< 7; x++) {
  cout << "in a loop" << endl;
}
```

1. Format for using while loop

```cpp
#include <iostream>
using namespace std;

int main()
{
    int num = 1;
    while (num < 6) {
        cout << "Number: " << num << endl;
        num = num + 1;
    }

    return 0;
```

1. Project countdown:

```cpp
	#include <iostream>
	using namespace std;
	
	int main() {
	    int n;
	    cin >> n;
	    
	    while (n>0){
	        cout<<n << endl ;
	        if (n%5==0){
	            cout<<"Beep";
	        }
	        n--;
	    }
	    
	    
	    return 0;
	}
```

1. Unlike in Python, string + numeral does not result in concatenation but instead gives an error
2. In C++, single quotation marks indicate a character; double quotes create a string literal. While 'a' is a single a character literal, "a" is a string literal.
3. The integer data type reserves 4-8 bytes depending on the operating system.
4. In most modern architectures, a float is 4 bytes, a double is 8, and a long double can be equivalent to a double (8 bytes), or 16 bytes. Floating type (the aforementioned 3) can hold negative numbers
5. There are two known conventions for naming variables: Pascal case  eg: BackColourHopBop and Camel case eg: camelCopBopBeep
6. C++ is case sensitive
7. Reserved keywords cannot be used as variable names eg: int, float , double, cout etc
8. Creating an array in C++:

```cpp
int a[5];
/*this creates an array 'a' consisting of 5 elements.
It is just initialized and there is nothing in it*/

int a[5]={1,2,3,4,5};
/*the number of elements in {} should not exceed the number of elements defined
while initializing in []
Notice the {} used instead of [] that we use in other languages

for creating as many elements as we want we use:*/
int b[]

//for accessing an element with index 4 in list 'a' we do://
cout<< b[4]
```

1. These arrays can be used to assign a value to an entered thing
2. Multi-dimensional arrays are basically matrices

```cpp
int x[3][4];

//Visualize this array as a table composed of 3 rows, and 4 columns.//
//first rows then columns
```

ex:

```cpp
//Type in a code to print arr's element which is in the first row, second column
cout<<arr[0][1]
//since counting starts from 0
```

1. Pointers: every variable is a memory location, which has its address defined. The address can be accessed using the **&** operator which denotes an address in memory

```cpp
int score=5;
cout <<& score << endl;
/*will give:
0x7ffce119c59c*/
```

1. A pointer is a variable with the address of another variable as its value. Helps in dynamic memory allocation. All pointers have the same data type: a long hexadecimal number that represents a memory address
2.  * is used for declaring a pointer. The asterisk sign can be placed next to the data type, or the variable name, or in the middle.

```cpp
int *ip
//declares ip as a pointer to an integer

int score=5;
int *scoreptr;
scoreptr=&score;

```

27. 

```cpp
#include <iostream>
using namespace std;

int main()
{
    int var = 50;
    int  *p;
    p = &var;

    cout << var << endl;
    // Outputs 50 (the value of var)

    cout << p << endl;
    // Outputs 0x29fee8 (var's memory location)

    cout << *p << endl;
    /* Outputs 50 (the value of the variable
     stored in the pointer p) */

    return 0;
}
```

1. The asterisk (*) is used in declaring a pointer for the simple purpose of indicating that it is a pointer (The asterisk is part of its type compound specifier). Don't confuse this with the **dereference** operator, which is used to obtain the value located at the specified address. They are simply two different things represented with the same sign.
2. & is address-of operator and * is contents of (dereference) operator
3. In a C++ program, memory is divided into two parts:
**The stack:** All of your local variables take up memory from the stack.
**The heap:** Unused program memory that can be used when the program runs 
to **dynamically** allocate the memory.
4. For allocating memory from the heap beforehand while creating a variable using ‘new’

```cpp
new int;
//this allocates (from the heap) the memory size necessary for storing an integer and 
//returns that address
```

1. The allocated address can be stored in a **pointer,** which can then be dereferenced to access the variable.

```cpp
int *p = **new** int;
*p = 5;
/*We have dynamically allocated memory for an integer, and assigned it a value of 5.

The pointer p is stored in the stack as a local variable, and holds the heap's allocated address as its value. The value of 5 is stored at that address in the heap.*/

```

1. For local stack variables, memory management is automatic but on for heap, manual intervention is required. Forgetting to free up memory that has been allocated with the **new** keyword will result in memory leaks, because that memory will stay allocated until the program shuts down.
’delete’ operator for freeing up memory

```cpp
delete pointer;
//this statement releases the memory pointed to by pointer
```

1. Delete operator does not delete the pointer, just the memory pointed to by it. Pointers that are left pointing to non-existent memory locations are called dangling pointers
2. The NULL pointer is a constant with a value of 0 that is defined in several of the standard libraries, including iostream. Assign NULL while declaring pointer and unsure where it should point to. That pointer will be called NULL pointer

```cpp
int *ptr=NULL;
```

1. sizeof operator shows the size of a variable or data type or array

```cpp
sizeof(int);
double arr[10];
//assuming that double takes up 8 bytes,
cout<<sizeof(arr);
//this will give 8*10: 80
```

1. Functions are also there in c++. main is also a function. The type of the result (return) of the function is pre-defined before the name of the function. Those functions which do not return any value are defined with the keyword void  

```cpp
int main(){
return 0
}
```

Syntax:

```cpp
return_type function_name( parameter list )
{
   body of the function
}
//this is declaration and definition of a function

return_type function_name(parameter list);
//this is just declaration of a function. this should be at the top of the file even 
//before int main when there are multiple files and the function is in a different
//than the one where it's needed
```

1. For using the pseudo random number generating function: rand(), we need to include C++ standard library (cstdlib)

```cpp
#include<iostream>;
#include<cstdlib>;
using namespace std;
int main(){
	cout<<rand()
return 0
}
//this will output a random number
```

1. Pseudo random because each time the code is run, it will return the same “random” number
2. Use % to define the range in which a random number needs to be found. Eg.

```cpp
int main(){
	for (int x=1, x<=5, x++){
	cout<<1+(rand()%6)<<endl;
	}
}
//this will return a random number between 1 and 6 (both included)
```

1. srand() (kind of) generates truly random numbers. Within the brackets we specify a numeric value which is the seed value. For different seed values, the returned value will be different and for the same seed value the returned value will be the same

```cpp
#include <iostream>
#include <cstdlib>
using namespace std;

int main () {
    srand(98);

    for (int x = 1; x <= 10; x++) {
        cout << 1 + (rand() % 6) << endl;
    }
}
```

1. For TRULY random numbers we can use the current time as the seed value for srand(). Should include ctime header for it to work

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main () {
    srand(time(0));
    for (int x = 1; x <= 10; x++) {
        cout << 1 + (rand() % 6) << endl;
    }
}
//time(0) will retrun the second value count, forcing the srand function to change its seed value everytime it's run
```

1. We can overload functions as in make them available for different data types

```cpp
int some(int a);
int some(float a);
//now this is availabe for both int and float
```

1. Recursion: When a function calls itself it’s called recursion: when a function calls itself it’s called recursion: when a.....

```cpp
//Factorial
int factorial(int n) {
  if (n==1) {
    return 1;
  }
  else {
    return n * factorial(n-1);
  }
}
```

1. Exit condition is also called base case. Without an exit condition, the code will keep running forever
2. Arrays can also be passed to a function as its arguments

```cpp
int func(int arr[]){
}
//this is the parameter
int myarr[3]=[1,2,3];
func(myarr);
```

1. Passing arguments by value: Pass the copy of the variable as the argument
2. Formal vs Actual Parameters

```cpp
int sum(int a, int b)		//Statement 1 
{ 
	return a+b; 
} 
int main() 
{ 
	int x=10,y=20; 
	int s = sum(x,y);		//Statement 2 
	return 0; 
)

//In Statement 1, the variables a and b are called FORMAL PARAMETERS. In Statement 2 
//the arguments x and y are called ACTUAL PARAMETERS (as they are the actual ones to hold 
//the values, you can think it like this).
```

1. Passing arguments by reference:
    
    copies an argument's address into the formal parameter. Inside the function, the address is used to access the actual argument used in the call. This means that changes made to the parameter affect the argument. To pass the value by reference, argument **pointers** are passed to the functions just like any other value.
    

```cpp
//by value
#include <iostream>
using namespace std;

void myFunc(int x) {
    x = 100;
}

int main() {
    int var = 20;
    myFunc(var);
    cout << var;
}
//output will be 20

//by reference
#include <iostream>
using namespace std;

void myFunc(int *x) {
    *x = 100;
}

int main() {
    int var = 20;
    myFunc(&var);
    cout << var;
}
//output will be 100
```

- In general, passing by value is faster and more effective. Pass by reference when your function needs to modify the argument, or when you need to pass a data type, that uses a lot of memory and is expensive to copy.

## Object Oriented Programming (OOP)

(starts here)

- It is a programming style that makes thinking about programming like thinking about the real world. A mug is an object irl. There may be two mugs but they both have their own identities.
- An object has its identity.
- An object has characteristics or attributes. irl example: a mug’s attributes can be its colour, the quantity of liquid in it, its size etc. An object’s type is independent of its characteristics eg. two glasses, one can be full and one can be half filled but they are still glasses. Attribute describes the current state of an object and an object may have multiple attributes.
- Behaviour is specific to an object’s type
- So, the following three dimensions describe any object in object oriented programming: **identity**, **attributes**, **behavior**.
- In programming an object is self contained: with its own identity. It is separate from other objects. Each object has its own attributes and behaviours.
- Objects are created using classes. Classes are the main things of OOP
- The class of an object describes what the object will be but is separate from the object itself i.e. it’s an object’s blueprint, description, or definition.
- You can use the same class as a blueprint for creating multiple different objects. For example, in preparation to creating a new building, the architect creates a blueprint, which is used as a basis for actually building the structure. That same blueprint can be used to create multiple buildings.
- In programming the term “type” is used to refer to a class name
- A method is basically a function belonging to a class. Methods are similar to functions - they are blocks of code that are called, and they can also perform actions and return values.
- Each object is called an **instance** of a class. The process of creating objects is called **instantiation**.

```cpp
//creating a class 'bankAccount'
	class bankAccount{
};
//notice the semicolon after the curly brace!
```

- All attributes and behaviours are to be written inside the curly braces (the body of the class)
- We can also define an access specifier for members of the class. A member that has been defined using the public keyword can be accessed anywhere outside of it as long as it is in the scope of the class object. Private and protected keywords are also there. Maybe later
- Public, private and protected are all access specifiers. Default is private.

```cpp
class BankAccount {
  public:
    void sayHi() {
      cout << "Hi" << endl;
    }
};
int main()
{
	BankAccount test;
	test.sayHi();
}
/* test is an object of the class BankAccount*/

```

- Abstraction: Focusing on the essential qualities of something. In C++ it is the foundation of polymorphism and inheritance (later). eg. Abstraction allows us to write different accounts’ information under the same class- BankAccount and we don't need to make separate classes for separate accounts
- Encapsulation: data hiding ie. an object of a class only reveals that much info to another application component as needed. Basically restricting access to the inner workings of a class. Also called black-boxing

```cpp
//public member can be viewed and modified from outside the class as well
#include <iostream>
#include <string>
using namespace std;

class myClass {
    public:
        string name;
};

int main() {
    myClass myObj;
    myObj.name = "SoloLearn";
    cout << myObj.name;

    return 0;
}
```

```cpp
//Private class cannot be viewed and modified from outside the class,, only from inside
#include <iostream>
#include <string>
using namespace std;

class myClass {
    public:
        void setName(string x) {
            name = x;
        }
    private:
        string name;
};

int main() {
    myClass myObj;
    myObj.setName("John");

    return 0;
}
/*The name attribute is private and not accessible from the outside.
The public setName() method is used to set the name attribute.*/

```

- Constructors are executed as soon as a new object is created in a class. The constructor’s name is identical to that of the class and it has no return type (not even void). But parameters can be there

```cpp
class myClass {
  public:
    myClass(string nm) {
      setName(nm);
    }
    void setName(string x) {
      name = x;
    }
    string getName() {
      return name;
    }
  private:
    string name;
};
```

- Source file has extension .cpp and header file has extension .h
- Header file contains the function prototypes and variable declarations
- The **header** declares "what" a class (or whatever is being implemented) will do, while the **cpp source** file defines "how" it will perform those features.
- ifndef (in the header file) stands for if not defined. Close the condition with endif

```cpp
#ifndef MYCLASS_H
#define MYCLASS_H

class MyClass
{
  public:
  MyClass();
  protected:
  private:
};

#endif // MYCLASS_H
```

```cpp
//Myclass.h
#ifndef MYCLASS_H
//if not defined
#define MYCLASS_H

class MyClass
{
  public:
		MyClass();	
		void newfunc();
  protected:
  private:
};

#endif // MYCLASS_H

//Myclass.cpp
#include "MyClass.h"

MyClass::MyClass()
{
   //constructor
		}
void MyClass::newfunc(){

}
//here double colon in MyClass::MyClass() is called as scope resolution operator. 
//This operator is used to define a particular class' member's functions which have already 
//been declared So, basically, MyClass::MyClass() refers to the MyClass() member function - or, in this case, constructor - of the MyClass class.

//since newfunc is a regular member function it is necessary to specify its data type both during declaration and definition
```

```cpp
//To create a function test in a class 'demo'
demo::test()
{
}
```

- Destructors are opposite of constructors
- Destructors are created when an object is removed from the class. Removed as in either going out of scope or removed using ‘delete’ expression. The name of the destructor is the same as the name of the class, but it is prefixed with a tilde (~). Destructors are useful in releasing resources before coming out of a program. This can include closing files, releasing memory etc.
- Destructors cannot take parameters so they can’t be overloaded. Every class can have at max 1 destructor
- The **arrow member selection operator (->)** is used to access an object's members with a pointer.
- When working with an object, use the **dot** member selection operator (.). When working with a pointer to the object, use the **arrow** member selection operator (->).

```cpp
MyClass obj;
    MyClass *ptr = &obj;
    ptr->myPrint();
```

- A constant variable is one which can’t be changed while the program is running. Use const keyword
- const can also be used for class objects. After using const, the objects cannot be changed from outside and even inside the class. It stays same throughout its lifetime
- Only non const objects can call non const functions

```cpp
//for making a constant function
void functionanme() const;

```

- We can initialize member variables in classes. We MUST make initializer lists for constant variables

```cpp
//This code will give error as in private class we have already said tht constVar is a constant variable but in public we are trying to assign a value to it
class MyClass {
  public:
   MyClass(int a, int b) {
    regVar = a;
    constVar = b;
   }
  private:
    int regVar;
    const int constVar;
};
```

```cpp
//Use this instead, here member initializers are used
class MyClass {
 public:
  MyClass(int a, int b)
//now comes the member initialization
  : regVar(a), constVar(b)
//above
  {
  }
 private:
  int regVar;
  const int constVar;
};

```

```cpp
Student::Student(int a, int b)
 :
 age(a),num(b) {

}
//for creating age=a and num=b
```

- There is a way to modify private members by functions which are not member functions of the class: the friend keyword. It indicates that the function is a “friend” of that class
- “this” is a pointer. Only member functions of a class have a this pointer. “this” is basically to store the address of the current object

```cpp

//For a class ''MyClass'', with one private member named ''mem'', fill in the blanks to print out its value in the printValue() function using the ''this'' keyword.
void MyClass::printValue() {

 cout << this->mem
;

}

```

- Overloaded operators are functions, defined by the keyword **operator** followed by the symbol for the operator being defined. An overloaded operator is similar to other functions in that it has a **return type** and a **parameter list.**

```cpp
class MyClass {
 public:
  int var;
  MyClass() {}
  MyClass(int a)
  : var(a) { }

  MyClass operator+(MyClass &obj) {
   MyClass res;
   res.var= this->var+obj.var;
   return res; 
  }
};
```

### Code Project - Queue Management 2

```cpp
/*We continue to develop our Queue management system that we made in the previous module.
You are asked to add a new functionality: adding two queues together. The result should be a new queue, where the elements of the first queue come first, followed by the second queue's elements.

Given the Queue class, overload the + operator, so that the code in main works and successfully adds two queues. The overloaded operator should return a new Queue object, which contains the elements of the first queue, followed by the elements of the second queue.*/
#include <iostream>
using namespace std; 

class Queue { 
	int size; 
	int* queue; 
	
	public:
	Queue() { 
		size = 0;
		queue = new int[100];
	}
	void add(int data) { 
		queue[size] = data; 
		size++;
	}
	void remove() { 
		if (size == 0) { 
			cout << "Queue is empty"<<endl; 
			return; 
		} 
		else { 
			for (int i = 0; i < size - 1; i++) { 
				queue[i] = queue[i + 1]; 
			} 
			size--; 
		} 
	} 
	void print() { 
		if (size == 0) { 
			cout << "Queue is empty"<<endl; 
			return; 
		} 
		for (int i = 0; i < size; i++) { 
			cout<<queue[i]<<" <- ";
		} 
		cout << endl;
	}
	//your code goes here
	Queue operator+(Queue &newobj){
		Queue result;
		result.size=size;
		result.queue=queue;
		int length=newobj.size;
		int n=0;
		while (n<length){
			result.add(newobj.queue[n]);
			n++;
		}
		return result;
	}
	
}; 

int main() { 
	Queue q1; 
	q1.add(42); q1.add(2); q1.add(8);  q1.add(1);
	Queue q2;
	q2.add(3); q2.add(66); q2.add(128);  q2.add(5);
	Queue q3 = q1+q2;
	q3.print();

	return 0; 
}

```

- Inheritance: works as it sounds. Base and Derived class

```cpp
//This syntax derives the Daughter class from the Mother class.
class Daughter : public Mother
{
 public: 
  Daughter() {};
};
//all public memebers of Mother have now become public members of Daughter as well

	//if we use private: public and protected members of the base class become private members of the derived class
//if we use protected: public and protected members of the base class become protected members of the derived class
//if no access specifier is used, default is private
```

- A derived class inherits base class methods with the following exceptions:
Constructors, destructors, overloaded operators, friend functions,
- A class can be derived from multiple classes by specifying the base classes in a **comma-separated** list. For example: **class Daughter: public Mother, public Father**
- Protected access specifier: Very much like private but the only difference is that private members cannot be accessed by derived classes but protected members can be
- When inheriting classes, the base class' constructor and destructor are not inherited. However, they are being called when an object of the derived class is created or deleted. Basically, the derived class needs its base class in order to work.
- When an object of the daughter class is destroyed, first the derived destructor runs, then the base destructor. When an object of the daughter class is created, first the base constructor runs, then the derived constructor
- Polymorphism: literal meaning: having many forms. In C++ it means that a single function can have a number of different implementations.
- Virtual function: works like templates and are used in the base class. The derived classes may have the same function but with different implementation. When the virtual function is run, it is telling the program that the derived classes may have the same functions and in that case the daughter function will override the base function.
- A class is called polymorphic when it has a virtual function
- Pure virtual function: it basically tells the program that all the derived classes have their own implementations of the function. It has no body

```cpp
//syntax for purely virtual
virtual void yeet()=0
//=0 tells the program about the derived classes having their own implementations
```

```cpp
//syntax for just virtual
virtual void yeet(){

}
```

- If the pure virtual function is not overridden in the derived class, the code fails to compile and results in an error when you try to instantiate an object of the derived class. So it must have implementations in the daughter classes.
- Classes with pure virtual functions are called abstract classes. These classes cannot have objects
- Function Templates: we don’t even need to overload functions in order for them to work with different data types, we can just specify a generic type and it will work for different data types

```cpp
template <class T>// instead of class T we can also write typename T
T sum(T a, T b){ //here sum is the function name
return a+b;
}
//this will work for integer double etc. etc.

```

```cpp
template <class T, class U>
//here two different generic data types are used. eg. one can be int and the other can be double

```

```cpp
a<b?a:b
//this is equivalent to: if a is smaller than b, return a else return b
// ?: is a ternary operator since it takes 3 operands
```

- Class templates: Work like function templates

```cpp
template <class T>
class Pair {
 private:
  T first, second;
 public:
  Pair (T a, T b):
   first(a), second(b) {
  }
};
```

- There is a specific format in case we define our member function outside of the class eg in a source file

```cpp
template <class T>
class Pair {
 private:
  T first, second;
 public:
  Pair (T a, T b):
   first(a), second(b){
  }
  T bigger();
};

template <class T>
T Pair<T>::bigger() {
  // notice the angular brackets here
// we can also use int, double instead of T her to get the required result
}
```

- To specify different behavior for the data type char, we would create a template specialization.

```cpp

template <class T>
class MyClass {
 public:
  MyClass (T x) {
   cout <<x<<" -  not a char"<<endl;
  }
};

template < >
class MyClass<char> {
 public:
  MyClass (char x) {
   cout <<x<<" is a char!"<<endl;
  }
};

//here the second class is the specialized template
```

### Exception handling in C++

- Exception handling in C++ is built on top of three keywords: throw, try ,except
- throw

```cpp
int motherAge = 29;
int sonAge = 36;
if (sonAge > motherAge) {
  throw "Wrong age values";
}
```

- try...catch

```cpp
try {
        int motherAge = 29;
        int sonAge = 36;
        if (sonAge > motherAge) {
            throw 99;
        }
    }
    catch (int x) {
        cout<<"Wrong age values - Error "<<x;
    }
```

- It's possible to specify that your catch block handles any type of exception thrown in a try block. To accomplish this, add an **ellipsis (...)** between the parentheses of catch:

### File Handling in C++

- library required is fstream
- Three data types of fstream are
    1. ofstream- output file stream that creates and writes information to files
    2. ifstream- input file stream that reads information from files
    3. fstream- Combo of both above

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
  ofstream MyFile;
  MyFile.open("test.txt");

  MyFile << "Some text. \n";
	MyFile.close()
}

//this opens a file and writes into it
// If the file does not already exist, it is created
//we can straightaway use ofstream MyFile("test.txt") to skip the open function
```

- To check if the file is open and is ready to be accessed we use is_open()

```cpp
if (MyFile.is_open()){
//code
}
```

- Second parameter of open function: it’s like python rw+ r+ etc. filemodes 
ios::app/ate/binary/in/out/trunc
    1. app: for appending only
    2. ate: to go to the end of the file on opening
    3. binary: open file in binary mode
    4. in: open file for reading only
    5. out: open file for writing only
    6. trunc: delete the contents of the file if it exists
- We can combine them suing bitwise or ( | )
- For reading a file

```cpp
int main () {
    ofstream MyFile1("test.txt");
    
    MyFile1 << "This is awesome! \n";
    MyFile1.close();

    string line;
    ifstream MyFile("test.txt");
    while ( getline (MyFile, line) ) {
        cout << line << '\n';
    }
    MyFile.close();
}
//we can also use fstream instead of ifstream
//The getline function reads characters from an input stream and places them into a string.
//The example above reads a text file and prints the contents to the screen.
//Our while loop uses the getline function to read the file line by line.
```
