they will interact with each other 
let us refresh it 

all these will reappear 
you need to submit regrade requests 
we have a ton of exams
take it some time work through rubrics 
the individual portion 
i want to go over recovery policy, if you felt like xxx 
we go into here 
our participation 
it is capped at xxx
just for simplicity 
our adjusted score


we actually hope and remember buckets are here 
reach out or you know if you are concerned at all 

if you put in the time 
you come ask for help, you can definitely improve all 



we are centered around a theme 
the paradign that means the idea of this new type of programming 
problems can be solved using this 


# Object Oriented Programming 
#### a method for organizing modular programs and represent the real world 
#### what modular means is sort of self-contained programs that represent the real world, this relies heavily 1 data abstraction 2 bundling together information and realted eahviour 


#### a metaphor for computation using distributed state 
#### it means each object has its own local state, keep track of its own functions 
#### each object also knows how to manage its own local state 
#### method calls are messages passed between objects 
#### several objects may all be instances of a common type 
#### different types may realte to each other 
#### specialzied syntax and vocabulary to support the metaphor 
they have to keep track of that, withdraw money from my account, loan out money, there is a lot of interactions between these accounts, we want to model that behavours 

# Class: a class serves as a template or blueprint for its instances 
it basically tells us what we should build 
idea: all bank accounts have a balance and an account holder; add those attribtues to each newly  created instances 
#### abstracted way to get hold on to it 
#### the class should give these instances 
ideas: bank accounts should have withdraw and deposit behaviours that all work in the same way 

####a better idea , make all bank acounts share methods 
across accounts also share other characteristics like maximum withdrawl 


class<name>:
	<suite>
that is going to describe the behaviour of the class 
a class statement creates a new class and binds that class to the current environment 
assignment & def statements in the <suite> create class attributes 
characteristics shared across different classes 
this variable signifies that only that can xx that is like a security feature, we are only allowed to implement that 

have that same functionality, it makes a little more sense 
bind that class to current environment 
a class is a mapping between variables and their values 
these are called class attributes 
we are copying over all these 
whenever you see this structure, we are talking about frames 


# the class statement 
#### before we start implementing our methods, we need to talk about how to create accounts 
idea: all accounts ahve a balance and account holder, these are not shared across Accounts 
we need those to be unique for each instance 
#### right parentheses that is calling the class . a new nstance of that class is created. 

# when a class is called 
## 1 a new instance of that class is created 
## 2 the __init__ method of a class is called with the new object as its firs argumet named self, along with additional arguments provided in the call expression 

it takes in two arguments , are we supposed to 
python does something magical and fancy, it passes some instance of the class as the firs argument  in the instances of the class as the first argument automatically 


###### it is little weird and counterintuitive 
we first make an instance of the class we passed that in as the first argument 
and then will pass in the rest of the arguments 
so we say self.isntance_variable = value 
this were to go away 
>>> class Account: 
...     def __init__(self,account_holders):
...             self.balance = 0
...             self.holder = account_holders
... 


this is called the constructor, the __init__ method allows us to constuct the instance of the classes 
i am just gonna put in for now
what does this code do? let us walk through it 

we can hide the attributes, the class attribtues 

>>> class Account:
...     def __init__(self,account_holder):
...             self.holder = account_holder
...             self.balance = 0
...     def withdrawal(self, amount):
...             self.balance -= amount 
...     def depsoit(self, amount):
...             self.balance += amount
... 

actually, each time when we call this function floating in space so like how you call the lamda function 
it is floating in the space before we bind it 
let us walk down 


because there is no return value it returns none
we called the init method by calling the class and then we made an instance of the account sort of floating it 
>>> eddie_account = Account('Eddie')
>>> eddie_account.depsoit(100)
>>> eddie_account.balance
100


we call the init method, we point self to the arrow is completely rolling now 
account instance creates an instance and then makes account holder and it gives the balance it binds to the instance 
these called instance attributes 


### object identity , every object that is an instnce of a user defined class has a unique identity 


## Dot Expressions 
we see that little dot there 
# you can access class or instance attribtues with dot notation 
<expression>.<name>

