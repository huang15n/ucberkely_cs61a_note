this lecture is being webcasted 


in terms of sure make sure you get phase one completed 

quiet down please

this is completely optional 
checkpoint due tonight
write your own strategies. 
the code you turn in should not have dependencies 
at the usual time in place 
there is still some slots open 
the info for it is up 

there is going to be a group portion of it called choosing your group 

revoke their invitation 


how to process sequences
go over what the sequence abstraction is and explore this topic using various data types 


>>> def something():
...     return 1, 2, 3
... 
>>> one, two, three = something() 
>>> one 
1
>>> two 
2
>>> three 
3


#### a sequence is an ordered collection of values 
strings : sequence of characters 
lists : sequence of values of any data types
see this in action really quickly 

similiarly if i call the length of that, it refers to the lngth of list 
>>> [1,2,3,4]
[1, 2, 3, 4]
>>> len([1,2,3,4])
4
>>> lst = [1,2,3,4]
>>> len(lst)
4

each element is specified by the index 
sequence are ordered collection of values 
>>> lst = [1,2,3,4]
>>> lst[0]
1
>>> 


similiarly 
>>> "hello"[1]
'e'

it does not have to be the same type 
they can carry any type of data 

>>> lst = [1,2,[3,4],5]
>>> lst[2]
[3, 4]

i can index into that again
i will expect to get the index again, put some bracket next to it 
>>> lst[2][1]
4

in general it does not matter how you want to represent strings 
are there any meaning of apostrophe.  does that make sense 


sequences by themselves are not specific data type 
there is no concrete type
## all seuqneces have special behaviors 

## all sequences have a finite length 
## each elements in a sequence has s discrete integer index 
it is labeled with index 
just our standard way 
the share trait of a finite length, being able to retrieve an element at particular position , create a copy of a subsequence, check for membership, concatenate two sequences together 


let us go eahd and focus on these for now 



#### get item get the /th element <sequence>[i]
we can creat a copy of sequence as slicing 
these sequence and syntax looks fairly similar to it 

#### slice a subsequence : create a copy of the sequence from i to j 
<sequence>[i:j:skip]
i is inclusive , j is exclusive 
i want to slice from i to j, i do not include the element of j

#### check membership: check if the value of <expr> is in <seq> 
#### <expr> in <seq>


#### concatenate: combine two sequences into a single sequence <s1> + <s2>



i want every other character in my sequence starting from i 
i just left it blank that defaults to 0 
if you do not include anything after this first colon : it defaults to the end of the sequence 
skip every other element 

>>> lst
[1, 2, [3, 4], 5]
>>> lst = [1,2,3,4,5,6,7,8,9]
>>> lst[::]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> lst[::2]
[1, 3, 5, 7, 9]
>>> lst[::-2]
[9, 7, 5, 3, 1]
>>> lst[:8:]
[1, 2, 3, 4, 5, 6, 7, 8]
>>> lst[:9:]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> lst[1::]
[2, 3, 4, 5, 6, 7, 8, 9]


slice up to that index 
combiding that , if i do not provide any index, i am just gonna create a copy of the entire lsit 


i want to point out this will take the subsequence out of it and create another list out of that 


check membership: chekc if the value of <exp> is in <seq> <expr> in <seq>

3 in [1,2,3,4,5]
'z' in 'socks'


>>> 3 in lst
True
>>> 'z' in "socks"
False
>>> 2 + 2 in lst
True

take note it is not an elmeent of this list, 3 is in the inner list  
>>> lst = [1,2,[3],4]
>>> 3 in lst
False
>>> 3 in lst[2]
True

lasty we can concatenate two sequence togehter
 doing this we use + 
 you are not gonna numerically add them but rather you are going to take the sequences and make it into 1 

 >>> [1,2,3] + [2,3]
[1, 2, 3, 2, 3]
>>> "hello" + " world"
'hello world'

at least for the time being 
what kind of what behaviours sequences can take on 
python constructs thta exists allow us to process easier 

i want to do something , it is not uncommon 
it works out 
if i keep like this, i increment i for every iteration , that is exepcted , you start out with some index, you do whatever you want 


sum up all of the even numebrs of some list of integers 

okay, let us go ahead and try this out 
iterating through the list, i had to initialize i, iterate through i and increment i 
it is kind of a lot of repeated code do separate things 


#### iterating through sequences. 
#### you can use a for statement to itearte through the lements of a sequences: 
for <name> in <seq>:
	<body>

it simplifies things a little bit 
it looks like, specifically what you do is to provide the sequences and python inds of takes care of the rule for you 
the rules for execution is for each element in the sequence, we are going to bind it to the name, provided name . 
1 bind it to name 
2 execute <body>
>>> i = 0
>>> for element in [1,2,3,4,5]:
...     print (i , ":", element)
...     i += 1
... 
0 : 1
1 : 2
2 : 3
3 : 4
4 : 5

