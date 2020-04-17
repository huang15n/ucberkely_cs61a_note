Lecture 8 Tree Recursion 

it builds off of soem of the ideas we talked about 
some general logistics 
particularly with the group portion
it is due on Friday 
we would like to emphasize that use the subset of it 

it will greatly benefit you 
you master the content that 
we will get the most out of this project 

it is completely optional 
your strategy will paired against xx receive extra amount of credits 

there is a few spots remaining 
please do sign up at this link here 


just to reiterate, this is going to be broken up 
it will center around the theme
understand the idea of funcitonal abstract to study the idea of higher order function 




# Recursion 
consider the scenario
we identified this as you base case 

let us formalize these words 
standing very far back in the line 


#### base cases: the simplest form of the problem 
#### recursive calls: smaller version of the problem 
#### use the solution to the smaller version of the problem to arrive at the solution to the original problem 
if we have the result of the person in front of us, which captures a lot of ideas you have been seening all week 
you made this assumption , that goes upon that bigger concept/. 
when we provide certain input, we get certain output 

underlying implementation. a powerful idea that really strongly uses 
how we can leverage this idea 


cascade -> goal: print out a cascading tree of positive integer n 
ideas: if n is a single digit, just print it out 
otherwise, let cascade(n // 10) floor dvision 10 take care of the middle and print n around it 
we can print n around it 
what i would recommend is to pause the video and translate them into code 
attempt to translate 


>>> def cascade(n):
...     if n > 10:
...             print(n)
...             cascade(n//10)
...             print(n)
...     else:
...             print(n)
... 
>>> cascade(486)
486
48
4
48
486

#### we assume it works , use this smaller version of the problem 
here is an alternative one 
## if two implementations are equally clear, then shorter is usually better 
## in this case, the longer implementation is more clear 
####  when learning to write recursive funcitons, put the base cse first 
#### when writing recursive functions, it is a good idea to make the base case and recursive case clear in your code. 


Fibonacci sequence: name after this person 
we start with the zeroth number of sequence , and the first number, the way we get the next digit is by summing get the digit 
to get every subsequent digit 
that corresponds to xxx 
this sequence can go on forever, it shows up a lot in nature, a nice little spiraual 

let us build out a few ideas of what we want to do 
ideas: the first fibonacci numbers are known; if we ask for 0th and 1 st number, we know it immediately 
otherwise , we sum up the previous two numbers 
>>> def fib(n):
...     if n == 0 or n == 1:
...             return n
...     else:
...             return fib(n-2) + fib(n-1)
... 
>>> fib(2)
1
>>> fib(8)
21



i want to reiterate very important point, we trusted it 
we had to make that assumption before we sum them up 
to make that clear 

break down this large problem we are interested in



iterative fibonacci, this will alow us to think about the problem in a slightly different way 
for reference 
let us consider thinking about this problem as such 
perform an iterative process of moving the window along 




#### in the recursive state of mind 
#### in theory, we can write recursive functions iteratively 
#### recursion and iteration are two different ways to think about a problem 



rely on recursion is the sum of the previous 
in iterative version, we eseentially started off at smalles version and built its way up 

tree recursive processdures are generally difficult to write iteratively 
it is a slight exception to build it up 
if you need to try multiple possibilties at the same time, ou should use tree recursion 

each of the enumerations, we are gonna keep these on the side in the recursive mindset 

#### to build up to a bigger problem that we are interested in 
find simpler instances of the problem 
it encompasses all the possibilities we can have 
it will capture all the possibilties , one direction 
that is gonna represent another possibility 


granted! we have this path down 
any other branches come out here 

to signify that we follow this branch we cannot get to a vliad parition 
we try to count up the number of ways 
that accumulates in our sum 
once we get to the state that 
we built out in xxx 
a lot of complex ideas 


to arrive at the solution 


recursion has three main components:
base cases: the simplest form of the problem 
recursive calls: smaller version of the problem 
use the solution to the smaller version of the problem to arrive at the solution to the original problem 


when working with recursion, use functional abstraction assume the recursive call gives the correct result 
tree recursion makes multiple recursive class and explores different choice 





















