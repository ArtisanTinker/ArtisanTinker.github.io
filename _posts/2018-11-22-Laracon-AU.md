---
title: "Laracon-AU"
date: 2018-11-22
layout: default
---

# Modelling business requirements with Eloquent.

## The Ugly
* creates model in controller - move to command bus

## Case Study

* Use the business terminology.
** Leaky Abstractions ** - save method inside of model

** Domain-Driven Eloquent



# Level up with a Microservices architecture
Douglas Reith

https://www.youtube.com/watch?v=iAKfq4uJrBY&list=PLEkJYA4gJb7_FKspNTgrve7FUb3A1dT3y&index=9

Why?
* growth

## Design MA -> Deploy as a Monolith

## How?
* Domain driven design - language ubiquitous in a domain. 
* CQRS - Command and Query Request Segregation - write model and read model
* Request Journey
* Package Exploration

* Packages can mimic the language of the business.







# Patterns that pay off
Matt Stauffer
https://www.youtube.com/watch?v=FNyUX2jVMeE&list=PLEkJYA4gJb7_FKspNTgrve7FUb3A1dT3y&index=12

## Preventative Patterns
Do this on every app no matter what.

## Reactive Patterns
Feel/see the pain, then choose the fix
There is a need.

**Problem: we just use patterns without first identifying a need **
We just want to use the favourite tool.

** Don't do stuff you don't need **

** Cost of change **
Well written code minimises the cost of change.

## Write code that is easy to delete.

## Matt's Patterns


### Process

### Architecture
  
### (Re)factoring

## No precogs
* You think you can predict the future
* You can't
* Do the best work with the requirements which you have

## Codebase Consistency
Everyone writes code the same way

## Four Eyes
* Code always have two sets of eyes on it.

## Architecture Patterns
### Monolith First
### Seeds not dumps
### Test to save your job
* what is most likely to break
* what would be the biggest nightmare
* what needs to work

## (Re)factoring patterns 26:37
* Seed each test - setup data in each test, don't do this up front.
### Custom Requests - for preparing data
* most controllers 1, get data, 2 process, 3 get data out

* not form requests.
* eg SignUpRequest - extending Illuminate Request class

### View Data Composition
#### Presenter  - layer on top of model (like decorator for views) 36 mins in

#### View Model - takes data in and exports the way you want
#### Responsible - interface for an object which can be converted into a response
#### View components - 


Slides available here:

https://mattstauffer.com/talks/

# Abusing Laravel for Fun and Profit
https://www.youtube.com/watch?v=dd-iHhmSi2k&index=8&list=PLEkJYA4gJb7_FKspNTgrve7FUb3A1dT3y

## Front End Filters
Filtering in controllers
### Pipeline
### Feature tests powered by seeders
Arrange -> Act -> Assert
Don't keep with the other seeders.
### Form Requests for Database Access


# Understanding git
Anwesha Chatterjee
https://www.youtube.com/watch?v=ofVcPhK2oYU&list=PLEkJYA4gJb7_FKspNTgrve7FUb3A1dT3y&index=6

* should rebase not amend

```git log --graph -- oneline --all```

```git reflog ```

Try rebasing:
``` git rebase master```

# Building a complex product while scaling a team and a business on Laravel
https://www.youtube.com/watch?v=eef3Pnxc5A0&index=5&list=PLEkJYA4gJb7_FKspNTgrve7FUb3A1dT3y


* annotations
* multi-tenancy 
09:01
* domain specific classes
* slim controllers
* use Facades (not their own) -> contracts and dependency injection
* monolith and packases
* interfaces good for learning code
* clearly defined APIs
* passing Eloquent models around take care with packages
* Homestead -> Docker + Kubernetes
* Tech debt weeks - 1 week a month - > customer value - just improving what you have got
* remote first
* document decisions
* write things down!
* markdown files in the code




29:48

