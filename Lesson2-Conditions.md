# Lesson 2 Conditions and Comparisons

In C, the mechanism for controlling flow based on testing a condition is the if-else statement. Here’s a simple example:
```c
#include <stdio.h>
void main (void)
{
  int a = 0;
  if (a == 0)
  {
    printf ("a is equal to 0\n");
  }
  else
  {
    printf ("a is not equal to 0\n");
  }
}
```
Here, the keyword if is followed by a test enclosed in round brackets, in this case (a == 0). If the test evaluates as true, the operations enclosed by the curly brackets after the test are executed. This example also shows the use of an else clause. At the end of the curly brackets around the operations which you want to execute if the test is true, there’s an else followed by another set of curly brackets; these contain the operations you want to execute if the original test evaluated as false. Try compiling the code above, and change the value with which a is initialised to make sure it does what you expect.

## = or ==

That’s all fine, but what’s this a == 0 all about? Surely if we want to know whether a is equal to 0, we just put a = 0. Why the two equals signs? Well, try replacing the double equals sign with a single equals and see what happens.

This is a very important aspect of C syntax, and a common source of bugs. The equals sign is used for two different things: one is to assign a value to a variable, whereas the other is to test whether a variable is equal to a value. A single equals sign (=) assigns a variable; a double equals sign (==) tests a variable. So the statement…
```c
if (a == 0)
```
…tests to see if a is equal to 0. If it is, then the test evaluates as true, and the code immediately after the if is executed. But the statement…
```c
if (a = 0)
```
…doesn’t compare a against 0 at all: it just sets a to 0. So how does the compiler decide what to do next? In this case, it just looks at the value of what’s in the brackets; you’ve set a to 0, so the value inside the brackets is 0. 

In C, a value of 0 is equivalent to false, and a non-zero value is equivalent to true. So by replacing the double equals with a single equals, you’ve changed the value of a, and then you look to see if the value you’ve set a to is equivalent to true or false; neither of which were what you wanted to do! If a C program is behaving strangely, check very carefully that all your tests are actually tests and not assignments: this is a very easy mistake to make. 

So == is the test to see if a value is equal to another one. There are other useful symbols that can be used in a test. The symbol !=, for example, means ‘is not equal to’. The mathematical operators > and < are used to test for ‘is greater than’ and ‘is less than’ respectively, and they can also be combined with an equals sign to give >= and <=, the tests for ‘is greater than or equal to’ and ‘is less than or equal to’. 

You can combine tests with logical operators. The symbol && is a Boolean AND (i.e. test whether both sides are true), and || is Boolean OR (i.e. test if either side is true). So, to execute code only if both a and b are 0, you would use if (a == 0 && b == 0). To check if either a or b is 0, you use if (a == 0 || b == 0). 

Similarly, you can use the operator ! as a Boolean NOT to invert the result of a test, so if (!(a == 0)) is the same as if (a != 0).
```c
#include <stdio.h>
void main (void)
{
	int a = 0;
	if (a == 0)
	{
	printf (“a is equal to 0\n”);
	}

	else
	{
	printf (“a is not equal to 0\n”);
	}
}
```
## Looping 
The if statement is useful for making a single decision, but what if you want to do something repeatedly until a test is true or false? We use a while loop for this, and here’s an example:
```c
#include <stdio.h>
void main (void)
{
int a = 0;
while (a < 5)
  {
    printf ("a is equal to %d\n", a);
    a++;
  }
  printf ("a is equal to %d and I've finished\n", a);
}
```
This is very similar to an if statement, but the code in the curly brackets is executed repeatedly for as long as the test in the round brackets is true, not just once. 

So in our example code, a is initialised to 0. We enter the while loop, and test to see if a is less than 5, which it is, so the code inside the curly brackets is executed. The value of a is printed out, then we have one of C’s useful shortcuts to save too much typing... 

a++ is the same as a=a+1; the double plus means ‘add one to this variable’. Similarly, a-- means ‘subtract one from this variable’; these are very commonly used to count the times around a loop. The notation a+=1 can also be used to add a value to a variable; this also works for other arithmetic operators, so a*=3 multiplies a by 3, and so on. 

In the while loop, each time the code in the curly brackets has been executed, the test in the round brackets is repeated; if it’s still true, the loop code is repeated again. As soon as the test is false, execution continues with the line after the closing curly bracket. 

Sometimes, we might want a loop which always runs at least once before a test is made. We do this with a small modification to the syntax to create a do-while loop:
```c
#include <stdio.h>
void main (void)
{
int a = 0;
do
  {
    printf ("a is equal to %d\n", a);
    a++;
  } 
while (a < 5);
  printf ("a is equal to %d and I've finished\n", a);
}
```
The keyword do now goes before the curly bracket, and the while and test go after the closing curly bracket. When this runs, the code in the loop always executes once before the test; you can test this by running both the loop examples above with a initialised to 5 rather than 0, and seeing how the behaviour differs.

## Note:
Unlike the test in an if statement or a while loop, you need to put a semicolon after the test in a do while loop. This indicates the end of the loop code; in a while loop, the loop code doesn't end until the last statement inside the curly brackets.

## Task

