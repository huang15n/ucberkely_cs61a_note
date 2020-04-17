

the idea of higher order functions 


# higher functions is a function that takes a function as an argument value, and / or returns a function as a return value 
because it took a function as an argument 
it can look kind of intimidating 

we can define functions 
such that we can make it easier for ourselves 



it is completely optional 
compete against your fellow students 
focus around the theme and goals to get through 



the idea of functional abstraction to study this idea throgh higher order functions and recursion 

the tool to fight against complexity is the abstraction 
the way we build functions to be able to use them as abstractions 


review lamdas and higher order functions :
>>> square = lambda x : x * x 
>>> square(10)
100
>>> multiplication = lambda x, y : x * y
>>> multiplication(10,20)
200

# Lambda Expressions and def statements 
#### they both created functions with behaviours
#### both functions' parents are the frame in which they are defined 
#### lambdas are expressions and are limited in that they can oly immediately return a single expression (no statement)
re-evaluate the functions 
we do have the benefits 
#### def statement can contain other statement even other statements and use a return statement to return  a value 
##### only the def statement gives the function an intrisic name 
#both of them are bound to it and functionally identically 




#functions are first class, meaning they can be manipluated as values 
i can assign name to functions , when we do passing functins in 
a higher order function is 
1 a function that takes a function as an argument and / or 
2 a function that returns a funciton as a return value 

but why should we use them? 
we are gonna talk a bit of a roundabout way and how we abstract things on functions 
sort of this rationale behind high order functions 


## domain: the set of possible inputs a function may take as arguments 
## range: the set of possible output values a function may return 
## behaviour: the relationship between input and output 


how do you design functions , make them maintainable and useful ? the best practices 
every functions has a domain : the set of possible inputs a function may take as arguments 
range: the set of possible output values a funciton may return 
behaviour : the relationship between input and output 
it all comes back to abstraction 
you can compose them together in interesting ways 

do not repeat yourself -- duplicated code is hard to maintain 
## we would like encoutered the bugs in, implement your functionality once and execute it many times 
## spilt that chunk of code and call it each place 


that will be cancelled 



## a guide to designing functions 
1 give a function exactly one job, but make it apply to many related situations 
but it should do one thing. apply to many related situations 



generalizing patterns with arguments 
regular geometric shapes relate length and area 
they each have a formula to calcuate the theory 
the area of the hexagon, the program breaks 
now these function start getting complicated 
>>> from math import pi, sqrt
>>> def area(radius, shape_constant):
...     assert radius > 9
...     return r * r * shape_constant 
... 
>>> area_square = lambda r : area(r,1)
>>> area_circle = lambda r : area(r,pi)
>>> area_hexagon = lambda r : area(r, 2 * sqrt(3) / 4)


note that not only does do we get the assertion error here but als ofor the circle 

we give them in palliative inputs 

generalizing over computational processes, look at summations 
it is actually an approximation of pi 


we need to pass that in expects that function 
formal parameter that expects to be bound to a single arument functions 


on the top of your head 
get rid of duplicated code 


function composition, a more complex one 
this news takes in a new function what essential what it does is passed into f 
>>> def make_adder(n):
...     def adder(k):
...             return n + k 
...     return adder 
... 
>>> def square(x):
...     return x * x 
... 
>>> def compose1(f,g):
...     def h(x):
...             return f(g(x))
...     return h
... 
>>> 
we can pass around this combined function 


self-reference:
we will find this helpful for doing the commentary problems on your project that has been released 
it creates a new function, itself actually calls it 
let us walk through this to get an understanding of how this might work 
you might want to refer back to this 

>>> def print_sums(n):
...     print(n)
...     def next_sum(k):
...             return print_sums(n + k)
...     return next_sum
... 
>>> print_sums(1)(3)(5)
1
4
9
<function print_sums.<locals>.next_sum at 0x10151f9d8>



this would just be a function that gets thrown away 

a higher order function is a function that takes in a function as an argument and /or returns a function as a return value 
these functions can be used to: 
express general methods of computation 
remove repetition from programs 
separate concerns among functions 
we saw a practical use of them with the generalization of the summation function 
function composition composes two functions together, into one function, which can now be called in place of two together 
higher order functions are even able to reference their outer functions 








