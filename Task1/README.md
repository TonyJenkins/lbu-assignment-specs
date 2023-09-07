# Introduction to Programming

## Assignment: Task 1

### The Problem

Pizza takeaways are popular. There is a wide variety from which to choose, ranging from international franchises to small local businesses.

For reasons that are not clear, the pricing of takeaway pizzas is very rarely straightforward. Prices vary depending on many factors. These might include the number ordered, the time of day the order is placed, the day of the week itself, whether the order will be collected, or even whether an app was used to place the order.

A computer program is often the only practical way to work out the price of a takeaway pizza order.

### The Task

In this task you will develop a program that will assist one Pizza Provider to calculate how much to charge a customer for a given order. The rules to be applied are set out below.

Beckett Pizza Plaza (henceforth *BPP*) offers a range of pizzas for collection or delivery. In common with all others in the marketplace, the pricing of individual pizzas is simple, but things become more complex with a complete order. At present the price structure is as follows:

* Every pizza from BPP costs £12. This is irrespective of toppings, crust, and so on.
* A 50% discount applies to all pizza prices on Tuesdays. This discount does not apply to any delivery cost (see below).
* Delivery costs £2.50, *unless* there are five or more pizzas in the order, in which case it is free. There is no cost for collection.
* A discount of 25% of the total price (pizzas plus delivery, if required) is applied if the customer orders via the new BPP App. This is *in addition to* the Tuesday Discount, and is applied *after* that discount.

Your program will need to gather various information about the order, and will then calculate and display the total price.

**It will be sufficient to ask the user to enter whether or not it is Tuesday. There is no need to try to work this out from the system clock.**

All money amounts should be displayed as pounds and pence; that is with two decimal places. Any reasonable way to round odd amounts is fine.

Your program should follow good programming practice. This includes choosing meaningful identifiers for variables and constants, and using functions to avoid code duplication.

### Examples

The following illustrate what should happen when the program executes in a variety of situations. The program is running within an IDE. The values entered by the user are after the ``?`` character.

It is not sensible to include all the combinations here, but there should be enough examples to illustrate the key points.

The dialogue here is only an example. You can use any dialogue that is suitably neat, but you should be sure to validate whatever input values you need.

Here is a simple order for collection, not on a Tuesday, made over the phone.

```text
BPP Pizza Price Calculator
==========================

How many pizzas ordered? 4
Is delivery required? n
Is it Tuesday? n
Did the customer use the app? n

Total Price: £48.00.
```

Here is the same order, with delivery required. So the delivery charge is added in.

```text
BPP Pizza Price Calculator
==========================

How many pizzas ordered? 4
Is delivery required? y
Is it Tuesday? n
Did the customer use the app? n

Total Price: £50.50.
```

This canny customer placed the same order, but used the app to score a 25% discount. Note there is some rounding here (the actual value is ``37.875``).

```text
BPP Pizza Price Calculator
==========================

How many pizzas ordered? 4
Is delivery required? y
Is it Tuesday? n
Did the customer use the app? y

Total Price: £37.88.
```

Finally, collecting pizzas on a Tuesday, having used the app, really is the way to go.

```text
BPP Pizza Price Calculator
==========================

How many pizzas ordered? 4
Is delivery required? n
Is it Tuesday? y
Did the customer use the app? y

Total Price: £18.00.
```

And the program should handle erroneous input, for example:

```text
BPP Pizza Price Calculator
==========================

How many pizzas ordered? -1
Please enter a positive integer!
How many pizzas ordered? cheese
Please enter a number!
How many pizzas ordered? banana
Please enter a number!
How many pizzas ordered? 4
Is delivery required? dunno
Please answer "Y" or "N".
Is delivery required? Y
Is it Tuesday? wednesday
Please answer "Y" or "N".
Is it Tuesday? N
Did the customer use the app? Y

Total Price: £37.88.
```
