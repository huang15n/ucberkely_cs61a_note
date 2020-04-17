Garfield comic strip , 


special type of evalaution where it won't evaluate unless we tell it to 
that is the theme for today , revision , revise your composition 


data structure and special forms 


# iterators: 
defintions : 
define a bunch of stuff, memorizing defintions 
you will see how they all tied together 


# lazy evalution - delays evaluations of an expression until its value is needed 
# some benefits :
# 1 the ability to define control flow if , and , or types fall under the category of lazy evalatuion, it evalautes according to some of control 
# 2 the ability to define potentially infinite data structure. infinite stream of data 

# iterable: an object capable of returning its members one at a time, examples include all sequences list, stirng, tuples and some nonsequence type , dictionaries 

# iterator, an object that provides sequential access to values, one by one 
metaphor: iterators are bookmarks , go page by page 
# all iterators are iterables not all iterables are iterators 
you know all iterators are iterables but not all iterables are iterators 

some defintions out of the way 

# iterators:  object that provides sequential access to values 
# itr(iterable): return an iterator over the elements of an interable alue 
# this method creates a bookmark from a book starting at the front 
# if you pass in an iterator, it is like trying to create a bookmark from a bookmark and it just returns iteslf 

# next(iterator): return the next element in an iterator : return the current page and moves the bookmark to the next page 
# the iterator remebers where you left on. if the current page is the end of the book, error 

>>> s = [1, 2, 3]
>>> one , two = iter(s), iter(s)
>>> one 
<list_iterator object at 0x10626f1d0>
>>> next(one)
1
>>> next(one)
2
>>> next(one)
3
>>> next(two)
1
>>> next(two)
2
>>> next(two)
3
>>> next(two)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration

## both of them pointing to the same position, next, move forward 
we raise a stop iteration error, conceptually 

# iterators are always ordered, even if the container that produced them is not 
>>> d = {"one":1, "two":2, "three": 3}
>>> d['four']=4
>>> k = iter(d)
>>> next(k)
'one'
>>> next(k)
'two'
>>> next(k)
'three'
>>> next(k)
'four'



the reason why is beyond the scope of this, it is always in this order 
>>> v = iter(d.values())
>>> next(v)
1
>>> next(v)
2
>>> next(v)
3
>>

when you call iterator, it will be in the same order 




# Exceptions / Errors 
what it has to do with everything 

# sometimes, computer prorgrams behave in non standard ways 
1 a function receives an argument value of an improper type 
2 some resources such as a file is not available 
3 a network conneciton is lost in the middle of data transmission 
#### to clarify errors and exceptions are the same things, we use them interchaneably 



a moth caused the computer to break 
the first actual case 
an error occurred 


# exceptions are raised with a raise statement 
# raise <exception>
# <expression> must evalute to a subcla of BaseException or an instance of one 
# Exceptions are constructed like any other object 
# BaseException(
# TypeError('error message') -- a function was passed the wrong number / type of argument 
# NameError --  a name was not found 
# KeyError -- a key was not found in a dictionary 
# RuntimeError -- catch all for troubles during interpretation 



>>> raise BaseException('anything in the exception with messages')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
BaseException: anything in the exception with messages




>>> raise KeyError('key not found')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'key not found'


