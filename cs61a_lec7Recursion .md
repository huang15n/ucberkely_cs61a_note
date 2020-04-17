recursion is a function that calls itself 
this is a funny easter egg 


on this midterm logistics 
you have to follow these instructions
these would have been already passed 
we made clarification 

reoccuring and drop in 



## functional abstractions so that means how could we use functions to sort of break down problems into smaller pieces that we can know use

# intuition behind recursion 
suppose you are waiting in line for a concert
you cannot step out of the line because you will immediately lose your spot 

##### an interative algorithm might say a while loop 

that is one way to do it 

#### a recursive algorithm , you figures it out, keep asking 
this is the idea behind recusion . it is sort of like you are a part of solution instead of by standing 


# a function is called recursive if the body of that function calls itself either directly or indreictly
##this implies that executing the body of a recursive function may require aapplying that function multiple times 
recursion is typically the harder concept to wrap your head around 

reading recursive functions, what would running this function display . 
to wrap your head around , your intuition 
it is important to separate them in my opinion 

>>> def fact(n):
...     if n == 0:
...             return 1 
...     else:
...             return 	n * fact(n-1)
... 

we will walk through it 
reading and evaluating codes !! 
learn all the rules we already know in order to read the recursive functions 
different frames keeps track it  

visualize execution , bind variables to functions in the global frame 
follow the same lookup operator evaluate the operands 
we open up a new frame 
we cross out xxx 


## what we mean by closed is when a function has a return value then it closes then it returns that value up 
each cricle represents a recursive call
it conveys the same idea 
it works back up 


# Structure of a recursive function 
1 one or more base case, usually the smallest input 
2 one or more recursive calls with simpler arguments 
for now let us focus only one recursive call 
simpler does not necessarily mean smaller numerical, it means closer to the base case 
3 using the recursive calls to solve our larger problem 


## recursive loop faith 
we have to assume the recursive call works putting faith into the fact that recursive call works 
understand with tangible numbers 
sometimes it is easier to convert it to mathematical notation 
this exclamation point
how do you trust it? why is it that a case we do this? 



we know if we were to really look inside the leap of faith 
verifying the correctness of recursive functions 
1 verify that the base cases work as expected 
2 for each larger case, verify it works by assuming the smaller recursive calls are correct 
open the Pandora's box 
works the way back up 


it is a lot of talking 
to sum all the digits of a number 
1 base case, me giving you some tips on how to approach a problem liek this 

>>> def sum_of_digits(number):
...     if number < 10:
...             return number
...     else:
...             return number % 10 + sum_of_digits(number//10)

round it down 
verbally we are summing any numbers 
2 recursive call with smaller arguments
3 use recursive call to solve the problem 

i will talk through it 
we can cut off to xx 
to break this apart 



takeaways 
1 base case
2 recursive call with smaller arguments, we can do over and over 
every step of the way we are doing the same operation 
we are cutting off the digits 
3 use recursive call to solve the problem 


count up, let us implement a recursive funciton to print the numbers from 1 to n 
assume n is positive 
instead of me giving you a hint 
think to yourself 
>>> def count_down(number):
...     if number == 1:
...             print(1)
...     else:
...             print(number)
...             count_down(number-1)
... 
>>> count_down(10)
10
9
8
7
6
5
4
3
2
1
>>> def count_up(number):
...     if number == 1:
...             print(number)
...     else:
...             count_up(number-1)
...             print(number)
... 
>>> count_up(10)
1
2
3
4
5
6
7
8
9
10


we have to do the least amount of work 
we know recursively we have to print more values 
in order for us to consitently print each number 
to decrement by one 
you are having a hard time trusing this 
step through the frame 



# Mutual Recursion 
### when a recursive function is divided among two functions that call each other, the funcitons are said to be mutally recursive 
this will go forever 
we can divide how we solve the problem in separate ways 


is_even() , is_odd() 
we have constraints of problem, some circumstance 
think about a problem differently 
in a slightly different 
divisible by 2, one more than an even number 
0 is even, i frame this problem like this 
it relies on checking its implementation 

## it nudges us towards the recursion, what is known to you? 
do not skip out it , let this code skin in for a little bit s

if a number is even if its one more than an odd number 
a number is odd if it is one more than an even number 

>>> def is_even(n):
...     if n == 0:
...             return True 
...     if is_odd(n-1):
...             return True
...     return False 
... 
>>> def is_odd(n):
...     if n == 0:
...             return False
...     if is_even(n - 1):
...             return True 
...     return False
... 

there is a way we can simplify this 
it was worth sharing 
##  as such, mutal recursion is no more mysterious or powerful than simple recursion, and it provides a mechanism for maintaining abstraction with a complicated recursive program 


## iteration versus recursion 
## technically all functions that can be written iteratively can be written recursively and vice versa, but sometimes the solution is easier using one 
## the code and thought process can be very different to approach the solution 
we usually try to constrain the solutions 


you get to choose it 
thinking about it mathematically 
the number that we pass in 
they are both valid , this is just to compare them 
i am not going to go over it 
you need to be able to come up with both of them 



summary: 
recursive functions call themselves, either directly or indreictly, in the function body 
reading recursive function require drawing out diagrams and following the same environment diagram rules 
all recursive functions have one or more base cases, have one or more recursive calls. , and use the recursive calls to solve the problem 
leap of faith is the idea that we assume the function works even before we have finished implementing it 
mutual recursion is when two functions call each other and is useful to maintain abstraction 


under the hood 













