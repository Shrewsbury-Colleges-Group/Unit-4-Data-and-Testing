[🏠 Home](index.md

# C Programming Language 

## Integers

```c
#include <stdio.h>
void main (void)
{
  int a;
  int b = 3;
  int c;
  a = 2;
  c = a + b;
  printf ("The sum of adding %d and %d is %d\n", a, b, c);
}
```

The top three lines inside the main function here are declarations. They tell the compiler that we would like to use variables called a, b and c respectively, and that each one is of type int, i.e. an integer. In the second line, we see an example of an initialisation at the same time as a declaration: this stores an initial value of 3 in the variable b. Note that the values of a and c at this point are undefined; you might assume that a variable which hasn’t had a value stored in it is always 0, but that isn’t the case in C. Before reading the value from a variable or using it in a calculation, you must store a value in it; reading a variable before initialising it is a common error in C.
```c
a = 2;
```
This stores a value of 2 in the variable a, which will now have this value until it’s changed. The reason a is called a variable is that it can vary: you can change its value as often as you like, but only to another integer. The value of a variable can change, but its type is fixed when it is declared.
```c
c = a + b;
```
This line adds a to b, and stores the result in c.
```c
printf ("The sum of adding %d and %d is %d\n", a, b, c);
```
Note the three %d symbols inside the string: these are format specifiers, and they are how you output numbers in C. When the printf function is executed, each %d is replaced by a decimal representation (d for decimal integer) of the variable in the corresponding position in the list after the string. So the first %d will be replaced by the value of a, the second with the value of b, and the third with the value of c. Compile the program above and then run it. You should see this:

The sum of adding 2 and 3 is 5

Floating-point numbers So we can add two integers together; what else can we do? One thing we might want to do is to use floating-point numbers: numbers with a decimal point. These have a different type, called float. Try changing the code above so instead of:
```c
int a;
```
you have
```c
float a;
```
This tells the compiler that a is now a floating-point value, rather than an integer. Compile and run your program. What happens? Oops! That doesn’t look right, does it? What has happened is that, while the maths is still all correct, the printf statement is now wrong; you’re telling it to print a, which is a floating-point value, as a decimal integer. To fix that, change the first %d in the printf function to %f, which is the format specifier for a floating-point number, like this:
```c
printf ("The sum of adding %f and %d is %d\n", a, b, c);
```
Try this: make b a float as well (not forgetting to change its format specifier in the printf), but leave c as an int, and set the two floats to values with decimal points, like this:
```c
float a;
float b = 3.641;
int c;

a = 2.897;
c = a + b;
printf ("The sum of adding %f and %f is %d\n", a, b, c);
```
You’ll see a result like:

The sum of adding 2.897000 to 3.641000 is 6

If you change c to a float, and change the final %d to %f, you’ll find it gives the correct answer.

C obeys the common rules for operator precedence – 
so a = a + 2 * 3 evaluates the multiply first and then adds the result, 6, to a. 
You can use round brackets to change precedence – a = (a + 2) * 3  gives 3a + 6

## Task

[⬅ Lesson 1](Lesson1-Variables.md) | [Next ➡ Lesson 2](Lesson2-Floats.md)
