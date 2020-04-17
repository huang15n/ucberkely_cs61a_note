it is due Thursady, try to get that done as soon as you can
it is going to release 
stay on the top the material 
we have this in place 
guide you and pull you along 
signups for our mentoring sessions, recurring sections if you are interested in doing that 
it is a potlock, a fun social event and have a great time. fill out the forms 


we will center around the theme with particular goals 


# while loops , we touched upon a bit at the end of last week 
execute rule for while statement
1 evaluate the header's expression 
we fulfill the header expression 
2 if it is a true value, execute the suite and return to step 1 
it stays unchanged 
we start off with xxxx 



>>> def fact(n):
...     i, total = 1,1 
...     while i < n:
...             i += 1 
...             total += i 
...     return total 
... 
>>> fact(4)
10

we check the header expressions 




# abstraction
1 assignment is a simple form of abstraction: bind names to values 
2 function defintion is a more poweful form of abstraction: bind names to a series of computations 

## the length of hypotenuse 
this goes right into the notion of function abstraction 
3 functional abstraction is the idea that we can call functions without thinking about how the function works 
that is how the computer performing these operatioion 
we don't concern with what happened inside


environent diagrams: we have a formalized way to do it 
1 formalization of how python code is evaluated,
2 has a set of rules that guides our procedure 
listing our rules: 
always start in the global frame 
when a function is defined 
1 create a function value in the following form: 
func <name> (<formals>) [parent =<label>]
the parent is the frame in which the function is defined 
2 bind <name> to the function value in the current frame 

when a function is applied 
1 add a local frame and copy the parent of the function
2 bind the <formals> to the arguments in the local frame 
3 execute the body of the function 

when we make a binding, we evaluate the right hand side first. 
we are done with the result  


variable lookup 
lookup name in the current frame 
lookup name in parent frame, its parent frame, etc .. 
we stop at the global frame, throw an error otherwise 
it refers to this function, as a result of this code. 




## nested def statements 
we will see an example 
it looks like a lot of going on here, let us look at the def statement 
we arrive at the def statement, which takes in a single argument n 
>>> def outer_function(x):
...     def inner_function(y):
...             return x + y
...     return inner_function
... 
>>> outer = outer_function(10)
>>> inner_outer_total = outer(20)
>>> inner_outer_total
30

take a moment to inspect what you have 
we can bind the name to a particular value. to the resulting value. when we make a new binding

when you are ready, keep resuming the video 
>>> def repeat_operation(function, times_of_operation, argument):
...     while times_of_operation > 0:
...             argument = function(argument)
...             times_of_operation -= 1
...     return argument 
... 
>>> def function(parameter):
...     return parameter * parameter
... 

i hope you have had a moment to try out this 
we open up a new frame 





# lambda expressions == > expression that evaluate to functions!!!! 
let us break down what this actually means 
>>> square = lambda x : x * x 
>>> square(100)
10000
>>> cube = lambda x : x * x * x 
>>> cube(10)
1000
>>> multiplication = lambda x, y : x * y
>>> multiplication(10,20)
200
z = lambda first_parameter ,second_parameter, third_parameter : first_parameter * second_parameterftake

lambda is a function with parameter that returns the value of operations 
it is important to note that is a function with the syntax lambda 

let us formalize this through the beauty of environment diagram 
what hsould keep in mind 
lambda expressions versus def statement 
this looks awfully similar , let us look at the resulting diagrams 
the name is bound to the next line, which takes in arguments 


make a note that xxx instead of using a lambda functioin we use a def, the behaviour is identical
it is only for your benefit 
do not worry about carrying around this 


# higher order functions 
a function 1 take a function as an argument value, and/or returns a function as a return value 




# summary: 
1 abstraction helps us manage complexity 
2 lambda functions are similar to functions defined with def, but are nameless 
3 environment diagrams formalzie the evaluation procedure for python, we can deeply understand any piece abotu how the code that you are writting actually works 

you have a lot of practice with this  
do not have an intrinsic name  
very soon, we will work with functions 

















