# refactoring

from: https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec

> Some of the examples took it to the extreme and became very quick at the cost of being totally unmaintainable. There's a middle ground between speed and comprehension and that's where good code lives.

like in many other things coding right the rist time is nececary as if you don't have time to do it right now you never will.
Be sure to include comments in all your code to make it readable and easily understood.

# Pure functions

pure functions are:
- detemanistic: given the same inputs will always return the same
- don't touch anything else. i.e. console log or update a variable somewere else in code.

immutability is refering to anything that can't be modified after it's creation ```const a = {num: 1}``` would not be immutable as ```a.num = 2``` is completely valid. ```const a = Object.freeze({num = 1})``` will however will 'deep freez' the obj making ```a.num = 2``` throw ```Error: Cannot assign to read only property 'num' of object Object```

from: https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0

> Declarative vs Imperative
Functional programming is a declarative paradigm, meaning that the program logic is expressed without explicitly describing the flow control.
Imperative programs spend lines of code describing the specific steps used to achieve the desired results — the flow control: How to do things.
Declarative programs abstract the flow control process, and instead spend lines of code describing the data flow: What to do. The how gets abstracted away.
