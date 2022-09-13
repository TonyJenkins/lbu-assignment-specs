# Introduction to Programming

## Assignment: Task 2

### The Problem

Poppleton Park Run is a monthly family fun run around Poppleton Park. Family groups run, jog, walk, or crawl
around their local park in a generally friendy way. The organisers publish the times of runners
at various points along the course around the park's perimeter. These times are eventually processed and published
on a website.

Automatic timing apparatus positioned around the park uses advanced computer vision techniques to read the numbers 
on each runner's singlet as they pass, and record this along with the elapsed time. These times need to be
processed so that they can be posted on the website. The course is long, so each runner who completes the run
should pass each timing point exactly once.

### The Task

You will write a program that will process the data stream from one of these devices to produce 
some useful statistics. The device is half way round the course, and is is known that every runner will
pass it at most once.

The data stream from the timing apparatus consists of the runner's number (as read from their singlet), and a time
in seconds. A time in seconds is used because runners tend to start at different actual times as they pass a 
designated point. The two elements on the line are separated by two colons (`::`), and each data item 
appears on its own line. So, for example, here:

```text
0012::239
01921::256
```

runner with number `0012` passed 239 seconds after starting, and runner `01921` is slightly slower, passing at
256 seconds.

The data stream ends when the operator powers off the apparatus. Just before shutting down it sends the single 
line `END` to mark the end of the stream.

For the purposes of this simulation you should simply enter
data from the keyboard. Be sure to follow the format exactly.

The required output is:
* The total number of runners who have been seen.
* The average time recorded, rendered in minutes and seconds.
* The fastest time recorded at this point, rendered in minutes and seconds.
* The slowest time recorded at this point, rendered in minutes and seconds.
* The number of the runner recording the fastest time (or the first one to do so, if there are several).

Remember that it is known that each runner will pass just once (there
is no need to handle "repeat appearances" as an error).

Some sample outputs below should make the required output and its format clear. Note especially that the
average time will probably include fractions of a second - it is fine to round these to some close approximation.

For full marks your program should ignore lines of data that do not fit the expected pattern. Some examples of
this are included below.

This is a short race, so it can be assumed that every runner will reach the timing point in less than an hour.

As a rough guide, the model solution to this task, laid out as per PEP-8, is just under 70 lines of code.

*Note: You should write your program using "pure" Python. This means you should not install any additional packages,
and should not make use of any virtual environment.*

### Examples

The following illustrate what should happen when the program executes in a variety of scenarios. 

First, note that the program exits if there is nothing in the data stream.

```text
Park Run Timer
~~~~~~~~~~~~~~

Let's go!

> END
No data found. Nothing to do. What a pity.
```

If the program is run with only one time, obviously that runner will be the fastest, and their time will feature
heavily in the other statistics:

```text
Park Run Timer
~~~~~~~~~~~~~~

Let's go!

> 123::546
> END

Total Runners: 1
Average Time:  9 minutes, 6 seconds
Fastest Time:  9 minutes, 6 seconds
Slowest Time:  9 minutes, 6 seconds

Best Time Here: Runner #123
```

... and we can also illustrate that correct grammar in the output is important. Note the number of minutes:

```text
Park Run Timer
~~~~~~~~~~~~~~

Let's go!

> 124::100
> END

Total Runners: 1
Average Time:  1 minute, 40 seconds
Fastest Time:  1 minute, 40 seconds
Slowest Time:  1 minute, 40 seconds

Best Time Here: Runner #124
```

Finally, a complete run showing how the complete program should look, and also showing some invalid
data lines:

```text
Park Run Timer
~~~~~~~~~~~~~~

Let's go!

> 123::300
> 124::310
> 125::287
> 126::310
> 127::283
> 128::
Error in data stream. Ignorning. Carry on.
> 128::302
> ::
Error in data stream. Ignorning. Carry on.
> END

Total Runners: 6
Average Time:  4 minutes, 58 seconds
Fastest Time:  4 minutes, 43 seconds
Slowest Time:  5 minutes, 10 seconds

Best Time Here: Runner #127
```
