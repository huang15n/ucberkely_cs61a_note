the checkpoint for two phases 
do make sure to add that person the same way you added for the exam 




# mutable function : mutable function is a function with behaviour that varies over time 
### if you call the same function multiple times is not the case 
how do we actually implement it 


insufficient funds 


nonlocal assignment & persistent local state 
you would run into someting a particularly commentary 

it allows us to change a binding in a frame other than the current one 
### we need to declare it nonlocal, we were changing the exiting balance 

>>> def nonlocal_frame_function(balance):
...     def withdraw(amount):
...             nonlocal balance
...             if amount > balance:
...                     return 'insufficient'
...             balance = balance - amount
...             return balance
...     return withdraw
... 
>>> withdraw = nonlocal
nonlocal                 nonlocal_frame_function(
>>> withdraw = nonlocal_frame_function(1000)
>>> withdraw(10)
990
>>> withdraw(20)
970
>>> withdraw(30)
940

they are all looking at the same balance, they are looking at the same state 
the nonlocal statement you always want to put it you are gonna modify it 
not locally 

persistent local state using environment, all of our class have the same parents 
there is never any balance declared here 
we changed the balance in our parent frame 


# nonlocal statement: nonlocal <name1>, <name2>, ....
# effect: future assignments to that <name > change its preexisting bidning in the first nonlocal frame of the current environment in which that <name> is bound 
pretty wordy 

# names listed in a nonlocal statement must refer to the preexisting binding in an enclsoing scope 
# names listed in a nonlocal statement must not collide with preexisting binngs in the local scope 

there is a collsion between local names and nonlocal name 

# nonlocal allows for a change in a nonlocal frame 

python particulars : 
you would think this would actually work 
unboundlocalError: local variabel references before assignment 
when we have talked about you evaluate call exprssion, this is strict rules 
it does an extra things, python precomputes which frame contains each name beore executing the body of the function 
within the body of a function, all instances of a name must refer to the same frame 

there has to be higher order function involved 

it is some misspelling errors , commentaries 


# mutable values & persistent local statements 
# mutable values can be changed without a nonlocal statement : lsit 
this actually works , the list out here in space can be manipulated 
bindings cannot be changed, the pointer from this frame to this lsit. 
the list itself changed but the pointer did not 
you have to maek this is done outside of the function 

but the point here, it is different from the other 
go through the rest of that 
we stick the balance 



# mutable functions in scheme 
go back to scheme 
they can be a useful tool to figrue out what is going on in a piece of code 
partial little diagram 

# we will commit to you 
why do not we need nolocal in scheme? 
in python, we use the same syntax for creating a new binding as we do for modifying an existing one , name = expression,
because of this, it does not know whether we want to create a new binding in the current frame or modify a binding in a parent frame 
it just assumes that we want a new binding unless we declare it nonlocal 


# referential transparent: if substituting an expression with its return value 
# exprssions are referentiall transparent if substituting an expression with its return value does not change the meaning of the program 
for an expression to be referentially transparent, it must be both pure and deterministic 

# mutation opeations violate the conditions of referential transparency becaue they are not pure 
they do more then just return a value, they change the environment 


# summary 
a mutable function is a function whoes behaviour can change on subsequent calss 
a nonlocal statement allows us to mutate name value bindings in a nonlocal frame in python, which we can use to create mutable functions 

mutation is a powerful tool, but comes at the cost of complexity 
it is a signal that calling this procedure can be dangerous 





