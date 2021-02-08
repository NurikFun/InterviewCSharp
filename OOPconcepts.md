# InterviewCSharp

**Abstraction means hiding the unnecessary details from type consumers.**
**Encapsulation means that a group of related properties, methods, and other members are treated as a single unit or object.**
**Inheritance describes the ability to create new classes based on an existing class.**
**Polymorphism means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.**

# Inheritance 

**Inheritance is an important pillar of OOP(Object Oriented Programming). It is the mechanism in C# by which one class is allowed to inherit the features(fields and methods) of another class.

**Important terminology:

**Super Class**: The class whose features are inherited is known as super class(or a base class or a parent class).
**Sub Class**: The class that inherits the other class is known as subclass(or a derived class, extended class, or child class). The subclass can add its own fields and methods in addition to the superclass fields and methods.
**Reusability**: Inheritance supports the concept of “reusability”, i.e. when we want to create a new class and there is already a class that includes some of the code that we want, we can derive our new class from the existing class. By doing this, we are reusing the fields and methods of the existing class.

**Example:

using System; 
namespace ConsoleApplication1 { 
  
class GFG { 
   
    public string name; 
    public string subject; 
  
    public void readers(string name, string subject) 
    { 
        this.name = name; 
        this.subject = subject; 
        Console.WriteLine("Myself: " + name);  
        Console.WriteLine("My Favorite Subject is: " + subject); 
    } 
} 
  
class GeeksforGeeks : GFG { 
   

    public GeeksforGeeks() 
    { 
        Console.WriteLine("GeeksforGeeks"); 
    } 
} 
   
class Sudo { 
  
    // Main Method 
    static void Main(string[] args) 
    { 
   
        // creating object of derived class 
        GeeksforGeeks g = new GeeksforGeeks(); 
  
        // calling the method of base class  
        // using the derived class object 
        g.readers("Kirti", "C#"); 
    } 
} 
}

# Encapsulation

**Encapsulation is defined as the wrapping up of data under a single unit. It is the mechanism that binds together code and the data it manipulates. In a different way, encapsulation is a protective shield that prevents the data from being accessed by the code outside this shield.

Technically in encapsulation, the variables or data of a class are hidden from any other class and can be accessed only through any member function of own class in which they are declared.
As in encapsulation, the data in a class is hidden from other classes, so it is also known as data-hiding.
Encapsulation can be achieved by: Declaring all the variables in the class as private and using C# Properties in the class to set and get the values of variables.


using System; 
  
public class DemoEncap { 
      
    private String studentName; 
    private int studentAge; 
      
    public String Name 
    { 
          
        get
        { 
            return studentName;     
        } 
          
        set 
        { 
            studentName = value; 
        } 
          
    } 

    public int Age 
    { 
          
        get 
        { 
            return studentAge;     
        } 
          
        set 
        { 
            studentAge = value; 
        } 
          
    } 
  
      
} 
  
class GFG { 
      
    static public void Main() 
    { 
          
        DemoEncap obj = new DemoEncap(); 

        obj.Name = "Ankita"; 
          
        obj.Age = 21; 

        Console.WriteLine("Name: " + obj.Name); 
        Console.WriteLine("Age: " + obj.Age); 
    } 
} 


**Advantages of Encapsulation:**

**Data Hiding:** The user will have no idea about the inner implementation of the class. It will not be visible to the user that how the class is stored values in the variables. He only knows that we are passing the values to accessors and variables are getting initialized to that value.
**Increased Flexibility:** We can make the variables of the class as read-only or write-only depending on our requirement. If we wish to make the variables as read-only then we have to only use Get Accessor in the code. If we wish to make the variables as write-only then we have to only use Set Accessor.
**Reusability:** Encapsulation also improves the re-usability and easy to change with new requirements.
Testing code is easy: Encapsulated code is easy to test for unit testing.


# Abstraction 

**Data Abstraction

Data Abstraction is the property by virtue of which only the essential details are exhibited to the user. The trivial or the non-essentials units aren’t exhibited to the user.
Data Abstraction may also be defined as the process of identifying only the required characteristics of an object ignoring the irrelevant details. The properties and behaviors of an object differentiate it from other objects of similar type and also help in classifying/grouping the objects.

