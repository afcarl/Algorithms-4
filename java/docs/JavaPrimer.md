# A Java Primer

## 1. Hello world program:

This is the hello world program written in Java

```java
public class Hello {

	public static void main(String args[]) {

		System.out.println("Hello World");

	}

}
```

## 2. Base type:

```java
boolean flag = true;
char grade = 'A';
byte b = 12;
short s = 24;
int i, j, k = 256;
long l = 890L;
float pi = 3.1416F;
double e = 2.3423, a = 124324e3;
```

## 3. Classes and Objects:

Members of a class in Java: 

* Instance variables
* Methods 
 * **Accessor** method: does not update the instance variables
 * **Update** method: update the instance variables

A demo class:

```java
public class Counter {
	
	public class Counter() {  }

	public void increase(int n) {  }

	public void decrease(int n ) {  }

}
```

### 3.1. Creating a class:

```java
Counter c = new Counter();
```

Classes are known as **reference types** in Java, and a variable of that type (such as c in the example) is known as a **reference variable**  
A reference variable is capable of storing the location (i.e., **memory address**) of an object from the declared class  

> Three events occur as part of the creation of a new instance of a class:  

> * A new object is dynamically allocated in memory, and all instance variables are initialized to standard default values. The default values are **null** for reference variables and 0 for all base types except **boolean** variables (which are **false** by default).

> * The constructor for the new object is called with the parameters specified. The constructor may assign more meaningful values to any of the instance variables, and perform any additional computations that must be done due to the creation of this object.

> * After the constructor returns, the **new** operator returns a reference (that is, a memory address) to the newly created object. If the expression is in the form of an assignment statement, then this address is stored in the object variable, so the object variable **refers** to this newly created object.

### 3.2. The Dot Operator:

To access the members of the class. We call a method associated with an object by using the reference variable name, following that by the dot operator and then the method name and its parameters.

For example:
```java
c.getCount();
c.increment();
```

> Side note: a method's name combined with the number and types of its parameters is called a method's **_signature_**, for it takes all of these parts to determine the actual method to perform for a certain method call.

### 3.3. Defining a class:

* Access control modifers:
 * **public**: all classes may access the defined aspect.
 * **protected**: access to the defined aspect is only granted to the following groups of other classes:   
   * **subclasses** of the given class  
	* classes that belong to the same **package** of the given class
 * **private**: access to a defined member of class be granted only to code withing that class. Neither subclasses nor any other classes have access to such members.

* **static** modifier:

> Static variables are used to store "global" information about a class. (For example, a static variable could be used to maintain the total number of instances of that class that have been created.) Static variables exist even if no instance of their class exists.

* **abstract** modifier:

> A method of a class may be declared as abstract, in which case its signature is pro- vided but without an implementation of the method body. Abstract methods are an advanced feature of object-oriented programming to be combined with inheritance

> A class with one or more abstract methods must also be formally declared as **abstract**, because it is essentially incomplete.

* **final** modifier:

If variable is declared with the **final** modifier, it can never be reassigned a new value.  
_If a member variable of a class is declared as final, it will typically be declared as static as well._  
A final method cannot be overridden by a subclass, and a final class cannot even be subclassed.

## 4. Strings, Wrappers, Arrays, and Enum Types

### 4.1. String Class:

###### Character indexing:  

Characters in a string can be referenced by using an **index**. The first index is 0 and the last is n - 1 (n is the length of the string). To access a character at a particular index _x_:
```java
string1.charAt(x);
```

###### Concaternation:

```java 
String term = "over" + "load";
```
###### The StringBuilder Class:

An important trait of Java's String class is that its instances are **_immutable_**, which means its values cannot be changed. Therefore, concaternation and reassigment do not mutate the current String, but rather reassign to a new one.

StringBuilder class, on the other hand, provides **_mutable_** strings with the following methods:
```java
term.setCharAt(k, c); // Change the character at index k to character c
term.insert(k, s); // Insert a copy of string _s_ starting at index _k_ of the sequence, shifting existing characters further back to make room.
term.append(s); // append string s to the end of the sequence.
term.reverse(); // reverse the current sequence
term.toString(); // return a traditional String sequence based on the current characger sequence
```