#### Classes and Inheritance
A class consists of data members and methods. They are default private, we can use keyword public to make these
data members and methods public.

	```CPP
	#include <iostream>
	using namespace std;
	
	#define NAME_SIZE 50
	
	class Person {
			int id;
			char name[NAME_SIZE];
		
		public:
			void aboutMe() {
				cout << "I'm a person." << endl;
			}
	};
	
	class Student: public Person {
		public:
			void aboutMe() {
				cout << "I'm a student." << endl;
			}
	};
	
	int main()
	{
		Student *p = new Student();
		p->aboutMe();
		delete p;
		return 0;
	}
	```
	
#### Constructors and Destructors
1. The constructor of a class is automatically called upon an object's creation. If no constructor is
defined, the compiler automatically generates one called the Default Constructor. Alternatively, we can 
define our own constructor. Note: constructor must be public, otherwise we cannot instantiate the class. 

	```CPP
	Person(int a) {
		id = a;
	}
	```
	
	```CPP
	Person(int a): id(a) {
		...
	}
	```
	
2. The destructor cleans up upon object deletion and is automatically called when an object is destroyed. 
It cannot take an argument as we don't explicitly call a destructor

	```CPP
	~Person() {
		delete obj; //free any memory allocated within class
	}
	```

#### Virtual Functions
	
	```CPP
	Student *p = new Student();
	p->aboutMe();  // output "I'm a student."
	```

	```CPP
	Person *p = new Student();
	p->aboutMe(); // output "I'm a person."
	```
	
	```cpp
	class person {
		...
		virtual void aboutme() {
			cout << "I'm a person." << endl;
		}
	}
	
	Person *p = new Person();
	p->aboutMe(); // output "I'm a student."
	```
	
#### Default Values
Functions can specify default values, as shown below. Note that all default parameters must be on the 
right side of the function declaration, as there would be no other way to specify how the parameters 
line up.

	```CPP
	int func(int a, int b=3) {
		x = a;
		y = b;
		return x + y;
	}
	
	w = func(4);
	z = func(4, 5);
	```
	
#### Operator Overloading
Operator overloading enables us to apply operators like + to objects. For example, if we want to merge two
Bookshelves into one, we could overload the + operator as follows.

	```CPP
	BookShelf BookShelf::operator+(BookShelf&other) {
		...
	}
	```
	
#### Differences between Pointers and References
1. A pointer holds the address of a variable and can be used to perform any operation that could be directly
done on the variable, such as accessing and modifying it. 

2. The size of a pointer varies depending on the architecture: 32 bits on a 32-bit machine and 64 bits on a 
64-bit machine. 

	```CPP
	int *p = new int[5];
	for (int i=0; i<5; i++) p[i] = i;
	cout << *p << endl;
	p++; // skip ahead by sizeof(int) 
	cout << *p << endl;
	```

3. A reference is another name of a pre-existing object, and it does not have memory of its own. You cannot 
create a reference without specifying where in memory it refers to. References cannot be null, and cannot be 
reassigned to another piece of memory. 

	```CPP
	int a = 7;
	int &b = a;
	b = 8;
	cout << a << endl; //output 8
	
	int d = 10;
	b = d;
	cout << b << endl;  // output 10
	b = 20;
	cout << b << endl; //output 20
	cout << d << endl; //output 10
	```

#### Templates (template class, and template function)
Templates are a way of reusing code to apply the same class or method to different data types. For example, we might
have a list-like data structure which we would like to use for lists of various types. 

1. template class
	
	```CPP
	template <class T>
	class List{
		T* array;
		...
	};
	```
	
2. template function

	```CPP
	template <typename T> 
	T add(T a, T b) {
		return a + b;
	}
	```

3. Three characteristics of Object-Oriented Design
	* encapsulation (·â×°)
	* inheritance (¼Ì³Ð)
	* morphism (¶àÌ¬)

