# Java-Basics
## Basic concepts of OOPs are:
1. Object
2. Class
3. Inheritance
4. Polymorphism
5. Abstraction
6. Encapsulation

__3. Inheritance:__ A class that is derived from another class is called a subclass (also a derived class, extended class, or child class). The class from which the subclass is derived is called a superclass (also a base class or a parent class).

__4. Polymorphism:__


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


