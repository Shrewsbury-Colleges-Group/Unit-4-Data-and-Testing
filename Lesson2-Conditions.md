# Lesson 2: Conditions & Comparisons

In C, controlling program flow based on a test is done with an `if-else` statement.

## ✅ Basic `if-else` example

```c
#include <stdio.h>

int main(void)
{
    int a = 0;

    if (a == 0)
    {
        printf("a is equal to 0\n");
    }
    else
    {
        printf("a is not equal to 0\n");
    }

    return 0;
}
```

If the condition is **true**, the first block runs.  
If it is **false**, the `else` block runs.

---

## ⚠️ `=` vs `==` (very important)

- `=` means **assign a value**
- `==` means **compare values**

### ✅ Correct comparison
```c
if (a == 0)
```

### ❌ Common bug (assignment, not comparison)
```c
if (a = 0)
```

`if (a = 0)` sets `a` to `0`, then checks that value.  
In C:
- `0` = false
- non-zero = true

So this often causes confusing bugs.

> 🔍 **Debug tip:** If conditions behave strangely, check you used `==` not `=`.

---

## ✅ Comparison operators

- `==` equal to
- `!=` not equal to
- `>` greater than
- `<` less than
- `>=` greater than or equal to
- `<=` less than or equal to

---

## ✅ Logical operators

- `&&` AND (both conditions true)
- `||` OR (at least one true)
- `!` NOT (reverses true/false)

Examples:

```c
if (a == 0 && b == 0)   // both are 0
if (a == 0 || b == 0)   // either is 0
if (!(a == 0))          // same as a != 0
```

---

## 🔁 While loop

Use a `while` loop to repeat code while a condition is true.

```c
#include <stdio.h>

int main(void)
{
    int a = 0;

    while (a < 5)
    {
        printf("a is equal to %d\n", a);
        a++;
    }

    printf("a is equal to %d and I've finished\n", a);
    return 0;
}
```

### Shortcuts
- `a++` means `a = a + 1`
- `a--` means `a = a - 1`
- `a += 1`, `a *= 3`, etc. are compound assignments

---

## 🔁 Do-while loop

A `do-while` loop always runs **at least once**.

```c
#include <stdio.h>

int main(void)
{
    int a = 0;

    do
    {
        printf("a is equal to %d\n", a);
        a++;
    }
    while (a < 5);

    printf("a is equal to %d and I've finished\n", a);
    return 0;
}
```

> ⚠️ **Note:** `do-while` needs a semicolon after `while (...)`.

---

## 🧪 Task: Multiple Conditions

**Objective:** Extend logic

Write a program that outputs:
- `"Cold"` if temperature `< 10`
- `"Warm"` if temperature is between `10` and `25`
- `"Hot"` if temperature `> 25`

Use:
- `if`
- `else if`
- `else`

---

## 🧪 Task: Apply Full Logic

**Scenario:** You are designing a temperature monitoring system.

Write a program that outputs:
- `"Cold"` (`< 10`)
- `"Normal"` (`10–25`)
- `"Hot"` (`25–35`)
- `"Danger"` (`> 35`)

Include:
- Correct conditions
- Clear output messages

---

[⬅ Lesson 1](Lesson1-Variables.md) | [🏠 Home](index.md) | [Next ➡ Lesson 3](Lesson3-Loops.md)