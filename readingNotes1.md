# Readings 1

## Debugging
### First analyze the problem
- what do i expect it to do?
- what is it actually doing?
  - is a variable wrong?
  - is it crashing>
  - is it showing something unexpected like `object`?
- keep these in mind

### Then use the debug tools
- run through in debug mode `F5`
- do you get an exception?
  - what does the exception say
- step through to see when the result or values change from what is expected
  - you can click on variables to see their value at a given point when stepping through

### Ask for some help
You could also explain your problem to a friend, coworker, or fellow student and they may be able to give some insight.
Even if they can't just explaining the issue can lead to you understanding the issue much better.

For large projects code review from other sources is a must. 
The Therac-25 is a great example of what not to do as it was programmed all in house with no code review which lead to a multitude of errors, some of which resulted in death.
[Wikipedia](https://en.wikipedia.org/wiki/Therac-25)

## Exceptions
If you know a section of code could give an exception then surround it in a `try-catch` block.
This runs a segment of code and the catch block will grab any exceptions so they can behandled then and there instead of crashing.
After catching the excpetion you should probably console log the information it contains by using it's native methods.
If you don't want to handle it yet you can rethrow the exception for something else to catch.
```
try {
  somethingThatMightErr();
} catch(Exception e) {
  handleExeption(e); // you would make the handleExpection function
  // or throw e; if you don't want to handle it yet
}
```
When you handle an exception try to give as much information about the exception as possible such as:
- the type of exception
- the exception itself
- the method it was caused in

The Therac-25 suffered from bad error handling as it would show,
>Several error messages merely displayed the word "MALFUNCTION" followed by a number from 1 to 64.
[Wikipedia](https://en.wikipedia.org/wiki/Therac-25)

It is very important to think ahead and also to test if any errors could show up in your software. 
Even in places where you know it works for certain sets of input.
The rocket Ariane 5 initial launch was a falure to to a software issue where a floating point number coulnt be coverted to an integer as it was too large.
[Wikipedia](https://en.wikipedia.org/wiki/Ariane_5)

