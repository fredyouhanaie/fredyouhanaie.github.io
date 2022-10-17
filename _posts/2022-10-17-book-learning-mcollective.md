---
layout: post
title: "Book review: Learning MCollective"
author: "Fred Youhanaie"
description: "Book review: Learning MCollective"
date: 2014-11-21
categories: general
---

**Update 2022-10-17:** _This is a copy of the review of a book that was kindly
made available by UKUUG._

```
Learning MCollective
Jo Rhett
O'Reilly Media
ISBN: 978-1-491-94567-4
264pp.
£25.99
Published: August 2014
```

MCollective (M for Marionette, as in puppet!) is a Ruby based software framework
from Puppet Labs for orchestrating configuration changes across Puppet or Chef
based groups of servers.

MCollective communicates with the servers under its control through a message
broker, currently only ActiveMQ and RabbitMQ are supported. The main text along
with the examples only covers ActiveMQ, however, those who prefer RabbitMQ are
provided with guidance in the appendix.

The book is divided into four parts that take the reader from initial
installation of the base software to writing custom plugins.

Part I, Getting Started, takes the reader through the basic installation and
configuration of the software, MCollective and ActiveMQ. It then proceeds to
introduce, with examples, the main command line interface, mco. Although, there
are web clients for the software, we are urged to stay with the command line.

Moving along, we are introduced to the basic workings of MCollective plugins and
agents, as well as brief tips on system level maintenance, such as time sync,
log files, monitoring etc. We are then shown how to configure MCollective with
puppet and chef, yes it does sound like a chicken and egg situation, but the
modules are there for us to use.

Those with a large enterprise installation are catered for in part II, Complex
Installations. The message broker plays a very critical role in an MCollective
based environment. In the next five chapters the reader is given guidance on how
to create broker networks to aid scalability and resilience, as well as using
certificates to make the message broker(s) more secure. Admittedly, I only
skimmed over this part, but I am planning on a more through read at a later
date.

As one can expect with any framework these days, MCollective comes equipped with
the ability to create and use plugins. Part III, Custom Plugins, provides
various examples of plugins and walks the reader through creating and deploying
them.

Finally part IV, Putting It All Together, sums up the preceding chapters,
provides a set of best practices and gives guidance on expanding the MCollective
deployment.

I had a play with the command line examples on a Vagrant/VirtualBox based demo
environment that is provided by Puppet Labs, all good fun, and no surprises
there. The example codes and related data files used in the book have been made
available on Rhett's github repository.

Throughout the book, there are numerous hyperlinks for additional material,
however, they are all Bit.ly shortcuts, which means the reader of the paper copy
of the book will need to type in the links manually. It would be nice if the
author could include these on a web page, or somewhere on the book's github
repository.

Overall, this book covers a lot of ground, going beyond a mere introduction to
the basics of the framework. Although, its main focus is on Puppet and ActiveMQ,
those who prefer Chef and/or RabbitMQ can still benefit from the text.

---
