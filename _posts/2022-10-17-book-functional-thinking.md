---
layout: post
title: "Book review: Functional Thinking"
author: "Fred Youhanaie"
description: "Book review: Functional Thinking"
date: 2014-11-20
categories: general
---

**Update 2022-10-17:** _This is a copy of the review of a book that was kindly
made available by UKUUG._

```
Functional Thinking
Neal Ford
O'Reilly Media
ISBN: 978-1-449-36551-6
164pp.
£25.99
Published: July 2014
```

The preface starts with a history of the book. The author tells us how his
learning process culminated into a series of talks and articles, which now form
the basis of the chapters of the book. Ford also tells us that his "... goal in
the talk, the article series, and this book is to present the core ideas of
functional programming in a way that is accessible to developers steeped in
imperative, object-oriented languages."

Throughout the book we are treated to many examples of functional code snippets,
written in the three JVM (Java Virtual Machine) based languages, Clojure, Groovy
and Scala.

Chapter 1, Why, gently sets the scene for the functional programming concepts
that are to follow. It introduces the virtues of functional programming by
showing some long Java code snippets for solving simple problems, these will
suit the developers steeped in imperative, object-oriented languages.

Chapter 2, Shift, shows us how to shift our thinking from imperative programming
to functional programming. Ford demonstrates this by means of a simple case
study, number classification, deciding if a given integer is a perfect number
not. We are first introduced to a solution in Java (not Java 8), followed by a
much shorter one written in Java 8. We are then introduced to a few common
building blocks that are "ubiquitous" in functional programming. These "Useful
things" are filter, map and fold/reduce, and they are demonstrated using
numerous examples in Clojure, Groovy and Scala.

In chapter 3, Cede, we are shown how to cede control of the low level details
(such as author's least favourite, garbage-collection) to the underlying
run-time system. We are introduced to five ways of ceding control so that we can
spend more time thinking about the main problems. These methods are higher order
functions; closures; currying and partial applications; recursion and streams.
For each of these we are treated to a number of concise examples using the
familiar trio of languages.

As we move through the chapters, Ford delves deeper into the functional
programming paradigm. In chapter 4, Smarter, Not Harder, we learn about
memoization (caching) and lazy evaluation. As usual, there are plenty of
examples to help us work smarter.

Chapter 5, Evolve, demonstrates how one can bend the language so that it fits
the problem being solved, rather than the converse. The main topics covered are
operator overloading and functional data structure. The latter includes pattern
matching and Either/Options classes.

The main theme of chapter 6, Advance, is design patterns. Here we learn more
advanced techniques when programming in functional languages.

In chapter 7, Practical Thinking, Ford covers Java 8, the latest version of Java
that understands concepts of functional programming, as well as some real world
examples such as web frameworks and databases, although not in detail.

The book is concluded with chapter 8, Polyglot and Polyparadigm, where the
author discusses functional programming within the wider world of languages and
programming paradigms.

Overall the book is well written and worth a read for anyone interested in
learning the underlying concepts of functional programming. The presence of Java
examples does suggest that the book is aimed at Java programmers, however, the
non-Java developer should still be able to understand the main message of the
book -- "Paradigm over Syntax". Additionally, one also gets a fair exposure to
the trio of the JVM functional languages used in the text.

---
