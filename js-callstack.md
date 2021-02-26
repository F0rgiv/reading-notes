# Call stack

The below is from MDN and while a complete copy an excelent description that really helps ones mind understand this.

https://developer.mozilla.org/en-US/docs/Glossary/Call_stack

> A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.
> - When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
> - Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
> - When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
> - If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.



---

IF a function call results in an a recursive loop this will create a stack overflow error.
The call stack is completely synchronous and single threaded.

Cheatsheet for js errors: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors

Brake points are a great way of debugging as it enables you easily see values and test lines of code at any point.
