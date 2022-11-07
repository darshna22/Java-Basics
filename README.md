# Java-Basics
## Basic concepts of OOPs are:
1. Object
2. Class
3. Inheritance
4. Polymorphism
5. Abstraction
6. Encapsulation

__1. Object:__ An object is an instance of a class. which has properties and behavious.

__2. Class:__ A class is a template or blueprint from which objects are created. So, an object is the instance(result) of a class.

__3. Inheritance:__ A class that is derived from another class is called a subclass (also a derived class, extended class, or child class). The class from which the subclass is derived is called a superclass (also a base class or a parent class).

__What You Can Do in a Subclass__
* A subclass inherits all of the public and protected members of its parent, no matter what package the subclass is in. 
* If the subclass is in the same package as its parent, it also inherits the package-private members of the parent. You can use the inherited members as is, replace them, hide them, or supplement them with new members:
* The inherited fields can be used directly, just like any other fields.
* You can declare a field in the subclass with the same name as the one in the superclass, in that case super clsass field hides.
* You can declare new fields in the subclass that are not in the superclass.
* The inherited methods can be used directly as they are.
* You can write a new instance method in the subclass that has the same signature as the one in the superclass, thus overriding it.
* You can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
* You can declare new methods in the subclass that are not in the superclass.
* You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.
* If sub class object pass to super class variable then only super class things can be access.

__4. Polymorphism:__ Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance
In Java polymorphism is mainly divided into two types: 
1. Compile-time/Static Polymorphism
2. Runtime Polymorphism

__Compile-time Polymorphism:__ It is also known as static polymorphism. This type of polymorphism is achieved by function overloading or operator overloading. 
__Note:__ But Java doesn’t support the Operator Overloading.

* __Method Overloading:__ When there are multiple functions with the same name but different parameters then these functions are said to be overloaded. Functions can be overloaded by change in the number of arguments or/and a change in the type of arguments.
__Eg:__
```
class Helper {

    // Method with 2 integer parameters
    static int Multiply(int a, int b)
    { 
        // Returns product of integer numbers
        return a * b;
    }
 
    // Method 2
    // With same name but with 2 double parameters
    static double Multiply(double a, double b)
    { 
        // Returns product of double numbers
        return a * b;
    }
}
```
__Runtime Polymorphism:__
It is also known as Dynamic Method Dispatch. It is a process in which a function call to the overridden method is resolved at Runtime. This type of polymorphism is achieved by Method Overriding.
*__Method overriding:__ on the other hand, occurs when a derived class has a definition for one of the member functions of the base class. That base function is said to be overridden.
__Eg:__
```
// Java Program for Method Overriding
// Class 1
// Helper class
class Parent {

	// Method of parent class
	void Print()
	{

		// Print statement
		System.out.println("parent class");
	}
}
```
```
// Class 2
// Helper class
class subclass1 extends Parent {

	// Method
	void Print() {
    super.Print();
    System.out.println("subclass1"); }
}
```
```
// Class 3
// Helper class
class subclass2 extends Parent {

	// Method
	void Print()
	{

		// Print statement
		System.out.println("subclass2");
	}
}
```
```
// Class 4
// Main class
class GFG {

	// Main driver method
	public static void main(String[] args)
	{

		// Creating object of class 1
		Parent a;

		// Now we will be calling print methods
		// inside main() method

		a = new subclass1();
		a.Print();

		a = new subclass2();
		a.Print();
	}
}
```
```
__Output:__
parent class
subclass1
subclass2
```

__5. Abstraction:__ Data abstraction is the process of hiding certain details and showing only essential information to the user. Abstraction can be achieved by abstract class or interfaces.

__1. Abstract Class:__ 
* An abstract class is a class that is declared abstract—it may or may not include abstract methods. 
* Abstract classes cannot be instantiated, but they can be subclassed.
* An abstract method is a method that is declared without an implementation (without braces, and followed by a semicolon), like this:
```
abstract void moveTo(double deltaX, double deltaY);
```
* If a class includes abstract methods, then the class itself must be declared abstract, as in:
```
public abstract class GraphicObject {
   // declare fields
   // declare nonabstract methods
   abstract void draw();
}
```
* When an abstract class is subclassed, the subclass usually provides implementations for all of the abstract methods in its parent class. However, if it does not, then the subclass must also be declared abstract.
* An abstract class may have static, final fields and static methods. You can use these static members with a class reference (for example, AbstractClass.staticMethod()) as you would with any other class if sub class extends abstract class like below
```
public abstract class MyAbstract {
    protected static final int n=10;

    public static int getIntValue(){
        return n;
    }
    protected abstract void calculate();
}
```
```
public class MyAbstractImpl extends MyAbstract {
    public static void main(String[] args) {
        System.out.println(""+MyAbstract.n);
        System.out.println(""+MyAbstract.getIntValue());

    }
    @Override
    protected void calculate() {

    }
}
```
__2. Interface:__ 
This is another way of implimenting abstraction but by using interface we can get multi level abstraction while from abstract class we can get only single level abstraction
__Abstract Classes V/S Interfaces__
* Abstract classes are similar to interfaces. 
* You cannot instantiate them, and they may contain a mix of methods declared with or without an implementation. 
* However, with abstract classes, you can declare fields that are not static and final, and define public, protected, and private concrete methods. 
* With interfaces, all fields are automatically public, static, and final, and all methods that you declare or define (as default methods) are public.
* In addition, you can extend only one class, whether or not it is abstract, whereas you can implement any number of interfaces.
* Abstract class can implement interface while interface cam not extends or implement abstract class.
* Abstract class not abstract 100% while interfaces are provides 100% abstractions as they only have abstract methods.
```
interface Bicycle {

    //  wheel revolutions per minute
    void changeCadence(int newValue);

    void changeGear(int newValue);

    void speedUp(int increment);

    void applyBrakes(int decrement);
}
```
__6. Encapsulation:__ Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. 
Eg: Class which encapsulate object properites and behaviours.