the <expression> can be any valid python expression that evaluates to a class or instance 
the <name> must be a simple name 
to evalaute a dot expression
1 evaluate the to the left of the dot which yields the object of the dot expression 
2 <name> is matched against the instance attribtues with that name exists, its value is returned 
3 if not, <name> is looked up in the class, which yields a class attribute value 
4 that value is returned unless it is a function, in which case a bound ethod is returned instead 

the word method will appear 
these lookup rules are really important 
you always check the instance first 

it throws errors:
>>> Account.balance
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: type object 'Account' has no attribute 'balance'

it is pretty descriptive 
i commented it out
>>> Account.__init__
<function Account.__init__ at 0x10ffa5598>
	that is a function 

accessing the deposit method seems to give us a function 
luckily 

# methods are functions defined in the suite of a class 
## however methods are accessed through an instance will be bound meethods. bound methods couple together a function and the object on which that method will be invoked. this means that when we invoke bound methods, the instance is automatically passed in as the first argument 
an instance will get magically passed in the first argument 

## invoking methods, we can call class methods in two ways as a bound method and as a funtion 
## invoking class methods as a bound method 
## bound methods are accessed through the instance and implcity pass the instane object in as the first argument of the method 
# <instance>.<method_name>(<arguments>)
we accessed it through the instance, it bcomes a bound method 
because normally, we tell it to be passed in which is the second way to invoke the class 
# invoking class methods as functions 

## follow our typical function 

>>> class Account:
...     max_withdrawal = 10
...     def __init__(self, account_holder):
...             self.balance = 0
...             self.holder = account_holder
...     def deposit(self, amount):
...             self.balance = self.balance + amount
...             return self.balance
...     def withdrawal(self,amount):
				if amount > max_withdrawal: 
					return "Cannot witdraw that amount"
...             self.balance = self.balance - amount
...             return self.balance
... 

some descriptive messages, let us see that in action 
the impelementation of that message 



# Accessing Attributes
## there are builtin functions that can help us access attributes for various reasons 
## get getattr, we can look up an attribtues using a string instead 
## -- getattr(<expression>,<attribute_name(string)>)
## -- getattr(a, 'balance') is the same as a balance 
## -- getattr(Account, 'balance') is the same as 
>>> class Account:
...     max_witdrawal = 0
...     def __init__(self,account_holder):
...             self.balance = 0
...             self.account_holder = account_holder
...     def deposit(self, amount):
...             self.balance = self.balance + amount
...             return self.balance
...     def withdrawal(self, amount):
...             if amount > max_withdrawal:
...                     return "cannot withdraw that amount"
...             self.balance = self.balance - amount 
...             return self.balance 
... 

>>> eddie_account = Account("Eddie")
>>> getattr(eddie_account, 'balance')
0

those are different ways of trying to put explicitly 
using hasattr, we can check if an attribute exists 

### -- hasattr(<expression>,<attribute_name(string)>)
### -- hasattr(a, 'balance') returns True
### -- hasattr(Account, 'balance') returns False 
>>> hasattr(eddie_account,'balance')
True


let us formalize the rules for assigning slash 
### assigning attribtues: we saw this before, but let us formalize the rules for assigining /reassigning instance and class attributes 
<expression>.<name> = <value>
### change attribtues for the object of that dot expression 
### if the expression evaluate to an instance, then assignment sets an instance attribtue , even if it exists in the class 

# Summary
### object-oriented programming is another way paradigm to organize and reason about programs 
### the python class statement allows us to create user defined dat type that can be used just like built in data types 
### class attribtues are variables shared across instances 
### instance attribtues are unique to each instance 
### two ways to invoke methods, implicitly and explicitly 

it is gonna be really fun





>>> class Parent:
...     def __init__(self, name, number):
...             self.name = name
...             self.number = number
...     def call_it(self):
...             print("the name is " + self.name )
...             print("the number is "+ str(self.number))
... 

>>> class Child(Parent):
...     pass
... 
>>> c = Child("eddie",123)
>>> c.call_it()
the name is eddie
the number is 123





















