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
  printf("char size: %lu bytes\n", sizeof(char));
  printf("int size: %lu bytes\n", sizeof(int));
  printf("short size: %lu bytes\n", sizeof(short));
  printf("long size: %lu bytes\n", sizeof(long));
  printf("float size: %lu bytes\n", sizeof(float));
  printf("double size: %lu bytes\n", sizeof(double));
  printf("long double size: %lu bytes\n", sizeof(long double));
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
  printf("a: %d\n", a);

  #define b 20
  printf("b: %d\n", b);
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
- `?:`: ternary

Bitwise operators:

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
