#### final keyword
The final keyword has a different meaning depending on whether it is applied to a variable, method, or class. 

1. variable: The value of this variable cannot be changed once initialized.

2. method: This method cannot be overridden by a subclass. 

3. class: This class cannot be subclassed. 

#### finally keyword
The finally keyword is used in association with a try/catch block and guarantees that a section of code will be 
executed, even if an exception is thrown. The finally block will be executed after the try and catch blocks, but
before control transfers back to its origin. 

#### finalize method
The automatic garbage collector calls the finalize() method just before actually destroying the object.
A class can therefore override the finalize method to define custom behaviour during garbage collection. 

#### Difference between Overloading and Overriding
1. Overloading: a term used to describe when two methods have the same name, but differ in the type or 
number of arguments. 

	```Java
	public double computeArea(Circle c) {...}
	public double computeArea(Square s) {...}
	```
2. Overriding: a term used to describe when a method shares the same name and function signature as another 
method in its super class.

	```Java
	class Base {
		int me;
		void printMe{
			System.out.println("Base class");
		}
	}
	
	class Test extends Base {
		void printMe {
			System.out.println("Test class");
		}
	}
	```

#### Collection Framework
1. ArrayList

	```Java
	ArrayList<String> myArr = new ArrayList<String>();
	myArr.add("one");
	myArr.add("two");
	System.out.println(myArr.get(0));
	```
		
2. Vector: very similar to ArrayList, except that it is synchronized. 
	
	```Java
	Vector<String> myVect = new Vector<String>();
	myVect.add("one");
	myVect.add("two");
	System.out.println(myVect.get(0));
	```
	
3. LinkedList

	```Java
	LinkedList<String> myLinkedList = new LinkedList<String>();
	myLinkedList.add("two");
	myLinkedList.addFirst("one");
	Iterator<String> iter = myLinkedList.iterator();
	while (iter.hasNext()) {
		System.out.println(iter.next());
	}
	```

4. HashMap

	```JAVA
	HashMap<String, String> map = new HashMap<String, String>();
	map.put("one", "uno");
	map.put("two", "dos");
	System.out.println(map.get("one"));
	```
