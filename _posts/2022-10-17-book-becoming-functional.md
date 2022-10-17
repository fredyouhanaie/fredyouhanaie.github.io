---
layout: post
title: "Book review: Becoming Functional"
author: "Fred Youhanaie"
description: "Book review: Becoming Functional"
date: 2014-11-18
categories: general
---

**Update 2022-10-17:** _This is a copy of the review of a book that was kindly
made available by UKUUG._

```
Becoming Functional
Joshua Backfield
O'Reilly Media
ISBN: 978-1-449-36817-3
134pp.
£19.50
Published: July 2014
```

The subtitle of the book is "steps for transforming into a functional
programmer", however, from the start one realises that the object of this
transformation is "a Java programmer".

The entire book is based on an example which is the legacy Java code of a
fictional company named XXY, and the reader is gradually introduced to the
elements of functional programming by way of transforming the Java code into the
Scala and/or Groovy equivalents.

Chapter 1 gives an overview of functional programming in terms of the seven
concepts: First-Class Functions; Pure Functions; Recursion; Immutable Variables;
Strict and Nonstrict Evaluation; Statements; Pattern Matching. These concepts
are then described, using Java examples, in the seven chapters that follow the
overview.

In chapters 2 and 3, first-class and pure functions are introduced by means of
transforming Java examples into more functional looking variants. In chapter 2
we learn about lambdas and closures, while chapter 3 demonstrates how to avoid
side effects in order to create Pure Functions. Here, we encounter some Groovy
(the language) examples.

Chapter 4 demonstrates how immutable variables can be implemented using a series
of transformations of the standard example Java codes. This is followed by a
chapter on recursion. Tail recursion, an important concept in functional
programming, is also covered here. This is the chapter where we start learning
about Scala.

Chapter 6 is about strict and non-strict (lazy) evaluation. The concepts are
explained using examples in Groovy and Scala. The advantages and disadvantages
of each of the methods is also covered.

In chapters 7 (Statements) and 8 (Pattern Matching) we are treated to more Scala
code. Chapter 7 shows how one can obtain a more concise code since every
statement in a functional language returns some value. This is demonstrated by
means of transforming the example Java code to its Scala equivalent. This leads
nicely to the chapter on pattern matching, which contains plenty of example
codes in Scala (and no Java!)

In chapter 9, Functional OOP, we are treated to more examples in Scala and shown
how we can got about taking advantage of both worlds.

The book is short and concise. The text is well written and the structure makes
it easy to get the gist of the contents. Most of the chapters have a conclusion
section that sums up what has been covered in the chapter, including the
"Conclusion" chapter, but the recursion stops there!

If you are a Java programmer and have not had any exposure to functional
programming, then you can benefit from this book. On the other hand, if you have
had some exposure to functional programming, but programming in Java is not
second nature to you, then you may find the Java examples rather distracting.

---
