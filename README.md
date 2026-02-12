# Python Learning

# Functions, Classes and Modules

## Functions

In software development, efficiency, organization, and reusability are extremely important. Python is up to the task, through the use of a tool called functions. By the end of this video, you'll be able to define functions, explain why they are used, and break down the basic syntax of a function. 

Functions are reusable blocks of code that perform specific tasks. They **encapsulate** a set of instructions, allowing you to execute those instructions as many times as you need to in your program, without having to rewrite the code each time. Consider them as sort of mini-programs within the larger program. 

Functions are important because they bring **order**, **efficiency**, and **reusability** to your code, affecting Python programming in four key areas. Functions affect programming in four key areas:

- `Code organization`: code is organized into logical sections, each with specific purpose like chapters in a book.
- `Reusability`: can be called multiple times throughout your program
- `Abstraction`: hiding the intricate details of a task behind a simple interface 
- `Collaboration`: creating modular, self-contained units of code that different team members can work on independently, allowing for parallel development and seamless integration with the final code

## Classes: Blueprint for objects

Classes are digital entities that sum up a set of attributes, or data, and methods, or functions. Together, they define the characteristics and behaviors of objects. They are like a mold or a blueprint you can use to create multiple objects based on the class's data and functionality. For example, in a car plant, the plans for a car model is the class.  

But classes are more than just templates for creating objects. They provide three important abilities for organizing, reusing, and extending your code:

- `Encapsulation` 

Encapsulation is the practice of bundling the data (attributes) and methods (functions) that operate on that data into a single unit called a class. It restricts direct access to some of the object's components, which can prevent unauthorized access and modification.

**Example in Python**

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance  # Public method to access the private attribute
```

- `Inheritance`

 Classes can also inherit attributes and methods from other classes, forming a hierarchical relationship. Inheritance allows a new class (child or derived class) to inherit attributes and methods from an existing class (parent or base class). This promotes code reuse, as the child class can use and extend the parent class's functionality.

 **Example in Python**

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):  # Dog inherits from Animal
    def speak(self):
        print("Dog barks")

dog = Dog()
dog.speak()  # Outputs: Dog barks
```

- `Polymorphism`

 Polymorphism allows objects of different classes to respond to the same function call in their own unique way. Polymorphism allows methods to do different things based on the object it is acting upon, even if they share the same name. This can be achieved through method overriding (inherited classes define methods that have the same name as methods in their parent class) or method overloading (same method name with different parameters).

 **Example in Python**

```python
def make_sound(animal):
    animal.speak()  # Calls the speak method on the animal object

class Cat(Animal):
    def speak(self):
        print("Cat meows")

cat = Cat()
make_sound(cat)  # Outputs: Cat meows
make_sound(dog)  # Outputs: Dog barks
```

# The art of abstraction: Functions and the DRY principle

