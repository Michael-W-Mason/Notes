### Primitive Data Types
Variables in C# must be statically typed beforehand, meaning that we cannot just define a variable with explicitly saying what it is.
- int - A 32 bit integer value
- long - a 64 bit integer value
- short - a 16 bit integer value
- float - a 32 bit decimal value
- double - a 64 bit decimal value
- char -  a single character
- string - a collection of chars
- bool - true or false statement
- null - variable does not have any value associated with it

There does exist an implicit data type called var however that breaks the statically typed language and should be used sparingly
- var - any data type you want it to be, even null by default

### Declaring Variables
```cs
    int myVar = 0;

    // The ? allows any variable to be the null type
    int? otherVar = null;
```

### Non Primitive Data Types
- Array - A collection of data with an index in order
```cs
  int[] myArr = {1,2,3,4};

  // Creates an array of length 5 initializing all to 0
  int[] otherArr = new int[5];

  int[] anotherArr;
  anotherArr = new int[] {1,2,3,4};
```
- List - A linked list of data
```cs
    List<string> myList = new List<string>();
    myList.Add("item 1");
    myList.Add("item 2");
    Console.WriteLine(myList[1]); // Prints "item 2"
    myList.Insert(1, "item 1.5"); // Adds item at a specific index
    myList.Remove("item 1.5"); // Removes an item by data from list
    myList.RemoveAt(0); // Removes an item at a specific index
```
- Dictionary - Similiar to an object in javascript. Every item of data has a key that is assocatied with that data.
```cs
    Dictionary<string, string> myDict = new Dictionary<string, string>();
    myDict.Add("Key", " Value");
```

### Logical Operators
- && - And
- || - Or
- ! - Not

### Loops
- For Loop
```cs
    for(int i = 0; i < 4; i++){
        // Loops 3 times
    }
```
- While Loop
```cs
    bool condition = true;
    while(condition){
        // Run until condition = false
    }
```

### Functions
```cs
    static void HelloWorld(string data){
        // Code Here
    }
```
- The static word means that the function can be executed anywhere in our code.
- The parameters passed in must be given a data type
- void is the return type of our function. Void means that our function does not return anything at all

### Namespace and using
Namespaces are just a way to organize your code. Defining a namespace is as easy as this
```cs
namespace Code;
// Or in older versions
namespace Code{

}
```
The code you have written can then be referenced by another file with the using keyword
```cs
using Code;
```
The most common case of using is the System
```cs
using System;
```