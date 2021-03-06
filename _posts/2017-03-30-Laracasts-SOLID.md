---
layout: default
title: "Laracasts-SOLID"
date: 2017-03-30
---

# Single Responsibility
S in SOLID - single responsibility

"A class should have one, and only one, reason to change"

"A class should have one job"

## Examples:
**Sales reporter should not have authentication in "extract to controller"**

**Querying the db and doing a calculation.**

**Formatting output.**

Class would have to change, if we need to change either of these.

*This violates single responsibility*

## How Fixed

**Querying the db and doing a calculation.**
This was moved to a repository.

**Formatting output.**

1, Leave this to the consumer.

This is not the sales reporters job, so this means it needs to go.

2,

In the Reporting folder, create an interface.

```
interface SalesOutputInterface
{

  public function output($sales);
  

}

//and output classes which implement this

class HtmlOutput implements SalesOutputInterface {

  public function output()
  {
    return "<h1>$sales</h1>";
  }

}

```

# Open Closed

## "Entities should be open for extension but closed for modification."

"open for extension" - easy to change behaviour.
"closed for modifications" - change without modifying source code - extension

Modify behaviour without ever touching the original source.
= avoid code rot

```

class Square {

  public $width;
  public $height;
  
  function __construct($height, $width)
  {
    $this->height = $height;
    $this->width = $width;
    
  }
}

```
"We want to calculate the area"

```
class AreaCalculator{

  public function calculate($squares)
  
  
  {
  
      $area = 0;
      foreach($squares as $square)
      {
      
        $area += $square->width * $square->height;
      
      }
      
      retuen $area;
  
  }

}

```

"We also need circles"

```
class Circles {

  public $radius;
  
  
  function __construct($radius)
  {
  
    $this->radius = $radius;  
    
  }
}
```

Now we need the area!
Edit the original code = broken open/close principle.

*I think - interface and then implement for each shape?*


** Separate extensible behaviour behind an interface and flip the dependencies.**

Interface is a contract.

"Code to an interface".

Polymorphism - sharing a common interface,

# Liskov Substitution

"Code to an interface".


"Derived classes must be substitutable for their base classes"


- functions in derived classes should return same things
- so consumer recieves same thing
- instanceof suggests breaking LSP
- comment in the interface what should be returned


# Interface Segregation


"A client should not be forced to implement an interface that it doesn't use."

Star Trek example.

```
interface WorkerInterface{
  public function work();
  public function sleep();
}

class HumanWorker implements WorkerInterface{

  public function work(){
  
  }
  
  public function sleep(){
  
  }

}


class Captain {
  public function manage(Worker $worker){
    $worker->work();
    $worker->sleepk();
  }
  
}

```
Now we want to employ androids - they don't sleep.

Should not be forced to implemet sleep method. - Violates interface segregation

## Solution
Create two interfaces: WorkableInterface and SleepableInterface
``` HumanWorker implements  WorkableInterface, SleepableInterface ```

``` AndroidWorker implements  WorkableInterface ```

** Not sure i get the final stage of this **


# Dependency Inversion


"Depend on abstractions, not on concretions"

- not dependency injection
- high level modules should not depend on low level modules
- should depend on abstractions
- comes down to decoupling code

## High level Code
  Not concerned with details

## Low level Code
  More concerned with details and specifics.

One class should not be forced to depend upon an implementation.
Should depend on abstract, contract or interface

Plugs and sockets, not wiring to wire.

House provides outlet (intercace).
Anything which requires power must get it through this interface.

Example: 
Passing MYSQL connection to PasswordReminder. - bad, why does PasswordReminder care about the db?

High level modules (PasswordReminder) should not depend on low level modules (MySQLConnection).

High level modules should depend on abstractions. 

** Instead code to an interface. **

```
interface ConnectionInterface {
  public function connect();
}


```

Now PasswordReminder can depend on a ConnectionInterface.


```
public function __construct(ConnectionInterface $dbConnection)
```


# Watch Repositories


https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design

