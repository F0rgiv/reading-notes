## Objects and Class 

### Class 
A class is a blueprint that can be used to create multiple objects all with the same general requirements. 

### Object 
An object is Java stores fields and methods that can be ran on it. these can be created from a class and will then inherit the properties from that class 

## Base systems 
A base system in regards to numbers is a different way of counting. Base ten is what we are used to but base 16(hex) and 2 (Binary) are often used by computers. In a base system you don’t start over at 10 until you have reached the end of your base. So 10 in base ten is = to 10 but in base 2 would be 3. and in base 16 would be 17. 

# SOLID

## S - Single-responsiblity Principle
>A class should have one and only one reason to change, meaning that a class should have only one job.

if you have a count animals age method it should expect objects that implements the hasAge interface. This way it doesn't have to calculate things like the age of a dog or a tree that may have special calculations.
## O - Open-closed Principle
> Objects or entities should be open for extension but closed for modification.

You class should be perfectly implemented. and thus never needs to be modified. It could however be expanded upon by inheriting from it.
## L - Liskov Substitution Principle
>Let q(x) be a property provable about objects of x of type T. Then q(y) should be provable for objects y of type S where S is a subtype of T.

This is perhaps th most specific to OOP. It essentially means that a child class should be able to stand in for it's parent. For example in an example game if you were to have a parent class creature with a move() method and have a class tree that extends it. In this what you wouldn't do is create treeCantMoveWildEsxception.
## I - Interface Segregation Principle
>A client should never be forced to implement an interface that it doesn’t use, or clients shouldn’t be forced to depend on methods they do not use.

This just means that interfaces shouldn't require methods that may not be needed by all classes that implement them.
## D - Dependency Inversion Principle
>Entities must depend on abstractions, not on concretions.

This essentially means that you shouldn't hard type things that are lowerlevel and may change.