### Object Construction
The most basic way to make a class ...
```cs
public class Vehicle{
    public int NumPassengers; //Automatically defaults to 0
}
```
To create a constructor within your class....
```cs
public Vehicle(int val){
    NumPassengers = val;
}
```

### Access Modifiers
- public - Any Property or Method of a class can be access and changed
- private - Only the class can change the property or invoke the method
- protected - Allows the parents of inheritance to access the childs property or method
- internal - Only the internal assembly can access the property or method

Encapsulation is the idea that you want only certain properties or methods to be exposed to the rest of your code. If a method is only used internally for your code then it should be private. 


### Getters and Setters
Sometimes you want your code to be "protected" meaning that a property shouldn't be accessed to the public, but you still want other pieces of code to change or read that property. That is where get and set come in.
```cs
    public int Age {get; set;}
```

### Inheritance
Often times a class will want to pass its methods and properties down to a child. To do this...
```cs
public class Vehicle{
    public int NumPassengers;

    // Constructor
    public Vehicle(int numPass){
        NumPassengers = numPass;
    }
}


public class Car : Vehicle{
    public string Make;
    public string Model;
    // Constructor
    public Car (int numPass,string make, string model) : base(numPass){
        Make = make;
        Model = model;
    }
}
```
The base method says to take the speicified input parameter and send it to the parents constructor.

### Method Overriding
Often times the parent and child will share a method, so how can we make sure which one to use
- Adding virtual to the parent method means that this method can be overrwritten by a child
- Adding override to the child method means that the parent has the same method and you want to use the child's instead.
```cs
    // Inside the parent class
    public virtual void GetInfo(){
        // Do something
    }

    // Inside the child class
    public override void GetInfo(){
        // Do Something different
    }
```

### Polymorphism
The idea that any class can be treated as such inside the inheritance class chain. In our example we could treat a car as a vehicle because it is inherited from that class

### Interfaces
Interfaces are used where a method might require a property beforehand to invoke said method
```cs 
interface IRideable{
    void Ride(double distance); // Method Signature
    double TotalDistanceTravelled {get;set;}
}
```
So to use the interface an object must have a matching method called Ride and a Property called TotalDistanceTravelled.

To implement this inside our code we do so just like inheritance
```cs
class Car : Vehicle, IRideable{
    // Code
}
```

### IEnumerable
The most common use case for interfaces is an IEnumerable. Lists, Dictionarys, and Arrays are all child elements to the IEnumerable interface meaning that they can be looped through.

### Abstract Classes
An abstract class is a class that can never become an instance by itself and its sole purpose is to be inherited by a child. 
```cs
abstract class Vehicle{
    // Code Here
}
```

We can then add an abstract method to the parent, meaning that the child MUST override the method
```cs
    // Inside Parent
    public abstract void MakeNoise();
    // inside of Child
    public override void MakeNoise(){
        // Code
    }
```

### Delegates
A callback is a function passed to another function. A delegate is a reference to a function such that it can be passed to a function.
```cs
public delegate void Del(string message);
public static void DelegateMethod(string message){
    // some code
}
Del handler = DelegateMethod;
```

### Static Classes
A static class is one that only contain static fields/methods and it cannot be instanced. 