i can be incremented
similarly, in the next iteration, it seems fairly a simple  
you will see how the element has been bound to the frame 
there is no explicit assignment, it just does it for you 


this name you can make whatever you want, it has to be consistent with whatever's in the body of the for loop 
this is really any name you want to give to thelement 
>>> def sum_of_evens_for(lst):
...     total = 0
...     for e in lst:
...             if e % 2 == 0:
...                     total += e 
...     return total 
... 

you have to keep track of, you do not have to do it manually 
you should be able to get the same result 
we removed the redundancy of removing the loops 


# Range: 
#### the range function creates a sequence containing the values within a specified range 
#### range(<start>,<end>,<skip>)  
#### skip specifies how many every other x numbers of element that we want 
#### start inclusive end exclusive 
#### create a range object from start to end , skipping every skip element 
i can skip every other element 

i can do the range of the length of the element 
the start defaults to zero 


if i have only one parameter in the range, that becomes end index 
all i am saying, iterating through the sequence and print it out 
it is kinda useful tool if you ever mean to iterate through some sequence of numbers 

come to me during the break actually i can talk to you abot that 
come to me after lecture i am not really sure what you are asking 
>>> def print_odd(lst):
...     for x in range(lst):
...             if x % 2 == 1:
...                     print(x)
... 


if you do not need the name of the sequence that you are intearteing through 
# you can just provide a random name or an underscore just to denote that you do not. care about the name 

i do not care what element in the ranges 
>>> def print_n_times(x,n):
...     for _ in range(n):
...             print(x)
... 
>>> print_n_times("hello",5)
hello
hello
hello
hello
hello
anything what i care is that this loop iteration happens xxx times 
find out for yourself, you can try out on 
we just throw on a bunch of tools 

that was kind of to illustrate that if you want both the index and the elemnet of the list ithin the body of the for loop, you can access that element as well as provide the index 



# list comprehensions: 

#### you can create a list out of a sequence using a list comprenhension 
[<exp> for <name> in <seq> if <condition>]

