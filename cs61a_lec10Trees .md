
# Lecture 10 Trees 

a picture of upside down trees 
we will see what that means a bit later 



display everyone's name . 
disbanded and put into another group 
you tak a look at that 
there is no discussions 
you can get through the problems quickly
reoccuring drop in mentoring sections 
that can be found here 

take it all the way through 

how take advantage of this week, there is a lot going on, you are stressed 
receive a blast 
a quick overview of what is important 

start on it 
we think that understanding fundamentals is really important before you jump into exam questions 
you have been working really hard 
go through more discussions 

untied , on instructional computers 
go through a problem and try it out 
grade yoruself, see wha concepts are tested 
check out the full posts 
work with people around you or work through any of probelms 
it will mostly like activities 
more information to be announced 
you time it


you do this in a place 
you are just taking it all the way through 

computer is lagging, resources per topic 
we have tagged these questions 
deals with list 
it does not require any information 
we really want to filter this 
staff review sections as a final sort of wrap up 

review some more problems to take time to exams , you get tired 
#### you do not want to burn out. you will feel more confident with concepts, more managemeable  stay clam, work through , complete to completion, feel free jump around, that is what we intend yo uto do 

understand how it affects our program 

#### trees as a data type, 
## Sequences Aggregation 
sequences are ordered colleciton of data so that would be lists, tules 
there is a couple more, how to aggregate them together 
#### iterable -- an obejct capable of returning its members one at a time.  it includes all sequences list, strings, tuples and some non sequence type like dictionaries 
for now you can think of iterable as the sequences, and there is non sequences types 
we will talk way more about it 

#### several built in functions take iterable arguments and aggregate them into a value 
#### sum(iterable, [start]) -> value , an optional argument 
#### returns sum of an iterable of numbers or lists not Strings plus values of parameter start which defualts to 0. when the iterable is empty, return start. to join a sequence of strings, use . join iterable 


