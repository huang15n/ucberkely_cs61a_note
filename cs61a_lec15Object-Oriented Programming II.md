

we are gonna continue talking about object oriented programming 
let us take a look at some announcements 
read through the grade scrote rubic meaning if you should have gotten a point , you should submit a regrade request 


the first checkpoint is to complete the phases 
the whole project will be due 
at the usual time and place 



the goal is to learn the paradigm, study the applications and porblems can be using oop 
jump into some reviews


a tower defnce games from invading colony 
keep from reaching it 

some extra amour, we have some bodyguard 

the key ideas are as follows.
it is made up of tunnels, which are chains of places 
bees stsart in the hive each time step 
they perform their action 
it depends on its types that specialize in some way 

phase1 : using oop basics to implement the core functionality of the games with basic ants 
phase2 : using inheritance to make specilzied ants with unique offensive 
phase3 : using inheritance to make specialzied ants with unique defensive capabilities 
phase4 : implement the ultimate, one and only 


objects: we have already seen some examples of python built in objects. list lterals
>>> lst = [1,2,3,4]
>>> lst.pop(2)
3
>>> lambda x : x + 3
<function <lambda> at 0x10acad1e0>

object oriented programming : a paradigm for programming based on objects with attribteus and methods 
we can modularize our programs by writing our own classes for objects 
a user defined obejct can be used with a class 
here is the representation of the class, you can od on instance of this class 
this is a representation of that instance 


class statement header 
whenever we have an assignment statement with a class statement, this becomes a class attribute 
__init__() methods which defines how that instance of class is created 
setting instance attribtue, constructors methods 
and more methods, we went through the logic and change it appropriate 
any name defined within a class statement is an attribtue 
even though they are not explicitly set 

# dot expression 
<expression>.<name>
an object is either an instance of a class or the class itself 
how to evaluate: 
1 evalaute<expression>, which yields an object 
2 <name> is matched against the instance attributes of that object if an attribute with that name exists, its value is returned 
3 if not, the name is looked up in the class, which yields a class attribute value 
let us move onto xxx 

# mutating objects: 
### it is a formalization of some of the things we have things 
i bind them to the names, each state 
anytime our balance has been changed, that is completely separated from any other instances 


# assigining attributes
recall that to mutate an object is to change its satte 
we can change an object's state by assigining new attribtues or reasigining exsiting ones. this is done in the methods of that 
<object_expression>.<name> = <expression>
if <object_expression> evalautes to a class then a class attribtue is assigned 
if <object_expression> evaluates to an instance, then an instance attribtue i assigned 

running low on funds
it evaluates the right hand side then assign to the left hand side 



# inheritance
an energizing example
tackle! 
this is not comprehensive of the complete everythig that can do 
he is a special type , electric type. a trainer,  thunder shock paralyze other 

put our class attribtues and a default damage
we set instance attributes that are particularly for each instance 
it is not completely conventional to assign these on the sam line here 

for the sake of saving space 
that will start off as xxx 
its name so with exclamation mark 


as to say shout its name whatever the basic attack is 
we are gonna set the hit point, we do not want to have negative points 
electric type. we are gonna paralyze the other pokemon 
we can call the builtin function type 
this is unique to received damage then we subtract health point 
there is a lot of repeated code 

its probability constant that now have change of paralyzing the other 
# one error will propogate 

electric type are simply specializedversion of the regular 
they attack differently, there is a realtionship 
water pokemon can swin


this is kind of representation are simply speciiazation of classes 



# the class definition allows us to specify that a new class inherits from a superclass : 
in the case of that example regular 
# class <Class Name>(<superclass name>)
# <suites>
# we call the more specialized class a subclass of the general class and the general class a # superclass of the specialized class 
# the subclass inherits all class attributes of the superclass 
# the subclass can override attribtues to specifiy how it is differernt from upserclass 

>>> class Pokemon():
...     def __init__(self, name, trainer):
...             self.name = name
...             self.trainer = trainer
...             self.level = 1
...             self.hp = 50
...             self.paralyzed = false
...     def speak(self):
...             print(self.name + "|")
...     def attack(self,other):
...             if not self.paralyzed:
...                     self.speak()
...                     print(self.name, 'used', self.basic_attack, 'on' , other.name + '|')
...                     other.receive_damage(self.damage)
...     def receive_damage(self,damage):
...                     self.hp = max(0,self.hp - damage)
...                     if self.hp == 0:
...                             print(self.name, 'fainted')
... 


