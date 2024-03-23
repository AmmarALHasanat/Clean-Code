# Code smell

**the traces in the code that indicates a deeper problem in the application or codebase.**

## Bloaters

**Methods and classes that have grown to a lot of lines of code that can difficult to handle.**

To solve a problem in most case, we can use single responsibility principleto solve a provlem in most case we can use single responsibility principle.

### Long Method

Signs and Symptoms: A method contains too many lines of code.

#### Treatment:

* Extract Method
* Replace Temp with Query
* Introduce Parameter Object
* Preserve Whole Object

### Large Class

**Signs and Symptoms: A class contains many fields/methods/lines of code.**

#### Treatment:

* Extract Class
* Extract Subclass
* Extract Interface

### Primitive Obsession

**Signs and Symptoms: the excessive use of primitive data types in programming without utilizing custom data types tailored for the intended purpose. A class contains many fields/methods/lines of code.**

#### Treatment:

* Replace Data Value with Object.
* Replace Type Code with Subclasses.
* if use in method Replace these parameters with an object. "Introduce Parameter Object " or Preserve Whole Object.
* Replace Type Code with Class, Replace Type Code with Subclasses or Replace Type Code with State/Strategy.

#### Examp in project: when fix webhooks for platforms.

### Long Parameter List

**Signs and Symptoms: More than three or four parameters for a method.**

#### Treatment:

* Replace Parameter with Method Call
* Introduce Parameter Object
* Preserve Whole Object

### Data Clumps

**Signs and Symptoms: recurring groups of related data in different parts of the codebase.**

#### Treatment:

* Replace Parameter with Method Call
* Introduce Parameter Object
* Preserve Whole Object

#### Examp in project: Objects like contacts or deals.

<br/><hr/>

## Object-Orientation Abusers

**All these smells are incomplete or incorrect application of object-oriented programming principles.**

### Switch Statements

**Signs and Symptoms:You have a complex `switch` operator or sequence of `if` statements.**

#### Treatment:

* Extract Method and then Move Method.Replace Parameter with Method Call
* Introduce Parameter Object
* Preserve Whole ObjectTemporary Field

#### When to Ignore:

* When a `switch` operator performs simple actions, there’s no reason to make code changes.
* Often `switch` operators are used by factory design patterns.
* Replace Type Code with Class, Replace Type Code with Subclasses or Replace Type Code with State/Strategy.
* Replace Conditional with Polymorphism.

### Temporary Field

**Signs and Symptoms: Temporary fields get their values (and thus are needed by objects) only under certain circumstances. Outside of these circumstances, they’re empty.**

#### Treatment:

* Extract Class and Replace Method with Method Object.
* Introduce Null Object

### Refused Bequest

**Signs and Symptoms: If a subclass uses only some of the methods and properties inherited from its parents, the hierarchy is off-kilter."superclass and subclass are completely different"**

#### Treatment:

* Replace Inheritance with Delegation.
* If inheritance is appropriate remove inappropriate methods from subclass, add common methods to superclass , and Extract Superclass

### Alternative Classes with Different Interfaces

**Signs and Symptoms: Two classes perform identical functions but have different method names.**

#### Treatment:

* Rename Methods to make them identical in all alternative classes.
* Move Method, Add Parameter and Parameterize Method to make the signature and implementation of methods the same.
* Preserve Whole ObjectTemporary Field

#### When to Ignore:

Sometimes merging classes is impossible or so difficult as to be pointless.

#### Examp in project: create Objects, and (rename , put) common methods form Contact.

<br/><hr/>

## Change Preventers

**if you need to change something in one place in your code, you have to make many changes in other places too.**

### Divergent Change

**Signs and Symptoms: when a single class is frequently modified for different reasons, such as adding new features or accommodating changes in requirements.**

#### Treatment:

* Split up the behavior of the class via Extract Class.
* Extract Superclass and Extract Subclass.

### Shotgun Surgery

**Signs and Symptoms: Making any modifications requires that you make many small changes to many different classes. Reasons (A single responsibility has been split up among a large number of classes)**

#### Treatment:

* Use Move Method and Move Field to move existing class behaviors into a single class.
* Inline Class

### Parallel Inheritance Hierarchies

**Signs and Symptoms: Whenever you create a subclass for a class, you find yourself needing to create a subclass for another class.**

#### Treatment:

* You may de-duplicate parallel class hierarchies in two steps. First, make instances of one hierarchy refer to instances of another hierarchy. Then, remove the hierarchy in the referred class, by using Move Method and Move Field.
