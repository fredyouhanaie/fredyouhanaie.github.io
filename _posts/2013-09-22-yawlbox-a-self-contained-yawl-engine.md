---
layout: post
title: "YAWLbox, a self contained YAWL engine"
author: "Fred Youhanaie"
description: "YAWLbox, a self contained YAWL engine"
date: 2013-09-22
categories: general
Tags: bpm debian linux vagrant virtualbox workflow yawl
---

**Update 2022-10-03** _This article was originally posted on Wordpress. It has
been moved here so that I can clean up the Wordpress account!_

### YAWLbox, a self contained YAWL engine

Following my initial play with YAWL on a Debian box, I have now created a
[Vagrant](http://vagrantup.com) base box that can be downloaded and deployed
from Dropbox.

This can be used as the base platform for experimenting with YAWL4Enterprise.

### Getting Started

To get up and running, and provided that you have Vagrant and VirtualBox already
installed on your server, then the following is all you need:

```
    mkdir yawlbox
    cd yawlbox
    vagrant init yawlbox https://www.dropbox.com/sh/5zembswmxjg94gi/tivEVgfYpz/vagrant-yawlbox-235-20130911.box
    vagrant up
```

You should be able to watch the boot process by connecting to the console with
any RDP client, such as `tsclient` or `xfreerdp`, the VRDE port is the default
3389.

Once, the box is up, you can login with `vagrant ssh`. You should also be able
to connect to YAWL with <http://localhost:8888/resourceService>.

For connecting from the YAWL Editor to the engine you would need to adjust the
hostname and port as above. The change can be done in the Settings drop down
menu of the Editor with the "Engine Connection" and "Resource Service
Connection" menu items.

### The Software Stack

The box consists of the following major components:

  1. Debian 7.1.0 (Wheezy)
  2. PostgreSQL 9.2
  3. Tomcat 7
  4. YAWL Engine 2.3.5

### Box Configuration

#### Debian

The set of packages installed at the base OS layer is minimal, there are no
Desktop, X11 or other software included. The base OS only contains what is
needed for PostgreSQL, Tomcat and YAWL.

#### PostgreSQL

This was installed using the apt repository at postgresql.org. A new database
was created for yawl with owner `postgres` and the password expected by YAWL.

The box uses single NAT interface to connect to the outside world. There are two
port forwarding rules that allow the outside world to connect to the vbox. These
are shown below, and defined in the `VagrantFile` that was created during the
`vagrant init` phase:

Host | Guest | Guest Service
-----|-------|---
2222 | 22    | SSH server
8888 | 8080  | Tomcat service
  
### Important Notes

The vagrant box is intended as a conventient way for anyone interested in
experimenting or building prototypes with the YAWL4Enterprise engine. As it
stands the box needs additional changes, such as the default passwords for
Vagrant, YAWL and Tomcat (see the respective manuals for the details) before the
system is ready for production use.

The box comes with no warranties whatsoever, Do drop me a line if you find this
useful, or experienced problems with the configuration.

---
