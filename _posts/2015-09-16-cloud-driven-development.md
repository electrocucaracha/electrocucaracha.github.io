---
layout: post
title:  "Cloud-Driven Development"
---
Even today, environments dedicated entirely to support projects during its
development and/or testing phases are under-utilized during non-working
hours. No matter the use of those servers they're always consuming energy for
its operation, resulting in infrastructure operating costs for the company.
Adapting software development processes in such a way that can only consume
resources(servers) on demand during development and testing phases can
significantly reduce costs and prevents information loss for an application.

## Problem/Opportunity

The process to create and configure environments is traditionally assigned to a
single person and managed through a ticketing system whereby time and effort
are estimated. In other words, the operator or responsible will only have
predefined period of time for setting up an environment requested by an end
user(e. g. developer, tester). This is why provisioning activities are made
only once and usually at the beginning of a project. But the working
environment creation can be the easiest way to do a sanity check of the whole
project and verify its correct functionality, this process must not have
workarounds or undocumented steps.  Additionally, the earlier detection of
defects can simplify its resolution and reduce costs for the software
development process. Therefore, creating working environments periodically can
help to detect defects no matter the stage of the project.

Development and Testing environments are mainly used during working hours,
meaning that almost two-thirds of their time the servers are in a state of
inactivity. Simple acts such as turning servers off when they are not used can
reduce infrastructure operating costs. In order to make this a new habit, these
actions must be done on a regular basis.

## Solution

Vagrant provides easy to configure, reproducible, and portable work environments
built on top of industry-standard technology and controlled by a single
consistent workflow to help maximize the productivity and flexibility of you
and your team. Vagrant has the ability to manage virtual machines such as
VirtualBox, VMware, KVM, and others. Lastly, boxes are the package format for
Vagrant environments.

A base box is created from a minimal Operative System with the minimum set of
software required for Vagrant to function.  Vagrant uses industry-standard
provisioning tools such as shells scripts, Chef or Puppet to automatically
install and configure software on the machine.  As result, developers, testers
and operators are able to create disposable and consistent environments for
development and testing.

Agile methodologies promotes adaptive planning, evolutionary development, early
delivery, continuous improvement, and encourages rapid and flexible response to
change. The main goal for short iterations is to release working item(s) to
product owners and communicate the progress on the project with stakeholders
and project sponsors.

This document suggests doing changes into day-to-day activities of developer
and tester, in a way that at the beginning of the day they must recreate a work
environment for getting the latest changes.  Having completed their work, only
those desired changes should be backed up to proceed to release resources used
(i. e. destroy the work environment created at the beginning).  If those
actions are performed daily by the team, anyone can be joined and start working
on the project without assistance, since anytime can request the creation of an
work environment and it will have latest changes of the project setup and the
project itself. Furthermore, those changes that were not backing up previously
are going to reflect malfunctioning the next time that someone creates a work
environment, as consequence, this new process helps to fail fast and quickly
realize that something is not working.

In order to demonstrate how this methodology works, I'll take the OpenStack
development as an example. OpenStack is an open source infrastructure as a
service (IaaS) initiative for creating and managing large groups of virtual
private servers in a data center. According to their activity reports during
the last 7 days 553 commits have been submitted, resulting in around 80
commits per day. That is why an OpenStack developer can get different results
of the work environment based on the day that was created.

The devstack-vagrant project allows to setup an OpenStack work environment and
retrieve latest changes of each OpenStack component using Vagrant boxes.  Using
Cloud-Driven Development, an OpenStack developer must recreate an OpenStack work
environment with devstack-vagrant project at the beginning of the day.  This new
work environment will remain active until all changes have been tested and
verified properly. Once all desired changes have been submitted to the OpenStack
repositories, before ending the day, the work environment must be destroyed to
release any resource.

## Results

Adapting agile methodologies to consume only the resources that are needed can
results in:

+ By using cloud computing model of "pay as you go" only during working hours
can reduce infrastructure costs for development and test teams.
+ Every time a work environment is created there is an opportunity to early
detect failures in the project.
+ Performing regular backups of the project reduces time for recovering and
impact caused by a disaster.
+ New members can quickly start contributing into the project.
