# Polymorphism
Look up the word ***Polymorphism*** online and you will get results like this:

*"the quality or state of existing in or assuming different forms"*

*"the condition of occurring in several different form."*

and even...

*"Polymorphism involves one of two or more variants of a particular DNA sequence"*

**But what has all this got to do with computer science and programming?**

Well, let's start with a simple example using the Python interpreter:

```
>>> 2 + 2
4
```
No surprises there...

How about:

```
>>> "He" + "llo"
'Hello'
```
Interesting, we have used the **+** operator in two different scenarios and it worked in different ways. 

With **integers** provided it added them together and printed the result.

With **strings** provided it concatenated them together and printed the result.

This is ***Polymorphism*** in action!

The **+** operator is taking two different forms depending on what we give it to work with.


## Function Polymorphism
Another example of Polymorphism can be the use of a function that provides different information depending on what type of data we pass it.

```
print(len("Hello")) # String
print(len([1, 2, 3])) # List
print(len({"Name": "Bob"})) # Dictionary

5
3
1
```
When using **len()** function above we get the following:

Data Type: String

Result: Length of String

Data Type: List

Result: Number of items

Data Type: Dictionary

Result: Number of keys

Again, the function behaves differently depending on data type provided, another example of ***Polymorphism***.


## Method Overriding
Method overriding occurs when we have a method that exists in both the **Parent** class and the **Child** class with ***the same name***

Example:
```
class Parent:
    
    def printMe(self):
        return "I am instance of Parent class"

class Child(Parent):

    def printMe(self):
        return "I am instance of Child class"
```
Both classes have a ***printMe()*** method which returns a string.

Let's create some instances and work with them:

```
p1 = Parent()
c1 = Child()

p1.printMe()
>>> 'I am instance of Parent class'

c1.printMe()
>>> 'I am instance of Child class'
```

Python defaults to calling the ***printMe()*** method of the instance type you have created.

It doesn't have a problem with you having duplicate method names in sub-classes.

This is ***Method Overriding***

**Question:** What happens if you don't provide a method with the same name in the sub-class?

Example:

```
class Parent:
    
    def printMe(self):
        return "I am instance of Parent class"

class Child(Parent):
    pass
```

```
p1 = Parent()
c1 = Child()

p1.printMe()
>>> 'I am instance of Parent class'

c1.printMe()
>>> 'I am instance of Parent class'
```
Python calls the method ***printMe()*** from the Parent class.

## Method Overloading
Method Overloading occurs when we have two methods with ***the same name*** in our two classes ***BUT*** they have different ***Method Signatures***.

***Method Signatures*** are the arguments we specifiy for the method.

For example, let's say you have two methods called printMe (below):

```
printMe(greeting) # One argument
printMe(greeting, name) # Two arguments
```

Because the second printMe() method has a different number of arguments to the first this would be considered ***overloaded***.

Having different data types in the two methods could also be an example of ***overloading***.

Python doesn't support Method Overloading (you can sort of do it but not really) so nothing to see here but if you want to look at an example in **Java** [be my guest](https://www.javatpoint.com/method-overloading-in-java).