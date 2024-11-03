# Clean-Code

> Clean code refers to writing code that is easy to understand, maintain, and modify. "fight technical debt"

### Clean code benefits:

* Clear for other programmers
* doesn’t contain duplication
* Clean code has a less code
* passes all tests
* easier and cheaper to maintain

# Technical debt

> Technical debt is a concept in the software development process that refers to the costs resulting from taking shortcuts or implementing non-optimal solutions during the development process.

### Causes of technical debt:

* **Bsiness pressure:** Features released before completion for some reason.
* **Lack of understanding of the consequences of technical debt.**
* **Failing to combat the strict coherence of components:** Any change in some a part of the project affects the other part of the project
* **Lack of tests:** This means more bugs and other problems
* **Lack of documentation:** Slowing down the project development process or delaying new people’s understanding of the project
* **Lack of interaction between team members:** People will end up working with an outdated understanding of processes and information about the project.
* **Long-term simultaneous development in several branches**
* **Delayed refactoring:** When requirements change constantly, some parts of the code may become outdated, or when writing new code, old parts may need to be modified. Delay in this increases the cost of refactoring.
* **Lack of compliance monitoring:** when everyone working on the project writes code as they see fit
* **Incompetence:** When a developer writes bad code

# When to refactor


#### Rule of Three

1. When you’re doing something for the first time, just get it done.
2. When you’re doing something similar for the second time, cringe at having to repeat but do the same thing anyway.
3. When you’re doing something for the third time, start refactoring.

> When writes same code every time

#### When adding a feature

* If you have to deal with someone else’s dirty code, try to refactor it first.

#### When fixing a bug

#### During a code review

# How to refactor

* #### The code should become cleaner.
* #### New functionality shouldn’t be created during refactoring.
* #### All existing tests must pass after refactoring.

