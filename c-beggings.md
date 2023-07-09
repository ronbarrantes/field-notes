---
title: Basics of C
date: 2023-07-08T11:00:00.000Z
# image: https://upload.wikimedia.org/wikipedia/commons/a/af/Cara_de_quem_caiu_do_caminh%C3%A3o..._%28cropped%29.jpg
type: Note
tags:
  - C
---

## Basic hello world

A basic c program looks like this:

```c
#include <stdio.h>

int main(void)
{
    printf("Hello, world!\n");
}
```

Every c program starts with `#include <stdio.h>` which includes the standard input and output library.
Every c program has a main function which is `int main(void)`.
The `main()` function is the entry point for a C program.
Sometimes a c program `return 0` at the end but it is not necessary.
Every line of code in c ends with a semicolon `;`.

## Variables and Types

There are a bunch of types in c, they all have different sizes and they are:

- `char`: character and it's size is 1 byte
- `int`: integer number (signed) and it's size is 4 bytes
- `short`: short integer number (signed) and it's size is 2 bytes
- `long`: long integer number (signed) and it's size is 8 bytes
- `float`: floating point number and it's size is 4 bytes
- `double`: double floating point number and it's size is 8 bytes
- `long double`: long double floating point number and it's size is 16 bytes
- `bool`: boolean (bool requires including `stdbool.h` to work) and it's size is 1 byte
- `void`: nothing and it's size is 1 byte

```c
#include <stdio.h>

int main(void)
{
  printf("char size: %lu bytes\n", sizeof(char)); // 1 byte
  printf("int size: %lu bytes\n", sizeof(int)); // 4 bytes
  printf("short size: %lu bytes\n", sizeof(short)); // 2 bytes
  printf("long size: %lu bytes\n", sizeof(long)); // 8 bytes
  printf("float size: %lu bytes\n", sizeof(float)); // 4 bytes
  printf("double size: %lu bytes\n", sizeof(double)); // 8 bytes
  printf("long double size: %lu bytes\n", sizeof(long double)); // 16 bytes
}
```

The sizeof operator returns the size of a type or a variable in bytes.

## Constants

There are two types of constants in c:

- `const`: a constant that can be used in the whole program
- `#define`: a constant that can be used in the whole program

```c

#include <stdio.h>

int main(void)
{
  const int a = 10;
  printf("a: %d\n", a); // 10

  #define b 20
  printf("b: %d\n", b); // 20
}

```

## Operators

There are a bunch of operators in c, they are:

Normal math operators:

- `+`: addition
- `-`: subtraction
- `*`: multiplication
- `/`: division
- `++`: increment by 1
- `--`: decrement by 1
- `%`: modulus

Logical operators:

- `&&`: and
- `||`: or
- `!`: not
- Bitwise operators:

- `&`: bitwise and
- `|`: bitwise or
- `^`: bitwise xor
- `~`: bitwise not
- `>>`: right shift
- `<<`: left shift

Comparison operators:

- `==`: equal
- `!=`: not equal
- `>`: greater than
- `<`: less than
- `>=`: greater than or equal
- `<=`: less than or equal

Assignment operators:

- `=`: assignment
- `+=`: addition assignment
- `-=`: subtraction assignment
- `*=`: multiplication assignment
- `/=`: division assignment
- `%=`: modulus assignment
- `&=`: bitwise and assignment
- `|=`: bitwise or assignment
- `^=`: bitwise xor assignment
- `>>=`: right shift assignment
- `<<=`: left shift assignment

## Conditionals

There are two types of conditionals in c:

- `if`: if statement
- `switch`: switch statement

## Ternary operator

- `?:`: ternary, example `a > b ? a : b`

```c
#include <stdio.h>

int main(void)
{
  int a = 10;
  int b = 20;

  if (a > b)
  {
    printf("a is greater than b\n");
  }
  else if (a < b)
  {
    printf("a is less than b\n");
  }
  else
  {
    printf("a is equal to b\n");
  }

  switch (a)
  {
    case 10:
      printf("a is 10\n");
      break;
    case 20:
      printf("a is 20\n");
      break;
    default:
      printf("a is not 10 or 20\n");
      break;
  }
}

```

## Loops

There are three types of loops in c:

- `for`: for loop
- `while`: while loop
- `do while`: do while loop (it is like while loop but it runs at least once, almost never used)

```c

#include <stdio.h>

int main(void)
{
  for (int i = 0; i < 10; i++)
  {
    printf("i: %d\n", i);
  }

  int i = 0;
  while (i < 10)
  {
    printf("i: %d\n", i);
    i++;
  }

  i = 0;
  do
  {
    printf("i: %d\n", i);
    i++;
  } while (i < 10);
}

```

If you want to break out of a loop you can use `break` and if you want to skip the rest of the loop you can use `continue`.

## Arrays

Arrays are a collection of variables of the same type.

```c
#include <stdio.h>

int main(void)
{
  int arr[10];

  for (int i = 0; i < 10; i++)
  {
    arr[i] = i;
  }

  for (int i = 0; i < 10; i++)
  {
    printf("arr[%d]: %d\n", i, arr[i]);
  }
}

```

## Strings

Strings can be represented as an array of characters.

```c
#include <stdio.h>

int main(void)
{
  char a[10] = "hello";
  char b[10] = {'h', 'e', 'l', 'l', 'o', '\0'};

  printf("a: %s\n", a); // hello
  printf("b: %s\n", b); // hello
}

```

A string is an array of characters that ends with a null character `\0`.
The last character is called a terminator.

To manipulate strings you can use the `string.h` library.
which contains functions such as

- `strlen()`: returns the length of a string
- `strcpy()`: copies a string to another string
- `strcat()`: concatenates two strings
- `strcmp()`: compares two strings

