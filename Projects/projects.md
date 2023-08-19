---
layout: page
title: Projects
permalink: /projects/
---

The following is a summary of my publicly available projects. They are
mainly hosted on [github](https://github.com/fredyouhanaie/)

---
<br/>
# espace

The `espace` project is an Erlang implementation of the Tuple Spaces
(or Linda) paradigm. Details about the paradigm can be found on
Wikipedia for
[Linda](https://en.wikipedia.org/wiki/Linda_(coordination_language))
and [Tuple Spaces](https://en.wikipedia.org/wiki/Tuple_space).

The are two main repositories for the project, the main
[application](https://github.com/fredyouhanaie/espace/) and a
collections of
[examples](https://github.com/fredyouhanaie/espace-examples/)

---
<br/>
# etsmgr

While ETS is a full feature and efficient method of providing shared
data among processes, it is tightly coupled with the process that
created it. This means if that process terminates/crashes, then all
the data will be lost. To overcome this, ETS allows a table to have an
`heir` process, which would take ownership of the table if/when the
main process terminates, so that no data is lost.

`etsmgr` provides a general facilty for an ETS based process to have
an `heir` in the case of the process crashing and restarting. After a
restart, the new process can take back the ownership of the table.

The project can be found on [hex](https://hex.pm/packages/etsmgr) and
[github](https://github.com/fredyouhanaie/etsmgr).

---
<br/>
# portcl

`portcl` helps one create Erlang ports based on Tcl scripts. This
enables an Erlang application to run external Tcl/Tk scripts, such as
a GUI or dashboard, and communicate with it as if it's another Erlang
process.

The project can be found in the [portcl project
repo](https://github.com/fredyouhanaie/portcl/)

---

