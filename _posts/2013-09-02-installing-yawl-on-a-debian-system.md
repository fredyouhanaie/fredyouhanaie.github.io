---
layout: post
title: "Installing YAWL on a Debian System"
author: "Fred Youhanaie"
description: "Installing YAWL on a Debian System"
date: 2013-09-02
categories: general
Tags: bpm debian linux workflow yawl
---

**Update 2022-10-03** _This article was originally posted on Wordpress. It has
been moved here so that I can clean up the Wordpress account!_

## What is YAWL?

[YAWL](https://yawlfoundation.github.io/) (Yet Another Workflow Language) is an
open source (LGPL) workflow system that started life about 10 years ago. You'll
find a good deal of documentation and examples at their web site.

This post is intended for those who have already discovered YAWL and would like
to try YAWL4Enterprise on a Debian GNU/Linux system.

The YAWL documentation describes how to install YAWL4Enterprise on an MS windows
based system, but it gives very brief guidance on how to do the same on other
systems such as Linux.

The following is based on my experience of installing and configuring YAWL on a
freshly created Debian 7.1.0 (Wheezy) system. These notes should be taken as
complementary to those in the manual.

## Summary of the steps

Note that these instructions are for installing YAWL on a fresh system, or at
least one that is not running postgresql or tomcat.

You should certainly NOT attempt this on a production system, or one where you
are already running tomcat or postgresql services, unless you already know what
you are doing!

You should also be familiar with the installation chapter in the
[User Manual](http://yawlfoundation.org/pages/support/manuals.html),
as well as basic Debian software installation commands, such as apt-get.

### Base system

Install Debian 7.1.0 on a system, either bare metal or a virtual machine. When
using the interactive installer it is sufficient to only select the "standard
system utilities" and the "ssh-server" packages.

### PostgeSQL

Install PostgreSQL. The latest stable version available from the Debian
repository is 9.1, however, you can install the latest stable version (currently
9.2) using the instructions on the
[PostgreSQL web site](http://www.postgresql.org/download/linux/debian/), if you
wish.

Configure PostgreSQL. As user "postgres", "createdb yawl", we only need the
empty database, YAWL will create the tables on start-up. Change the database
user password to "yawl", NOT the Linux one! This can be done using the
"\password" command in psql.

### Tomcat

Install Tomcat. The package "tomcat7" should be sufficient, however, you may
also want to install "tomcat7-admin", which provides admin access to the Tomcat
applications/services.

Configure Tomcat. See the user manual for details. Note that the configuration
files are in "/etc/tomcat7".

### Additional Packages

If you've opted for minimal base system, you will need to install two more
packages, "unzip" will be needed to unpack the YAWL software, and "ttf-dejavu"
for the fonts used by YAWL.

### YAWL

Install YAWL. The YAWL zip files should be unpacked in
"/var/lib/tomcat7/webapps". Once YAWL is unpacked in the webapps directory,
restart Tomcat. It may take about a minute or so for the YAWL services to
complete initialization. The log files are in "/var/log/tomcat7", should there
be a need for any troubleshooting.

If you encounter out of memory errors, follow the instructions in the manual,
but note that the file "setenv.sh" should be put in "/usr/share/tomcat7/bin".

## General

The above steps should get you up and running with the minimum steps. For the
rest you should be able to continue with the instructions in the user manual.

If you are happy to install/run YAWL on an existing server, then you should skip
the OS install step, and only install the prerequisite package if not already
installed.

For non-Debian systems, the steps should be very close to those above, although
the paths may be different.

---