## Pointers

A pointer is a variable that stores the address of another variable.
Probably one of the most confusing things in c.
An address is a location in memory.
Memory is an array of bytes.

Pointers are declared by adding a `*` after the type.
To get the address of a variable you can use the `&` operator.
To get the value of a pointer you can use the `*` operator.

```c
#include <stdio.h>

int main(void)
{
  int a = 10;
  int *b = &a;

  printf("a: %d\n", a); // 10
  printf("b: %p\n", b); // 0x7ffeeb0b4a3c
  printf("*b: %d\n", *b); // 10
  printf("&a: %p\n", &a); // 0x7ffeeb0b4a3c
  printf("&b: %p\n", &b); // 0x7ffeeb0b4a30
}
```

An array is just a pointer to the first element of the array.

```c
#include <stdio.h>

int main(void)
{
  int a[10] = {0,1,2,3,4,5,6,7,8,9};
  int *b = a;

  printf("a: %p\n", a); // 0x7ffeeb0b4a30
  printf("b: %p\n", b); // 0x7ffeeb0b4a30
  printf("a[0]: %d\n", a[0]); // 0
  printf("b[0]: %d\n", b[0]); // 0
  printf("*a: %d\n", *a); // 0
  printf("*b: %d\n", *b); // 0
}
```

And could be iterated over using pointer arithmetic.

```c
#include <stdio.h>

int main(void)
{
  int a[10];

  for (int i = 0; i < 10; i++)
  {
    a[i] = i;
  }

  for (int i = 0; i < 10; i++)
  {
    printf("a[%d]: %d\n", i, *(a + i));
  }

  for(int *p = a; p < a + 10; p++)
  {
    printf("p: %d\n", *p);
  }
}
```

## Functions

Functions are a block of code that can be called from anywhere in the program.

```c
#include <stdio.h>

// a and b are parameters
int add(int a, int b)
{
  return a + b;
}

int main(void)
{
  int a = 10;
  int b = 20;

  // a and b are arguments
  int c = add(a, b);

  printf("c: %d\n", c); // 30
}

```

Functions have a return type and may or may not take parameters.
Functions can be declared anywhere in the program but must be defined before they are called.
Parameters can be pointers.

```c

#include <stdio.h>

// swap the values of two variables
void swap(int *a, int *b)
{
  int temp = *a;
  *a = *b;
  *b = temp;
}

int main(void)
{
  int a = 10;
  int b = 20;

  printf("a: %d | b: %d\n", a, b); // a: 10 | b: 20

  swap(&a, &b);

  printf("a: %d | b: %d\n", a, b); // a: 20 | b: 10
}

```

## Scope

There is global scope and local scope.

```c

#include <stdio.h>

int a = 10; // global scope

int main(void)
{
  int b = 20; // local scope

  printf("a: %d\n", a); // 10
  printf("b: %d\n", b); // 20
}

```

## Type Definitions

You can create your own types using `typedef`.

```c

#include <stdio.h>

typedef int NUMBER;

int main(void)
{
  NUMBER a = 10;

  printf("a: %d\n", a); // 10
}

```

## Enumerations

Enumerations are a list of named integer constants.

```c
#include <stdio.h>

enum Weekday
{
  Monday,
  Tuesday,
  Wednesday,
  Thursday,
  Friday,
  Saturday,
  Sunday
};


int main(void)
{
  enum Weekday today = Monday;

  printf("today: %d\n", today); // 0
}
```

## Enumerated Types

```c
#include <stdio.h>

typedef enum
{
  true,
  false
} BOOLEAN;

int main(void)
{
  BOOLEAN isTrue = true;
  printf("isTrue: %d\n", isTrue); // 0
}
```

## Structures

Structures are a collection of variables of different types.
Structures use the word `struct` to define them.

```c
#include <stdio.h>

struct Person
{
  char *name; // pointer to a string
  int age; // integer
};

// *name is a pointer because strings are arrays of characters and an array is a
// pointer to the first element of the array

int main(void)
{
  struct Person person = {"John", 20};

  printf("name: %s\n", person.name); // John
  printf("age: %d\n", person.age); // 20
}

```

Structures can be declared and defined at the same time.

```c

#include <stdio.h>

struct Person
{
  char *name;
  int age;
} ron, people[10]; // ron is a struct Person, people is an array of struct Person

int main(void)
{
  ron.name = "Ron";
  ron.age = 20;

  printf("name: %s\n", ron.name); // Ron
  printf("age: %d\n", ron.age); // 20

  people[0].name = "John";
  people[0].age = 20;
  people[1].name = "Jane";
  people[1].age = 30;

}

```

## Typedef Structures

You can create your own types using `typedef`.

```c
#include <stdio.h>

typedef struct
{
  char *name;
  int age;
} Person;

int main(void)
{
  Person person = {"John", 20};

  printf("name: %s\n", person.name); // John
  printf("age: %d\n", person.age); // 20
}

```

## Pointers to Structures

```c

#include <stdio.h>

typedef struct
{
  char *name;
  int age;
} Person;

int main(void)
{
  Person person = {"John", 20};
  Person *p = &person;

  printf("name: %s\n", p->name); // John
  printf("age: %d\n", p->age); // 20
}

```

## Unions

Unions are a collection of variables that share the same memory location.

```c
#include <stdio.h>

union Number
{
  int i;
  float f;
};

int main(void)
{
  union Number number;

  number.i = 10;

  printf("i: %d\n", number.i); // 10
  printf("f: %f\n", number.f); // 0.000000

  number.f = 10.5;

  printf("i: %d\n", number.i); // 1092616192
  printf("f: %f\n", number.f); // 10.500000
}

```
