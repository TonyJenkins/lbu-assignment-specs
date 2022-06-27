# Introduction to Programming

## Assignment: Task 1

### The Problem

Many organisations are concerned about the security of passwords used for
access to their systems. Users tend to choose passwords that are easy to remember and therefore often
dictionary words. These passwords are easy to crack using simple methods. Requiring users to use a mix of
upper and lower case, special characters, and so on, is better but results in passwords that are difficult
to remember. Users resort to tactics such as always having the upper case character first, which defeats the
object and can make passwords easier to crack.

A better strategy to ensure users choose (and, importantly, can remember) more complex, longer, passwords
is needed. A good approach, which ticks all the requirements, is to chain together three random
words - the resulting password is easy to remember, long, and challenging to crack using brute force methods.

### The Task

Write a program that generates a password consisting of three random words joined together. The words 
can be drawn from a list (or lists) declared as ``CONSTANTS`` in the program. The number of possible 
passwords that can be generated should be at least 500 (which is obviously not enough, but will do for now).

Your program could be used to generate random passwords for, say, a new group of students. So it should start by
prompting the user to enter the number of passwords needed, and should then display a list of that many passwords.
The number should be between 1 and 24 inclusive.

You may ignore the (unlikely) possibility that your program will generate the same random password more than 
once in the provided list.

As a guide, the model solution to this task, laid out as per PEP-8 is 52 lines long. About 22 of these lines are
definitions of the wordlists.

### Examples

The following illustrate what should happen when the program executes in a variety of situations. This version
of the program is taking the three words from three different lists, the aim being to show how it works, and also to 
produce hopefully more memorable passwords. There is no need for your program to follow these scheme.

Here, the program generates a short list of passwords:

```text
Password Generator
==================

How many passwords are needed?: 6

  1 --> boredtealcamel
  2 --> livelygraygorilla
  3 --> willingorangesnake
  4 --> impressivetealgorilla
  5 --> crankynavygorilla
  6 --> calmtealgorilla
```

It is important to check boundary conditions, so we see that the program will generate just one password ...

```text
Password Generator
==================

How many passwords are needed?: 1

  1 --> glumbluekangaroo
```

... but it behaves sensibly if asked to generate a number that is out of the allowed range:

```text
Password Generator
==================

How many passwords are needed?: 0
Please enter a value between 1 and 24.
```

Finally, it also behaves sensibly if the user enters a wildly incorrect value:

```text
Password Generator
==================

How many passwords are needed?: cheese
Please enter a number.
```