Example: Consider a real-life scenario of withdrawing money from ATM. The user only knows that in ATM machine first enter ATM card, then enter the pin code of ATM card, and then enter the amount which he/she wants to withdraw and at last, he/she gets their money. The user does not know about the inner mechanism of the ATM or the implementation of withdrawing money etc. The user just simply know how to operate the ATM machine, this is called abstraction.

using System; 
  
namespace Demoabstraction { 
      
abstract class Shape { 
   
    public abstract int area(); 
} 
  
class Square : Shape { 
  
    private int side; 
  
    public Square(int x = 0) 
    { 
        side = x; 
    } 
      
    public override int area() 
    { 
        Console.Write("Area of Square: "); 
        return (side * side); 
    } 
} 
  
class GFG { 
      
    static void Main(string[] args) 
    { 
          
        Shape sh = new Square(4); 
        
        double result = sh.area(); 
          
        Console.Write("{0}", result); 
   
    } 
} 
} 


**Encapsulation vs Data Abstraction

Encapsulation is data hiding(information hiding) while Abstraction is detail hiding(implementation hiding).
While encapsulation groups together data and methods that act upon the data, data abstraction deals with exposing to the user and hiding the details of implementation.

# Polymorphism

**The word polymorphism means having many forms. In object-oriented programming paradigm, polymorphism is often expressed as 'one interface, multiple functions'.
Polymorphism can be static or dynamic. In static polymorphism, the response to a function is determined at the compile time. In dynamic polymorphism, it is decided at run-time.

**Types of Polymorphism
There are two types of polymorphism in C#:
  
  Static / Compile Time Polymorphism.
  Dynamic / Runtime Polymorphism.
  


![](https://csharpcorner.azureedge.net/UploadFile/ff2f08/understanding-polymorphism-in-C-Sharp/Images/ploymorphism.jpg)
  
  
# Static or Compile Time Polymorphism 

It is also known as Early Binding. Method overloading is an example of Static Polymorphism. In overloading, the method / function has a same name but different signatures. It is also known as Compile Time Polymorphism because the decision of which method is to be called is made at compile time. Overloading is the concept in which method names are the same with a different set of parameters.


public class TestData  
{  
    public int Add(int a, int b, int c)  
    {  
        return a + b + c;  
    }  
    public int Add(int a, int b)  
    {  
        return a + b;  
    }  
}  
class Program  
{  
    static void Main(string[] args)  
    {  
        TestData dataClass = new TestData();  
        int add2 = dataClass.Add(45, 34, 67);  
        int add1 = dataClass.Add(23, 34);  
    }  
} 


# Dynamic / Runtime Polymorphism

Dynamic / runtime polymorphism is also known as late binding. Here, the method name and the method signature (number of parameters and parameter type must be the same and may have a different implementation). Method overriding is an example of dynamic polymorphism.

Method overriding can be done using inheritance. With method overriding it is possible for the base class and derived class to have the same method name and same something. The compiler would not be aware of the method available for overriding the functionality, so the compiler does not throw an error at compile time. The compiler will decide which method to call at runtime and if no method is found then it throws an error.


public class Drawing  
{  
    public virtual double Area()  
   {  
         return 0;  
   }  
}  
  
public class Circle : Drawing  
{  
    public double Radius { get; set; }  
    public Circle()  
    {  
        Radius = 5;  
    }  
    public override double Area()  
    {  
        return (3.14) * Math.Pow(Radius, 2);  
    }  
}  
  
public class Square : Drawing  
{  
    public double Length { get; set; }  
    public Square()  
    {  
        Length = 6;  
    }  
    public override double Area()  
    {  
        return Math.Pow(Length, 2);  
    }  
}  
  
public class Rectangle : Drawing  
{  
    public double Height { get; set; }  
    public double Width { get; set; }  
    public Rectangle()  
    {  
        Height = 5.3;  
        Width = 3.4;  
    }  
    public override double Area()  
    {  
        return Height * Width;  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
  
        Drawing circle = new Circle();  
        Console.WriteLine("Area :" + circle.Area());  
  
        Drawing square = new Square();  
        Console.WriteLine("Area :" + square.Area());  
  
        Drawing rectangle = new Rectangle();  
        Console.WriteLine("Area :" + rectangle.Area());  
    }  
}  


