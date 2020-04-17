these annoucements might be a little outdated 

we have some instructions and logistics about that 
focus on the next homework 
signups for recurring and dropin mentoring sections 
we have some set of goals 
the ideas are centered around the data 




how the size of data affects program

motivate the idea of time complexity 

those are too far apart 

# factors: 
goal: count the number of factors n > 0 so that retierate a factor by definition is a number that evenly divides another number -- has no remainder 
the goal of the function that we are trying to write is one that counts the number of factors of n 

we can test each number from 1 to n 
ideas : test each number from 1 to n 

we check this procedure here we perform a modulos 
we want to increment total because we found a factor of n 
so that we eventually get to N 
once we exit the while loop we can return the number of n 
we are investigating the number 

we are gonna use this alternate implementation of the signature perform a similar iteration 



ideas: 
for every factor, n divided by that factor is also a factor 

>>> def factor(n):
...     total = 0
...     i = 1
...     while i * i < n:
...             if n % i == 0:
...                     total += 2
...     if i * i == n:
...                     total += 1
...     return total 
... 



# High Level Time Complexity 

let us count the number of times we need to perform 
we perform the body of this while loop 
each modulus operation takes some amount of time 
for small n, the difference between n and square root n is small 
they are not extraordinarily far apart 
however, if n is very large, the difference is huge 
this gap between n and square root is huge 
when evaluating runtime, we want to think about very large input size 
we will formalize these ideas 


# Space Consumption 
we just talked about time complexity by looking at the operations for a procedure 
which environment frames do we need to keep during evaluation 
values and frames in active environments consume memory 
memory that is used for other values and frames can recycled 
we need to consider which is frame 
same goes with values 


# orders of growth :  a method for bounding the resources used by a function by th size of the input 
provide some formalization 
sets in Math so we are a little fluent in what we are gong to disucss 
s is a set 

n  : size of the problem 
R(n) measure of some resource used -- time or space 
R(n) <- Theta(f(n))
means that there are positive constants k1 and k2 such that 
k1 * f(n) <= R(n) <= k2 * f(n) as n gets large 
seem overly mathematical 
so we can upper bound 

buil the intution of what we are trying to say 

same general properties of the set 
### constants : constant terms do not affect the order fo grwoth 
n <- theta(n)
## we can disregard the constant factor 
## logarithms: the base of the logarithm does not affect the order of growth 

## lower order terms: the fatest growing part of the conmputation dominates  the rest 
n ^ 2 <- theta (n ^ 2)
it is insignificant, it won't really make a dent which can verify that 



# properties 
# nesting : when an inner process is repeated for each step in an outer process, multiply the steps in the outer and inner processes 
Outer loop takes m steps 
inner loop takes n steps 

overlap(m, n) <- theta(m * n)
important note: before multiplying, check to make sure that both processes run to completion and that neither terminate early 

perform this initialization here 
we need to perform this operation and times 

frames and values. 
at any given time is not depedent on the size of n 
to the space complexity


let us assume we have arrived at the steps 
all the work that was done over here 
all the frames and values are recycled 
that was used to store those frames, the highlighted path 
no matter where we are in this tree, the number of active frames will not exceed n 



# exponentiation 
our goal is to calcuate B to the power n >= 0

b ^ n = 1 
otherwise we can say b = b * b ^ (n - 1)
>>> def exp(b, n):
...     if n == 0:
...             return 1 
...     else:
...             return b * exp(b , n - 1)
... 
>>> exp(10,2)
100


>>> def exp(b , n):
...     if n == 0:
...             return 1 
...     elif n % 2 == 0:
...             return square(exp(b , n // 2))
...     else:
...             return b * exp(b, n - 1)
... 
the time / space complexity grows linearly to n 



this is a procedure of growth 
so in conjunction to that 


# comparing the order of growth 
theta(b ^ n) exponential growth , incrementing the problem scales R(n) by a factor 
theta(n  ^ 2 ) quadratic growth, incrementing n increaes R(n) by the problem size n overlap (n ,n)
just to iterate the overlap 
theta(n) linear growth , increment the amount of work 
theta(square(n)) square root growth 
theta(log n) logarithmic growth  multiplying n by a factor incremetns R(n) 
theta(1) constant    the problem size does not matter 
the number of the frames does not depend on the number of size 

in comparison to the size of the problem, which is a handy thing to refresh what we talked about 


# Important Sums 
when you are computing the order growth 
write this fancy summation all the way to some specified integer 
for our analysis 



# summary 
orders of growth : a method of bounding the resources used by a function by the size of the input 
ignore constant terms 
base of logarithm does not matter 
lower order terms are dominated 
space complexity: memory consumed to run a procedure  
time complexity: amount of time it takes to run a procedure 
















































