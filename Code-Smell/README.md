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