[individual_element**2 for individual_element in list if individual_element % 2 == 0]
>>> [alphabet for alphabet in "abcdefghijklmnopqrstuvwxzy"]
['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'z', 'y']


>>> [100 for _ in range(100)]
i just want somethign to happen 100 times 


it kinda look like a for loop inside a list 
#### it is kinda unrolled in this code, specifically 
when you execute a list comprehension 
#### rules of execution 
1 add a new frame with the current frame as its parent 
2 create an empty result list that will be the value of the list comprehension 
3 for each element in <seq>
	a bind to that element to <name> in the new frame from step 1 
	b if condition evalutes to a true value then add the value of <expr> to result list 

it is kinda a lot 
if the element here satisfies that 
let us see a walkthrough of this 
i am opening a new temporary frame, it is provided to each element of the sequence , the condition is option 
>>> [c + "0" for c in "cs61a"]
['c0', 's0', '60', '10', 'a0']
>>> [e for e in "stake" if e > "a"]
['s', 't', 'k', 'e']
e is assigned to s 

i want something to happen xxxx times 
>>> [100 for _ in range(100)]
[100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100, 100]


i am gonna make a list with two and three , put a list in a list 
>>> [[e, e + 1] for e in [1,2,3,4]]
[[1, 2], [2, 3], [3, 4], [4, 5]]
oen for each element of the sequence i provided here 



####  the skip in range allows you to go every other element or whatever parameter you put 
>>> [_ for _ in "hello world"]
['h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']


you can come up and talk to me here 


we move on to a related topic called mutability 

# Mutability: 
mutable objects have state and can change over the course of program 
lists care one example of mutable objects. not all sequenes are mutable and not all mutable objects are sequences 
a string is not mutable, it is a primtiive value. it is a sequence 
that is how we are going to represent the nest list 
we can change the value inside the list, that is why we call it mutable 
it is still the same exact object 
what I did was i index into the list and I changed an element 
that is known a mutating the list or changing thevalues of the list 

there are some methods or functions that we can mutate to change the list 


# list mutation method 
append(e1) takes in one argument and it adds argument onto the end of some list 
>>> lst = [1,2,3]
>>> lst.append([4,5,6])
>>> lst
[1, 2, 3, [4, 5, 6]]
>>> lst.append(1,2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: append() takes exactly one argument (2 given)



insert(i,e1): inserts el at index and shifts the rest of the elements over 
>>> lst = [1,2,3,4,5]
>>> lst.insert(2,2.55)
>>> lst
[1, 2, 2.55, 3, 4, 5]
>>> 

#### everyone is shifted over to make room of it 
both of these lists do anything, no list was created. i mutated the original list and when i looked up the original list had changed smae with insert 

#### remove(el): removes the first occurence of that argument in  the list from the list 
remove does not return anything, it just mutates the list 
>>> lst = [1,2,3,4,2,2,2,2]
>>> lst.remove(2)
>>> lst
[1, 3, 4, 2, 2, 2, 2]

## apped and remove only take one thing, if you want to do like multiple appendages or remove 
you would have to just call it multiple times 

### a sequence, drill this in. 
a sequence is just an abstraction for obejcts that have a fintie length and idnexed elements
### finite [fai nai t]
a list is a specific big data type in python. sequence is not a specific data type in python 
sequence is a colelciton of behaviour that various data types can take on 
that is the idea of data abstraction, we can say the data types follow this abstract 
we can do the same things with those data types 
do you need to import libaries? those are built into python standard libraries 

#### pop(i): remove and return the element at index i. pop also mutate the list but it also returns the element that it removes. only the method that has side effect with return values 
can we change together these list mutation methods? 
what is actually happening? 
if we pop two off, is that what you were asking? 

>>> lsit = [1,2,3,4]
>>> list = [1,2,3,4]
>>> list.remove(2)
>>> [1,2,3,4,5].append(6)
>>> list.remove(2).remove(3)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list
this is not a list which causes us a error 
this is like a common misconception is that these methods will return the result list 
####  there is no need to return the list, drill in here, we can just reference the rsults of wahtver the mutation was 

#### the nature of pop that we want to get the element back 
i will not get into immediately 
there are certain instances where you want some element of the list 
note that we are not actually returning the list 
we are returning the element 

in fact, something interesting is that if i mutate the list, i actually change the list ]


# identity versus equality 
#### the equality operator == checks whether two expressions evalaute to equal values 
#### the identiy comparison operator (is) checks whether two expressions evalaute to the same object 
i constructed them two separate times 
knowing this is really useful, we can see how we mutate the objects 
the identity comparison operator (is) checks whether two expression expression evalute to the same object 

>>> lst1 = [1,2,3,4]
>>> lst2 = [1,2,3,4]
>>> lst1 == lst2
True
>>> lst1 is lst2
False

we want to think of it more just like objects 
if i were to diagram these out , they have the same values in them 
if i assign lst 3 = lst 1 
i am adding a new name in my diagram, i do not make a copy in my diagram
two of which points to the same list 
if i mutate one object in list 1 , references the same list it does  change 
list1 is list 3 

>>> ls3 == lst1
True
>>> ls3 is lst1
True

assignment does not change to anything, asisgnment makes it point to somethign else . it still points to the original object 
it affects any object that those names point to 



another mutatble obejct 
# Dictionary 
a python dictionary is another type of mutable obejct
it stores mappings from keys to values 
it stores a colleciton things whereas lists store values 
### dictionary stores mappings from keys to values 

## a list cannot be a key for dictionary !!!!  the key of the dictionary cannot be mutable 
>>> d = {[1,2] : 2}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list


here is how construct the dictionary 
d = {'a': 1, 'b': 2, 'c':3}
>>> d['a']
1
list is a ordered colleciton of values whereas with dictionaries because you hae thiis key and value pair 
but instead providing some index, we are gonna provide the key 

## when i mean a dictionary is mutable, it means i can change the contents of this dicionary without having reassign it 
#### you can only have one of each key so keys must be unique in the dictionary 

i assign to some value all that does is to add to the dictionary 
dictionairies are not ordered, they are not in deterministic order place on them 
### the order could also being switched around 
>>> d = {'a': 1, 'b': 2, 'c':3}
>>> d['a']
1
>>> d['b'] = [2,3,4]
>>> d['b'][1]
3

look up value corresponding to it 
can you loop through a dictionary? 
>>> for k in d:
...     print(k,d[k])
... 
a 1
b [2, 3, 4]
c 3

k is bound to the key here 
i can also loop through the values 
and get it like that 



the other object is called Tuples 
# Tuple is an immutable sequence, it is pretty much like list, you can do the exact same thing with it . it follows exact instruction like a sequence abstraction , it has a fintie length and integer indexes for its element but it is not immutable 
## its contents cannot be altered
t = (1,2,3)
t[2]
len(t)
if i try to assign someting, because it does not support item assignment 
>>> tuple[2] = 2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment

# another thing about dictionaries and tuples is that dictionaries' keys must be immutable 
we could not have made a key for the dictionary as a list 
the list is unhashable.
## the keys in the dictionary is not mutable whereas in tuple tha works



why would you ever want to use tuples? there are instances 
you need someting to be immutable. in those cases such as add the key a sequence 


summary 
a sequence is an abstraction for data types that have a fintie length and indexed elements 
sequence behaviors include indexing, checking membership, slicing, finding the lengt, and concatenating 
a list is a type of sequence that stores elements of any data type 

mutable objects represent values that change over time 
a python dictionary is a mutable obejct that stores mappings from keys to value 
a tuple is an immutable sequence 











