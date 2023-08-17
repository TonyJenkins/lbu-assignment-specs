# Introduction to Programming

## Assignment: Task 2

### The Problem

A kindly cat owner has installed a cat house in his garden. This acts as a refuge for his feline friend should the creature be caught outside in inclement weather when its human servant is unavailable to open the back door.

The cat house contains a small camera, along with a motion detector and an RFID reader that detects a chip in the cat's collar. This is connected up to a laptop, which creates a log of when the cat enters and leaves the shelter. If the chip is not detected, but motion is, it can be assumed that the neighbour's cat has trespassed into the shelter. In this case, a loud siren plays automatically, and jets of water are directed at the intruder.

### The Task

The laptop stores a data stream that can be analysed. It records when a cat entered, when it left, and whether the cat was an intruder. Times are stored as minutes, with a start of midnight. So midnight is represented as zero, 1am is 60, and 9:30am would be 600 (9 x 60 + 30). There is one file a day.

The cat house is small, so there can only be one cat in it at a time. It is often empty (the cat likes to bask on the roof).

The format of the file is as follows.

```text
OURS,600,630
THEIRS,700,701
OURS,842,900
THEIRS,1000,1001
THEIRS,1010,1011
END
```

So we see that the cat entered the house at 9:30am (time 600), and stayed for 30 minutes. A different cat entered at time 700 ... Hold on:

```text
>>> 700 // 60
11
>>> 700 % 60
40
```

which is 11:40, and swiftly left.

The data stream ends ``END``. It is safe to assume that the file is always in this format.

The required output is:
* The total number of times the cat has entered the house.
* The number of times intruding cats have been doused with water.
* The total time spent in the house by the cat.
* The average duration of each visit, the duration of the longest visit, and the duration of the shortest visit.

### Examples

The following illustrate what should happen when the program executes in a variety of scenarios. 