>>> def f(x):
...     if type(x) != int:
...             raise TypeError('Give me an int')
... 
>>> f(1)
>>> f(1.0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 3, in f
TypeError: Give me an int



we have seen errors all over the place 


# try statement : try statements handle exceptions 
the idea of handling , let us not make anything 

# try :
#	<try suite>
# except <exception class> as <name>:
# <except suite>

this is where you want to specify whichever error you want to handle 
# executin rule: 
# 1 <try suite> is executed first 
# if, during the course of exeuting the <try suite>, an exception is raised that is not handled otherwise then <except suite> is executed with <name> bound to the exception 


it is only if something was not handled 
what will happen is , if it is an exception it fits this class, 
this name will be bound to exception and bound to the exception 


>>> try :
...     x = 1 / 0
... except ZeroDivisionError as e:
...     print('except a', e)
...     x = 0
... 
except a division by zero



>>> try : 
...     print("something")
... except BaseException as e:
...     print("something random")
...     print("good")
... 
something



we understand how to raise errors and why we might use that 


# back to iterators -- the for statement 
we have seen this a couple times 
but we really did not go into details 
# for <name> in <expression>
# <suite>

### 1 evalaute the header <expression>, which must evaluate to an iterable object 
### 2 for each element in that sequence, in order 
### a bind <name> to that element in the first frame of the current environment 
### b execute the <suite>
# when executing a for statement, iter returns an iterator and next provides 

python under the hood does this, let us make an iterator from that iterable 
when executing a for statement, iter returns an iterator and next provides each item 

wrap this all in try statement 
names get bound to next iterator 
>>> counts = [1,2,3]
>>> items = iter(counts)
>>> try:
...     while True:
...             item = next(items)
...             print(item)
... except StopIteration:
...     pass
... 
1
2
3


give me the next element forever until there is an error 
StopIterator is called whenver there is an empty iterator 
you baiscally are past the end of the book 

this is done element by element 

# built in functions for iterations 
##  many built in python sequence operations return iterators that computes results lazily 

we are only evaluating when we tell it to 

# map(func, iterable): returns an iterator that iterators over func(x) for x in iterable 
# filter(func, iterable) returns an iterator that iterates over x in iterable if func(x)
# zip(iterable, iterable2): returns an iterator that iterates coindex(x,y) pairs 
# reversed(sequence): returns an iterator that iterates over a sequene in reverse order. note this only works on ordered collections (sequences)
# to view the contents of an itrator, place the resulting elements into a container 


>>> func1 = lambda x : x ** 2 - 1
>>> map(func1, [1,2,3,4,5])
<map object at 0x1063934a8>
>>> m = map(func1, [1,2,3,4,5])
>>> m
<map object at 0x106393710>
>>> for item in m:
...     print(item)
... 
0
3
8
15
24
>>> 

>>> f = lambda x : x > 2
>>> func2 = lambda x : x % 2 == 0
>>> f = filter(func2, [1,2,3,4,5,6,7,8])
>>> for item in f:
...     print(item)
... 
2
4
6
8



# list(iterable): create a list containing all x in iterable 
# tuple(iterable): create a tuple containing all x in iterable 
# sorted(iterable): create a sorted list containing all x in iterable 
>>> tuple([1,2,3])
(1, 2, 3)
>>> list((1,2,3))
[1, 2, 3]
>>> sorted((4,1,3,2))
[1, 2, 3, 4]




>>> f = lambda x : x >= 10 
>>> double = lambda x : x * 2 
>>> list(filter(f,map(double,range(3,7))))
[10, 12]


map takes in a function and an iterable , range is an iterable 
then it will creae an iterator 

that is actually conceptually important 
spit out one by one 
it also advantage of the conccept of iterator 




# Generators: generators deals with keyword yield 
# defintions and rules : some defintions : 
# generator: an iterator created automatically by calling a generator function 
# generators are special iterators because they get created automatically by calling a genettor unction 
# a generator function is a function that contains the keyword yield anywhere in the body 

# when a generator function is called, it returns a generator instead of going into the body of the function, the only way to go into the body of a generator function is by caling next on the returned generator 

# yield values are the same as returning values except yield remember where it left off !!!! 
# that is because yields are generators, generators are iterators 

>>> def plus_minus(x):
...     yield x 
...     yield -x 
... 
>>> t = plus_minus(3)
>>> t



what if i want to go inside: 
>>> next(t)
3
>>> next(t)
-3
you can imagine should have drawn a little arrow 
# it resumes execution and execute the next statement 
>>> def plus_minus(x):
...     yield -x
...     print("this is no explicit return statement")
...     yield x
... 
>>> t = plus_minus(10)
>>> next(t)
-10
>>> next(t)
this is no explicit return statement
10



# generator to represent infinite sequence 
# iterators are used to reprsent infinite sequences 
>>> def naturals(x):
...     while True:
...             yield(x)
...             x += 1
... 

we can keep doing this forever, 
 when we yield that value, the generator stopped for a sec 
 then we call that again 
 >>> def naturals(x):
...     while True:
...             yield(x)
...             x += 1
... 
>>> nats = naturals(1)
>>> next(nats)
1
>>> next(nats)
2
>>> next(nats)
3
>>> next(nats)
4
>>> next(nats)
5
>>> next(nats)
6
>>> next(nats)
7



it will keep calling generator 

# generators can yield from iterators 
# a yield from statement yields all valus from an iterable 


>>> def a_then_b(a, b):
...     for x in a:
...             yield x
...     for x in b:
...             yield x
... 


>>> def a_then_b(a, b):
...     yield from a
...     yield from b 
... 

we are gonna get all values of a and b 
>>> gen = a_then_b([1,2,3],[4,5,6])
>>> next(gen)
1
>>> next(gen)
2
>>> next(gen)
3
>>> next(gen)
4
>>> next(gen)
5
>>> next(gen)
6
>>> next(gen)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration

# a "yield from" statement yields all values from an iterable
this is a really nice short hand 

>>> def countdown(k):
...     if k > 0:
...             yield k
...             yield from countdown(k-1)
... 
>>> def countdown(k):
...     if k > 0:
...             yield k
...             yield from countdown(k-1)
... 
>>> c = countdown(10)
>>> next(c)
10
>>> next(c)
9
>>> next(c)
8
>>> next(c)
7
>>> next(c)
6
>>> next(c)
5


we are gonna yield each value, it is gonna yield us the correct value 
>>> def countdown(k):
...     if k ==  0:
...             yield 'blast off'
...     else:
...             yield k
...             yield from countdown(k - 1)
... 
>>> gen = countdown(3)
>>> next(gen)
3
>>> next(gen)
2
>>> next(gen)
1
>>> next(gen)
'blast off'
>>> next(gen)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration

that is because , yield from k - 1
and work through that 


for time sake, i am gonna move on 


# Streams 
it has been a dense lecture 
it is always good to take a look at the nature 


# defintions : streams : are lazily computed pairs, they are anallogous to lazily computed scemes lists 
# promise : an expression that evalautes to a value only when asked to. this is how streams accomplish lazy evaluation 

# not forced -- means the promise has not been evaluated yet 

# force: means the promise has already been evalauted 


































