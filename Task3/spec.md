# Introduction to Programming

## Assignment: Task 3

### The Problem

The University of Poppleton enrols many new students at the start of each academic year. One part of this process
involves creating email accounts for every new student. The format of these email addresses follows a particular
pattern, but creating them is a tedious process.

A program is required that will read a list of UCAS numbers (which will become student ID numbers) and corresponding
student names and generate a corresponding list of student emails to be created. Both lists are stored in 
text files.

### The Task

You should create a program that processes a file containing a list of student IDs and names, and produces a second
file containing the student IDs and the email address that should be created.

The names and IDs of new students are received in a file. It looks like this:

```text
c7090763 Velez, Hyun
c6542898 Salsbury, Debra Mary Adele
c9510348 Molina, Arianne Brittney
c5374186 Sampson, Lester
```

The first part is the student ID (at Poppleton that is always the same length). The rest of the line is the student's
name, with family name separated from forenames by a comma. As shown, and as in real life, students have different 
numbers of forenames.

The first part of a student's email consists of their initials, separated by dots, their surname, and four random 
digits (this last is to ensure that all students get unique emails). If a surname contains any non-alphabetic
character (as in "Fink-Nottle", "De Gea", or "O'Mahoney"), those characters are removed.

The second part is the University's domain, which is the same for all students. The result is rendered all in 
lower case. So the above students would be given the following emails (once the domain has been added in):

```text 
c7090763 h.velez6435@poppleton.ac.uk
c6542898 d.m.a.salsbury5250@poppleton.ac.uk
c9510348 a.b.molina2382@poppleton.ac.uk
c5374186 l.sampson3346@poppleton.ac.uk
```

Your program should take a file in the first format, and produce a file in the second. It is safe to assume that
every line in the first file is formatted exactly as expected.

You may ignore the (very remote) possibility of the program generating the same email for two different
students.

Hints:
* The student ID is always at the start of the line and is always the same length. That helps.
* There is only one comma on each line. Taking this with the above observation makes finding the surname easy.
* The initials are the only uppercase letters after the only comma on the line.
* List comprehensions really are your friend in this exercise.

As a guide, the model solution to this task, laid out as per PEP-8 is about 50 lines long. It contains many list
comprehensions.

### Examples

Examples of the correct results are above.

Remember that the student data is stored in a file, and the output is written to another file. The name of
the first file is provided as a command-line argument. The program should therefore behave sensibly if the
file cannot be opened or if the CLA is missing.

```text
$ py email_generator.py 
Error: Missing command-line argument.

$ py email_generator.py missing.txt
Error: Cannot open "missing.txt". Sorry about that.

```

If the program works correctly there should be no output to the screen.