>>> class Pokemon():
...     def __init__(self, name, trainer):
...             self.name = name
...             self.trainer = trainer
...             self.level = 1
...             self.hp = 50
...             self.paralyzed = false
...     def speak(self):
...             print(self.name + "|")
...     def attack(self,other):
...             if not self.paralyzed:
...                     self.speak()
...                     print(self.name, 'used', self.basic_attack, 'on' , other.name + '|')
...                     other.receive_damage(self.damage)
...     def receive_damage(self,damage):
...                     self.hp = max(0,self.hp - damage)
...                     if self.hp == 0:
...                             print(self.name, 'fainted')
... 
>>> class ElectricType(Pokemon):
...     basic_attack = "thunder shock"
...     prob = 0.1
...     def attack(self,other):
...             """attahks a pokemon with a chance of paralyzing it equal to 
...             self.prob. other electric types cannot be paralyzed """
...             self.speak()
...             print(self.name, 'used', self.basic_attack,'on',other.name + '|')
...             other.receive_damage(self.damage)
...             if random() < self.prob and type(other) != ElectricType:
...                     other.paralyzed = True 
...                     print(other.name , 'is paralyzed')
... 
>>> 


it is much shorter because we did not have to reapeat a bunch of code then 





# new dot expression rules: 
# <expression>.<name>
# how to evaluate 
# 1 evaluate <expression>, which yields an object 
# 2 <name> is matched against the instance attributes of that object; if an attribute with that name exists, its value is returned 
# 3 if not, the name is looked up in the class, which yields a class attribute value. if its not found in the class, look in any superclasses 
# 4 that value is returned unless it is a function, in which case a boun method is returned instead 


# desigining for inheritance 
# do not repeat yourself, use existing implementations 
# attributes that have been overriden are still accessible via class objects 
# look up attributes on instances when possible to allow for specialization 


we have look it up. 
i will pass in others 
then i can add other specialized logic 
we also want to use instance attributes whenever possible 
because eletric force is prob is a class attribute 
if we were to specialize further that inherits from another method 
maybe it defines a new xxx 
i can still call it, rather than defaulting to xx 

summarize here we reuse the general method that have been overriden via the class object 

this allows for specialization
representing objects as output 

# magic methods can implement special methods that allow the object to be treated like certain built in types 
that is kind of a handful of words 
they have seen so far is the init method so tese methods start and end with double underscores and init methods
this is a magic method that allows to construct an object by calling a class of function 
that sets a couple of 
it was not created with the def statenebt or a lambda expression yet 
we can still call it like a function 
we can also call in it the regular
it allows me to specizlize signals 

# objects as output
# sometimes, it is useful to see a descriptive representation of an object 


# magic methods
# python classes can implement special methods that allow the object to be treated like certain builtin types 
# these methods start and end with double underscores 
# we have already seen one : __init__ - a magic methods that allows us to construct an object by calling a class like a funciton 



# objects as outpu. sometimes, it is useful to see a descriptive representation of an object 
it is a useful represetnation, when you call it string of the purpose
we can see here that all function and less interesting 
this is less of a useful expression other than that fact that it is a fuction you know wehre is 
the idea is e want more descriptive and useful representation 



# __repr__ and __str__ 
# the __repr__ method defines a formal string representation fo an object 
# the __str__ method defines a informal readable represntation of an object 
# at first galance 
omit the rest of the class 


def __repr__(self):
	"""returns account"""
	return "we are gonna concenate this with "

def __str__(self):
 	""" this is a bit informal"""
	return self. xxx 

they are similar in that 
it just looks exactly like the constructor 
the output will be exactly the same 
it is simpler to undersand to anybody reads the book 

# __repr__(self) 
# what gets output, it evalautes to some object, then it is gonna to put that 
why are they special rathre than you call it any funciton
# __str__(self)
str coes here that you get the str representation whici is the the informal 

most of the times you are not going to be calling reference 

# it is just some weird underscripted object representation 
# specifically about implementing these things 
# it come in handy later 



# we can mutate objecst by reassigining their attribtue or assiginin new ones 
# use inheritance to implement a more specific versin of an existing class 
# a subclass inherits all class attribtues from its superclass, but can override them if necessary 

# the __repr__ and __str__ magic methods erturn string representations of objects that can be usful for output 










