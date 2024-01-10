---
layout: post
title: "The GCHQ Christmas challenge"
author: "Fred Youhanaie"
description: "The GCHQ Christmas challenge"
date: 2024-01-04
categories: general
mathjax: true
---

# Introduction

A few weeks ago I came across an
[article](https://www.bbc.co.uk/news/uk-67707647) on the BBC news web
site. It describes the Christmas challenge set by the UK Government
Communications Headquarters (GCHQ) during the run up to
Christmas 2023. The challenge was for school children aged 11-18
years.

The complete details can be found on the GCHQ's [challenge
page](https://www.gchq.gov.uk/news/schoolsxmaschallenge2023).

The fourth puzzle (of seven) caught my eye, since it involves numbers.
So I thought I'll have a go, even though I don't fit the age range
`;-)`

---
<br/>
# The challenge

Here is the fourth puzzle:

$$ MI \times MI = MAA $$

$$ TI + TI = RA $$

$$ DO - SO + TI - MI = RE $$

$$ RE \times RE = \, ?? $$

Where, _Each letter represents a different digit_. We are asked to
find a _one-word answer which can follow Christmas_.
 
---
<br/>
# An example solution

What follows is the tidied up version of my scribbles on the
whiteboard. Of course, there are other ways of solving the puzzle.

From the second equation we can see that $$2 \times TI = RA$$, so
$$RA$$ is an even number, and hence $$A \in \{ 0,2,4,6,8 \}$$

The third equation can be rewritten as follows:

$$ (10D + O) - (10S + O) + (10T + I) - (10M + I) = RE $$

rearranging the above, with each of the pairs of $$O$$s and $$I$$s
cancelling themselves, we end up with the following equation:

$$ 10(D - S + T - M) = RE $$

so, $$E=0$$, and hence $$A$$ is reduced to the set $$\{2,4,6,8\}$$.

Now, back to the first equation, the one that I could have started
with!

$$ (MI)^2 = MAA $$

So, $$MAA$$ is a 3-digit square number with repeated digits on the
right. This restricts the $$MI$$ to the range $$[10 .. 31]$$, so we
have four possibilities: 100, 144, 400 and 900.

We can exclude $$100$$, $$400$$ and $$900$$, since they would imply
that $$A=0$$, but $$0$$ already belongs to $$E$$.

This leaves us with $$MI=12$$ and $$MAA=144$$.

We now have $$E=0$$, $$M=1$$, $$I=2$$ and $$A=4$$.

The second equation can now be written as $$T2+T2=R4$$, so $$2T=R$$,
making $$R$$ an even number, and hence $$R\in\{6,8\}$$. This leads to
$$T\in\{3,4\}$$, but $$4$$ belongs to $$A$$, and so $$T=3$$, and
$$R=6$$.

Now, $$RE=60$$, which leads to the answer as follows:

$$ RE \times RE = 60 \times 60 = 3600 = TREE $$

So, __TREE__ is the _one-word answer which can follow Christmas_.

---
<br/>
# Carrying on ...

The puzzle is solved, but I'm on a roll, so let's solve for the rest
of the letters.

So far we have $$E=0$$, $$M=1$$, $$I=2$$, $$T=3$$, $$A=4$$ and
$$R=6$$.

From the simplified version of the third equation:

$$ 10(D - S + T - M) = RE $$

$$ D - S + 3 - 1 = 6 $$

$$ D - S = 4 $$

From the list of unassigned digits, $$D,S \in \{ 5, 7, 8, 9 \}$$, and
the only pair of digits satisfying the above equation are $$5$$ and
$$9$$, i.e.

$$ D=9, S=5 $$

But, what about $$O$$? Well, we can start with
$$O\in\{7,8\}$$. However, since $$O$$ is only mentioned in the third
equation, in a self-cancelling manner, and with only 9 letters
incorporated in the puzzle, we cannot narrow it down any further!

Have a successful and enjoyable 2024 :-)

---