#### max(iterable, [key = func] ) or max(a,b,c, [key = func]) -> key 
with a single iterable argument, returns its largest item, with two or more arguments , return the largest argument 
#### if you add a one argument function key, applies the key to each value and retruns the value that gives the largest number after applying the function 
it has to return some types it can be compared 
>>> sum(1,2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'int' object is not iterable
>>> sum([1,2,3])
6
>>> sum([1,2,3],3)
9
>>> sum([1,2,3],3,2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: sum expected at most 2 arguments, got 3
>>> sum([1,2,3],[2,3,3])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate list (not "int") to list
>>> sum([1,2,3],[2])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate list (not "int") to list
>>> sum([1,2,3],100.0)
106.0
>>> sum(['1','2'], '3')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: sum() can't sum strings [use ''.join(seq) instead]
>>> 'this is'.join(' Ed')
' this isEthis isd'
>>> 'this is'.join('Ed')
'Ethis isd'


let us try a list of list
you have to override the start value 
sum range to return a iterable 
range is a special type of sequence 
>>> sum(range(10))
45


the math checks out 
>>> max([1,2,3,1], key=lambda x : (-x - 3) * (x - 1 ))
1
#### after applying the number, that is all we have. take the minimum or the maximum of the strings compare by the minimum, who the strings are compared 
#### you cannot take the sum of this 





#### some more sequence aggregation
#### bool(any_value) -> bool , takes in any value not only iterables and returns True if the value is True value and False if it is a False value  
>>> bool(0)
False
>>> bool(1)
True
>>> bool([])
False 


#### all(iterable) -> bool. returns True if bool(x) is True for all values x in the iterable. if iterable is empty, return True. in other words, checks if all values in the iterable are true values 


#### any(iterable) -> bool, returns True if bool(x) isTrue for at least one value x in the iterable. if the iterable is empty, return False. in other words, checks if any values in the iterable are true values 

>>> any([1])
True
>>> any([])
False
>>> any(["", False, 0])
False






# Tree Abstractions. 
here is where it comes in that is because in cs they are circles conencted to other circles. that does not mean a lot to you 
how they relate to each other 
recursive defintion : wooden trees 
#### a tree has a root and a list of branches 
#### each branch is a tree 
#### this is the whole structure. because the tree is the whole structure.  a tree has a root and branches. 
#### a tree with zero branches is called a leaf 

use a metaphor of family tree, make a strcture 


#### relative description/ family trees: each location in a tree is called a node, each node has a label that can be any value 
something that is tricky that we have some problem

let us start with numbers 
people often refer labels by their locations; each parent is the sum of its children 

what that actually means each parent label is the sum of its children's label 



it were to be syntactically correct 
for our purposes 
trees are great way to figure out 
#### it should spit out formulaic way that a computer can understanad 
a company hire 
chief operational offcier 

#### we can depict this company hierachy 
you work up your way 


#### File Structure, how we represent where files are located. represents a folder with the names 
#### analyze it , tres are used everywhere in CS 
#### they cannot branch out. i am trying to expose you . it is used all over 
#### how do we code up a tree 


#### tree abstract data type
#### a tree has a root label and a list of branches
#### each branch is a tree 

a tree needs a label and branches, if we do not pass in a argument, it has not segents 
if you want to pass in any sort sequence , it will turn into a list, it is unnecsaary , but a safety check 
>>> def tree(label, branches=[]):
...     return [label] + list(branches)
... 
>>> def label(tree):
...     return tree[0]
... 
>>> def branches(tree):
...     return tree[1:]
... 


a tree is a list under the hood 
we can look through the branches, 
>>> def tree(label, branches=[]):
...     for b in branches:
...             assert is_tree(b)
...     return [label] + list(branches)
... 





if the length of tree is less than 1 or it is not a tree type 
if all branches are trees , then it is a tree 
>>> def is_tree(tree):
...     if type(tree) != list or len(tree) < 1:
...             return False 
...     for b in branches(tree):
...             if not is_tree(b):
...                     return False
...     return True
... 


technically it is bad, the whole point of abstract types 

maliciously , purposedfully 

printing trees, trees appear as nested lists because that is what they are underneath the abstraction barrier 
let us pretend we have print tree function to print our trees 




it does not technically break the structure


#### if you tilted our tree sideways rearranged it and stretched it a little bit 

#### we will see the innards of the tree class 
we made it optional 




# Tree Processing 
given a tree that is already built, how can i do stuf fwith values 

Tree Processing uses Recursion 
1 just like checking for whether the branches were trees, we also use recursion in tree processing function 
2 the recursive calls happens on smaller subproblems, which tend to be branches though not always 
3 we use the recursive calls with some types of aggregation  afterwards to get our final solution 


#### count nodes in a tree 
we want to count how many nodes there are in this tree 
this might be useful if you wanted to count how many people aer in a family trees 


count nodes initial solution: 
first two initial solutions: 
base case , what is the smallest known tree where we know the number of nodes ? a leaf 
recursive call. how we cut our problem into smaller parts and get closer to the base case? pass in each branch. we know branches are trees 


without having an explicit base case 
implicitly. it is completely ok to think of the inital solutions first 
move onto another problem 
gather all the entry level of subproblems 
again we tackle this recursively 
we notice that aggregation thsi time only requires adding the recursive calls and does not involve the root 



#### if you defined a function twice, it finds the latest one  
i donot quite understand how it works 
that keeps appearing 



->>> funciton call 
->>>> return 
this is for hte purposes of introducing this concpet 
i just made that up arbitrarily 
that is gonna run through out code 


#### one note, all these letters should be strings but quotes do not fit in the bubbles 
it illusrates how trees work 


that magic function , let us implement_tree now that we have gone through examples 
hint you can multiply strings by a number to make a string that is multiple of that string 


let me do a living coding 
for the time sake 
they are not idented 


### use builtin function str to convert numbers to strings 

break it up



# Creating Trees 
#### a function that creates a tree from another tree is also typically recursive . trees are recursive data structure 
# this allows us solve complicated real world problems 

it returns a new tree mean every label of every node squared 
take a look at both branches 
that would give us our final value 

trees are used everywhere in computer science, file structures 


square tree initial solutions 
return a tree with the square of every element in t 


sink in a little bit 
break it apart and return it back up 





fib trees, this whole tree is a fib tree of it 





#### Tree Recursion Problem versus Tree Problems 
#### tree recursion -- recursive function wiht multiple recursive trees 
#### tree problems -- problems dealing with trees 
#### tree problems that use recursion in their solutions are a form of tree recursion problem 
if you have difficulty in doing it 

just to differentiate 

#### trees are another cool data structure we run into the realm of computer science 
#### because trees are recursive in nature, it makes sense to implement tree functions with recursion. typically this involves recursing through every subtree, then aggregating somehow 
#### tree processing problem require manipulating existing trees and creating tree problems require creating new trees. these can be used together 


trees will make many apperance later in your careers !!!! 





>>> def tree(label, branches=[]):
...     for b in branches:
...             assert is_tree(b)
...     return [label] + list(branches)
... 
>>> def label(tree):
...     return tree[0]
... 
>>> def branches(tree):
...     return tree[1:]
... 


>>> def is_tree(tree):
...     if type(tree) != list or len(tree) < 1:
...             return False
...     for b in branches(tree):
...             if not is_tree(b):
...                     return False
...     return True
... 
>>> def is_leaf(tree):
...     return not branches(tree)
... 






they will make a lot apperances in the future 

