Imagine constructing a complex machine where every gear, lever, and pulley needs to be crafted from scratch each time you assemble a new component. The inefficiency would be staggering! The software development world faced a similar challenge until the DRY (Don't Repeat Yourself) principle emerged in the 1990s, popularized by Andy Hunt and Dave Thomas in their seminal book, "The Pragmatic Programmer." This principle, along with the powerful concept of functions, serves as the prefabricated parts and assembly instructions, enabling you to build sophisticated software with remarkable efficiency and elegance.

## The DRY principle: A blueprint for code efficiency

The DRY principle is a fundamental philosophy that underpins efficient coding. It advocates for eliminating redundant code, encouraging you to consolidate repetitive instructions into a single, reusable block. This approach isn't merely about saving keystrokes; it's about reducing the surface area for errors, inconsistencies, and maintenance headaches.

## DRY and functions: A match made in coding heaven

Functions are the perfect vehicle for implementing the DRY principle. By encapsulating reusable code within functions, you create a library of tools that can be called on whenever needed. This eliminates the need to reinvent the wheel for every task, saving you time and effort. Not only does this modular approach make your code cleaner and more organized, but it also makes it easier to test and debug each function in isolation. 

## Functions in the modern Python ecosystem

Python's rich standard library and the vast ecosystem of third-party packages are built upon functions. Mastering functions is essential for leveraging these tools to build robust and scalable applications. Python offers a range of features that enhance the power of functions:

- **Decorators**: These special functions modify the behavior of other functions without changing their core logic. For example, a *`@cache`* decorator could store the results of a computationally expensive function, avoiding redundant calculations.

- **Generators**: These special functions produce a sequence of values on demand, improving memory efficiency and enabling elegant solutions for tasks like processing large datasets. A generator function might yield one line of a file at a time, allowing you to process the file without loading it entirely into memory.

- **F-strings**: These formatted string literals provide a concise and readable way to embed expressions directly within strings, making it easier to generate dynamic output within your functions. For instance, you could use an f-string to format a greeting message like this: *`f"Hello, {name}! Today is {date.today()}."`*

- **Type Hints**: These annotations specify the expected data types for function arguments and return values, improving code clarity and enabling static type checking tools to catch potential errors early in the development process. For example, you could define a function like this: *`def calculate_area(length: float, width: float) -> float: ...`*

# Built-in functions in Python

Functions are pre-packaged tools designed to simplify common tasks and streamline coding. They're reusable blocks of code that perform specific tasks, eliminating the need to write code from scratch each time. Python comes preloaded with several built-in functions that offer a range of essential commands and actions for your Python code. 

Some python's built-in functions:

- **print()**: display output on a console or terminal
- **len()**: measure the size or amount of data
- **input(**): gatjers input as a string
- **type()**: determines the data type of a variable or value
- **int()**: converts data to an integer
- **float()**: converts data to a decimal
- **str()**: convert data to a text string

# The LEGB rule: Python's search strategy for variables

When you use a variable in your code, Python embarks on a systematic search to find its value. The search order is described by the LEGB rule:

1. **Local (L)**: Python first checks if the variable exists within the current function or code block.

2. **Enclosing (E)**: If not found locally, it looks in enclosing functions (if you're using nested functions, like Russian dolls).

3. **Global (G)**: Next, it searches the global scope, i.e., variables defined at the top level of your module.

4. **Built-in (B)**: Finally, it checks Python's built-in namespace for pre-defined functions and objects like print, list, etc.

This hierarchical search ensures that Python always finds the most relevant value for a variable, preventing conflicts between variables with the same name at different levels. 

# Building custom classes

## Understanding object-oriented programming

Imagine building a virtual zoo. In an OOP world, each animal wouldn't be a mere collection of characteristics and actions. Instead, each animal would be represented as an object—a distinct instance of a class. A Lion class might have attributes like name, species, age, and mane_color. Its methods could include roar(), hunt(), and sleep(). Similarly, a Monkey class would have its own unique attributes and methods. 

These are the essential components of OOP.

- **Objects**
They represent real-world entities or abstract concepts within your code. Each object is like a self-contained unit with its own data and the ability to perform actions.

- **Classes**
They serve as blueprints or templates for creating objects. Classes define the common characteristics (attributes) and behaviors (methods) that all objects of that class share. 

- **Encapsulation**
This means keeping the details of how an object works hidden inside the object, so you can change those details without breaking the rest of your program. It bundles data and the actions that operate on that data within a class, protecting the internal state of an object. 

- **Abstraction**
This simplifies complex systems by focusing on essential features and interactions, hiding unnecessary details. It focuses on what an object does rather than how it does it, so your code is easier to understand and use.

- **Inheritance**
This lets you create new kinds of objects that are based on existing ones, inheriting their features and adding new ones. This promotes code reuse and models hierarchical relationships. 

- **Polymorphism**
This means you can treat different kinds of objects in a similar way, as long as they share a common interface. This provides flexibility and adaptability in your code. 


## Why classes matter: Beyond basic Python

At a basic level, Python code includes variables, functions, and modules. These are great tools, but as your programs grow, you might feel like you're juggling too many loose pieces. Classes help you tame this complexity by providing a way to organize related data and actions. 

- **Code organization**
Classes create a clear structure for your code. Instead of scattering variables and functions throughout your script, you can group them together within a class, making your code easier to read, understand, and maintain.

For example, imagine you're building a game with multiple characters. Each character might have attributes like name, health, strength, and speed. Without classes, you might end up with a mess of variables like character1_name, character2_health, and so on. With a Character class, you can neatly encapsulate all these attributes within a single object.

- **Reusability**
Once you've defined a class, you can create multiple instances (objects) of that class. This means you don't have to rewrite the same code repeatedly. You can simply create a new object and customize it with specific attributes.

Let's say you have a BankAccount class. You can create objects for different accounts (my_account, your_account, etc.), each with its own balance and transaction history. The underlying logic for depositing and withdrawing money is encapsulated within the class, so you don't have to repeat it for each account.

- **Encapsulation**
Encapsulation in Python is achieved primarily through a convention rather than strict enforcement. It revolves around using a single underscore (_) prefix for attribute names to signal that they are intended for internal use within the class. While Python doesn't prevent direct access to these "private" attributes from outside the class, the underscore serves as a clear indication to other developers that these attributes should be treated as part of the class's internal implementation and not modified directly.

Let's see this in action with a BankAccount example:

```python
class BankAccount:
    def __init__(self, balance):
        self._balance = balance  # Private attribute

    def deposit(self, amount):
        self._balance += amount

    def get_balance(self):
        return self._balance
```

In this example, the **_balance** attribute is marked as private. While you could technically access and modify it directly from outside the class (for example., **my_account._balance = 1000**), doing so would violate the principle of encapsulation. The class provides the** deposit()** and **get_balance()** methods as the proper interface for interacting with the account's balance.

Abstraction
Abstraction empowers you to concentrate on the core functionality of an object without getting entangled in the intricacies of its implementation. Python's abc module (Abstract Base Classes) takes this a step further by enabling you to define abstract base classes. These classes serve as blueprints for other classes, outlining essential methods that concrete subclasses must implement.

Let's see how this works:

```python
from abc import ABC, abstractmethod

class Animal(ABC):  # Abstract base class
    @abstractmethod
    def make_sound(self):
        pass

class Dog(Animal):  # Concrete subclass
    def make_sound(self):
        return "Bark!"
```

In this example, **Animal** is an abstract base class. It declares an abstract method **make_sound()**, which doesn't have a concrete implementation. Any class inheriting from **Animal (like Dog)** must provide its own implementation of **make_sound()**.

## The anatomy of a class: A deeper look

Let's break down the key components of a class with more detailed explanations:

1. **Class definition**

This is the starting point. You use the class keyword followed by the name of your class to define it. By convention, class names are capitalized in Python.

```python
class Car:
    # ... (class contents)
``` 

**2. Attributes (data)**

Attributes are the variables that store the state or characteristics of an object. Think of them as adjectives describing your object. For a Car class, attributes might include **make, model, year, color, and fuel_level**.

```python
class Car:
    def __init__(self, make, model, year, color):
        self.make = make
        self.model = model
        self.year = year
        self.color = color
        self.fuel_level = 100  # Initial fuel level
```

Each **Car** object you create will have its own set of these attributes, allowing you to represent different cars with unique characteristics.

**3. Methods (behaviors)**

Methods are functions defined within the class that operate on the object's data. They represent the actions an object can take. For a Car, methods might include **start_engine(), accelerate(), brake(), and refuel()**.

```python
class Car:
    # ... (attributes)

    def start_engine(self):
        print(f"The {self.year} {self.make} {self.model}'s engine roars to life!")

    def accelerate(self):
        print(f"The {self.color} {self.make} {self.model} picks up speed!")

    def brake(self):
```

Notice how these methods use **self.attribute_name** to access and manipulate the object's attributes. The **self** parameter is crucial – it refers to the specific object on which the method is being called.

**4. The __init__ method: A special constructor**

The **`__init__`** method, often called the constructor, is a special method that Python automatically calls when you create a new object of your class. Its primary role is to initialize the object's attributes with appropriate values. This ensures that every new object starts with a valid state.

```python
class Car:
    def __init__(self, make, model, year, color):
        # ... (initializes attributes)
```

For instance, in our **Car** example, the **__init__** method sets the **make, model, year, and color** attributes based on the values provided when creating a new **Car** object.

## Functional code challenge: A dog can bark!

```python
# Add your class definition here (steps 1-3)
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

    def bark(self):
        print(f"Woof! My name is {self.name} and I'm a {self.breed}.")

# Creating the instance of the Dog class (step 4)
my_dog = Dog("Buddy", "Golden Retriever")
# Directing the dog to bark (step 5)
my_dog.bark()
```