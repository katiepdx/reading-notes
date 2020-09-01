## Quantity Always Trumps Quality FROM https://blog.codinghorror.com/quantity-always-trumps-quality/
- Keep trying! Focus on practice and building rather than if you are building the "right thing". Learn from the past builds. 

## Clean Code: A Handbook of Agile Software Craftsmanship (Chapter 1)
- "...code is really the language in which we ultimately express the requirements." 
- Bad code -- wading -- leads to slow changes and decrease in productivity 
    - Redesign - The Grand Redesign in the Sky -- new team selected -- green fielding (starting over the project) -- the others work on maintaining the old system. New system will eventually replace the old system. 
    - Clean code is cost effective
- Deadlines and Clean code 
- Programmer with "code-sense" can see messy code and see options and other ways. 
- Clean Code: It is efficient, has error handling, and does one thing well. It is focused. Can be read and enhanced by developers other than the original author. Meaningful names. DRY code. 
- Writing code: Programmers are authors, writing for readers. 
    - reading to writing ration 10: 1. Read surrounding code.

## Red, Green, Refactor FROM https://www.codecademy.com/articles/tdd-red-green-refactor
- TDD Test Driven Development -- tests drive the design of the software. 
- Red, Green, Refactor (a framework used to build tests and write implementation code in short development cycles).

**Definitions**
- Red (starting point) - think about WHAT you type
- Green (find a solution) - think about HOW to pass the tests
- Refactor (find a better solution (e.g., faster) but have tests still passing) - think about HOW TO IMPROVE existing implementation 

**Refactoring Questions to get more complete reliable and faster code (FROM ARTICLE)**
- Can I make my test suite more expressive?
- Does my test suite provide reliable feedback?
- Are my tests isolated?
- Can I reduce duplication in my test suite or implementation code?
- Can I make my implementation code more descriptive?
- Can I implement something more efficiently?

## The Clean Code Blog FROM https://blog.cleancoder.com/uncle-bob/2014/12/17/TheCyclesOfTDD.html
- TDD (test driven development) used to be called TFD (test first design) in 1999.

- Second-by-Second -- Nano-cycle.
    - **Three Rules of TDD**
    - Write a failing test
    - Write enough for the test to fail or fail to compile
    - Write just enough production code for test to pass 
- Minute-by-Minute -- micro-cycle (Red-Green-Refactor) 
- Usually used after each complete unit test OR after a dozen-ish TDD cycmes.
    - **RGR Cycle**
    - Create a failing test
    - Make it pass
    - Clean up (make it faster, etc.)

- "Make it work, make it right, make it fast."
- Customers value working software and the ease it can be changed.
- Refactor as you go, not at the end of a project. 

- Decaminute-by-Decaminute: milli-cycle (10-min level)
    - code that solves a specific and general problems. 
    - Check that code is not too specific too fast.

- Hour-by-Hour: Primary Cycle
    - Observe overall system
    - Find boundaries 
