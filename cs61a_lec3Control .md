why this picture is relevant? 
make everyone is on the same page 
they are fundamentally different 
what do functions evaluate to 

printing prints out the value. it does not evaluate to a value. we are not sure yet 
you can confirm to yourself 



>>> print(print(1))
1
None

the similarities are almost the same 
### None means that nothing is returned 
#### the special value None represents nothing in python. functions that do not explictly return a value will return None. 
#### None is not displayed when evaluated by the interpreter 
None + 5 : unsupported operand types for + 

printing is just a side effect: not a value that can be used by python 
return statemetns allow us to pass values between functions 
we wamt to get access to this value 



indicate which block we are on 

>>> def favorite():
...     return 'Ince Cream'
... 
>>> my_love = favorite()
>>> 
>>> my_love
'Ince Cream'
>>> my_love + 'is my love'
'Ince Creamis my love'
### I cannot add str to int 

### pure functions and non pure functions 
pure functions just return value 
we are feeding at aruments 


nested expressions: we always evaluate the operator. we have to evaluate this and that. feeds in one side effects 


# application of print and return. the operands of a call expression can be any expression .  this includes expressions that evalautes to functions, such as function names 



#  control -- creating logical path for program to follow. he represents the program 
we have a little tunnel , we do not program to execute every single time repeatedly 

######  expression in programs evaluate to values, statements are executed to perform actions 
##### but this is not enough to easily write most useful programs 
##### these functions are easiwer to write if we introduce control, special expression and stateemtns can control how the program is executed by the interpreter 


those are used interchangeably 

# conditional statements if statement 
a suit of statements 
if you clump the condition 
if <conditional expression>
<suite of statements>
elif <conditional expression>: 
<suite of statements>
else : 
<suite of statements>
##### syntax : always starts with if clause , zero or more elif clauses  zero or one else clause, always at the end 
##### execution rule for conditional statement 
##### each header is considered in order
##### 1 evaluate the header's expression if the header is not an else 
##### if the expression is true value or the header is an else, execute the suite and skip the remaining headers / all the rest of these 
the only thing will get outputted 



# boolean contexts 
>>> def absolute_value(x):
...     if x < 0:
...             return -x 
...     elif x == 0:
...             return 0
...     else:
...             return x 
... 

and so forth and so forth 
## boolean context is any place where an expression is evaluated to check if it is a True value or a False value. they encompass more than just the word in python 

# boolean expressions are special operators and, or ,not 
# <expr1> and <expr2> and <expr3> and ... 
evaluates to first value. if none are false, evaluates to the last expression. 
i spoil it 
expected a volatilized expression 

# <expr1> or <expr2> or <expr3> or ...
evaluates to first true value. if none are true, evalautes to the alst expression 

# not <exp>
evaluates to True if <exp> is a false value and False if <exp> is true value 


#### short circuiting is when an exprsesion returns the value and stops evaluating latter expression . if and finds a False value, it returns that value and stops evaluating remaining values 

#### if or finds a True value, it returns that value and stops evalauting remaining values 

# iteration -- act of repeating a process over and over again 
to iterate over something the while loop 
>>> def factorial(n):
...     i, total = 1, 1
...     while i < n:
...             i += 1
...             total *= i 
...     return total 
... 
it is gonna increment by 1 
we have simultaneous assignment here 
this is equivalent of syaing i equals 1 

something else is bouncing 
# execution rule for while statement 
1 evaluate te header's expression 
2 if it is a true value, execute the suite(swit) and return to step 1 
and we break out 


### while loops whenever we need to do something over and over again 
### while loop takeaways, we need the stop condition . when thinking about a problem , you canphrase the solution as do something. do something until some variable n is 1 
### need to increment closer to stop condition 
### you can make a while loop go forever by having the stop condition be true 

# for loops using range
##### execution rule for for statement using range
# for var in range(start, end)
# var first starts at start and we execute the suite 
# then var increments by 1 and we execute the suite again, we keep doing this until var becomes end and we stop   


control allows the interpreter to selectively or repeatedly execute parts of our program 
conditionals allows for different behavior beased on the input to and state of the program. 
iteration allows for parts of our program to be repeatedly executed a specfic number of times  
our pathways 







