---
title: CQRS/ES Einhorn Lunch
separator: --->
verticalSeparator: --v
theme: white
revealOptions:
    transition: 'fade'
---

# CQRS/ES

Was ist das? Warum brauch ich das?

<small>Einhorn Lunch<br/>Jan Galinski<br/>27.02.19</small>

--v

## Hypothese

> CQRS mit Eventsourcing ist ein fantastisches Architekturmuster 
> zum Bau nachrichtenbasierter, lose gekoppelter (Microservice) Systeme

--->

# Systems have State

--v

## State is represented by Domain Objects

- aka. Entities 
- aka. Aggregate (DDD)

--v

### State can be modified
<h1 class="fragment">&rarr; COMMAND</h1>

--v

### State can be retrieved

<h1 class="fragment">&rarr; QUERY</h1>

--v

## Code is easy
<br/>
## State is hard

--->

# CRUD

<p class="fragment">Create - Update - Delete</p>

--v

### Request/Response

![](img/crud1.png)

synchronous

--v

### Scaling up

![](img/crud2.png)

synchronous

--v

### Message Driven

![](img/crud3.png)

asynchronous

--v

# Eventual consistent

* query will "soon" retrieve correct state
* ACID &rarr; BASE
* we no longer benefit from having the same read/write model

--->

# CQRS

--v

## Command
## Query
### Responsibility
### Segregation

--v
<!-- .slide: data-background="./img/data-flow.svg" height="100%" -->

.
--v

# Command

* expresses and Intent that something should happen in the future
* has an imperative name (CreateOrder)
* can fail
* modifies the state
* triggers events

--v

# Event

* expresses somthing that happened in the past
* has a participe name (OrderCreated)
* is an immutable fact
* can not fail

--->

# Event Sourcing

> Event Sourcing ensures that all changes to application state are stored as a sequence of events.
>> Martin Fowler

--v

### Event Store

* append only, lock-free
* optimized for quick write
* easy to distribute
* single point of truth
* can be used to (re-)create State

--v

### Event Sourcing

![](img/active-record-es.png)

--v

## Benefits

* multiple Read models (Projection) with dedicated purpose
* audit log for free
* analyse/debug State by replaying selected events
* correct errors with compensation events

--->

### System Overview

![](img/cqrs-system.png)

--->

# "Demo"

* create a deployment

--v

![1](img/cqrs1.png)

--v

![2](img/cqrs2.png)

--v

![3](img/cqrs3.png)

--v

![4](img/cqrs4.png)

--v

![5](img/cqrs5.png)

--v

![6](img/cqrs6.png)

--v

![7](img/cqrs7.png)


--->

# `exit(0)`

