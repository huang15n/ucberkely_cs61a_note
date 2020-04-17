
have some familarity with it 
just as a remainder,. a bit more involved and take a bit more time and effort 
we urge you to benefit from , you can feel out. get a handson look at the material covered that day if you did not get to do that 
supplementary , are events where you get into mentoring groups with students through a worksheet 
reasons that are irrevocable 


overview; it will center around a theme with a specific set of goals, we weant to familarize everybody with the fundamentals of programming 
delve a bit depepr into what is a function 

it is a bit loaded, i am gonna point out 


# Values
#### programs manipulate values , all avlues have a certian type or categories
 we have quite gone over
#### the statemnt serve as instructions, these statemnts contain what are known expressions -- mathematical expressions. the program consists statements 

# expression : an expression describes a computation and evalautes to a value 
#### primitive expression evaluate to value in a single step 
>>> from operator import add 
>>> add(1,"2")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
>>> 1 + 2
3
>>> 1 + "3"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
>>> 1 + '3'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'

we will go over that , non primitive expression requre work. arithmetic expressions combine expression with operators and evaluate to numbers. 
# this is not an exhaustive list, expression is just a simple piece of code that evalaute to a value 


# Names 
names are labels refer to them can be a little bit easier , name can only bound to a single value 
values can be assigned to names to make referring to them easier 
a name can only be bound to a single value 
one way to intrpduce a new name in a program is with an assignment statement 
>>> from math import sqrt 
>>> sqrt(100)
10.0


# environments
### names and their values are stored in environments 
to execute an assignment statement 
1 evaluate the expression to the right of =
2 bind the value of the expression to the name to the left = in the current environment 


the length of the hypotenuse and there is theorem . pythagorean theorem a^2 + b ^ 2 = c ^ 2 . same sides and third side. recap wha we jus saw 




# functions 
### functions are a series of statemetns that map input to output. the input is known as the arguments. the output is known as the return value 
break this def statement becomes intrisnic name 

# defining new functions : use a def statement to define function. it becomes intrinsic name of the functino, the true name of any function created using a def statement. parameters, names assigned to the function's argument, body, sequence of statemetns that are executed when this function is called, we bound that value to some name, no evaluation takes in place 


# calling functions, 

##### something refers to the funciton to some parentheses, a call exprssion applies a function to some arguments. it consists of an operator and 0 or more operands 
##### to evaluate call expression 1 evaluate the operator, which should evaluate to a function 2 evaluate the operands to get the argument values 3 apply the value of the operator/ a function the value of the operands/ the arguments 
it is coming from time to time 

i was tabling earlier 

# return 
### return statement specifies the expression to evalaute to obtain 
### a return value for a function call. two properties to remember 1 once a return staement is reached, execution of the function termiantes 2 if a function body contains no return statement, the function returns None by default. None is a special value, it only means it is nothing 

# a note on abstraction, assignment statements bind names to values 
# assignemnt statements bind names to values 
# def statements bind names to statements 
# in either case we hide the details of some computations behind a human  readable that we can reasily refer to , hiding away we find something. there are some deterministic output each time 
we can manage complexity with abstraction 
abstracting away the details  






we have identified in python some of the elements that must appear in any powerful programming languages 
1 numbers and arithmetic operations are primitive builtin data values and functions 
2 nested function application provides a means of combining operations 
3 binding names to values provides a limited means of abstract 

function definitions, an abstraction technique by which a name can be bound to compound operation, which can then be referred to as a unit 

Function definitions consist of a def statement that indicates a <name> and a comma-separated list of named <formal parameters>, then a return statement, called the function body, that specifies the <return expression> of the function, which is an expression to be evaluated whenever the function is applied:

def <name>(<formal parameters>):
    return <return expression>
The second line must be indented — most programmers use four spaces to indent. The return expression is not evaluated right away; it is stored as part of the newly defined function and evaluated only when the function is eventually applied.
>>> def square(x):
...     return x * x
...
>>> square(100)
10000

We can also use square as a building block in defining other functions. For example, we can easily define a function sum_squares that, given any two numbers as arguments, returns the sum of their squares:
>>> def sum_square(x):
...     return square(x) + square(x)
...
>>> sum_square(100)
20000

our subset of python is complex enough that the meaning of program is nonobvious. what if a formal paramter has the same name as a builtin function without confusion in more detail? 

an environmenmt in which an exprssion is evaluated consists of a sequence of frames, deicted as boxes 
each frame contains bindings, each of hwich associates a name with its correspnding value. there is a global frame. 
assignment and import statements add entries to the first frame of the current environment. 
so far, our environment consists only of the global frames 

to evaluate a call expression whose operator names a user defined function, the interpreter follows a computational process 
as with any call expression, the interpreter evaluates the operator and operand expressions , and then applies the named function to the rseulting argument 

Applying a user-defined function introduces a second local frame, which is only accessible to that function. To apply a user-defined function to some arguments:

    Bind the arguments to the names of the function's formal parameters in a new local frame.
    Execute the body of the function in the environment that starts with this frame.

The environment in which the body is evaluated consists of two frames: first the local frame that contains formal parameter bindings, then the global frame that contains everything else. Each instance of a function application has its own independent local frame


local names, one detail of a function's implementation taht should not affect the function's behaviour is the iumplementer's choice of names for the function's formal paramters 
this principle -- that the meaning of a function should be independent of the parameter names chosen by  its author -- has important consequences for programming languages 
the simplest consequence is that the pramter names of a function must remain local to the body of the function 
we say that the scope of a local name is limited to hte body of the user defined function that defines it. when a name is no logner accesible, it is out of scope
this scope behvior is not a new fact about our model , it is a consequence of the way environemnts work 



choosing names; the interchangeability of names does not imply that formal parameter names do not matter at all 
on the contrary, well chosen function and paramter names are essential for the human interpretability of function defintions 
the guideline are adapted from the style, which serves as a guide for all non-rebellious programmers 
a shared set of conventions smmoths communication among memberes of a community 
as a side effect of conventions, you will  find that you code becomes internally consistent 
1 functions names are lowercase, with words separated by underscores. descriptive names are encouraged 
2 functions name typically evoke operations applied to arguments by the interpreter or the name of the quantity that results 
3 parameter names are lowercase, with words separated by underscores, single word names are preferred 
4 paramter names shoule evoke the role of the paramter in the funciton, not just the kind of argument that is allowed 
5 bsingle letter paramter names are acceptable when their role is obvious, but avoi l , lowercase el, O captial Oh, or I captial I to avoid confusion with numerals 
there are many exceptions to these guidelines, even in standard librarys 
python has inherited words from a variety of contributors, and the result is not alway consisstent 




function as abstractions, 
it exemplifies the most powerful property of user defined functions
it is defined in terms of the function, but relies only on the relationship that it defines between its input arguments and its outpute values 
the details of how it is computed can be suppressed, to be considered at a lataer time. indded, as far as it is concerned, it is not a particular function body, but rather an abstraction of a function, a so called funtional abstraction 
at this level of abstraction, any funciton that computes the value is equally good 
in other words, a function defintino should be able to suppress details 
the useres of the function may nbot have written the function themselves, but may have obtained it from another programmer as a blackbox 
a programmer should not need to know how the funciton is implemetnated in order to use it 




aspects of a functinal abstract. to master the user of a function abstraction, it is useful to consider its three core attributes 
1 the domain of a function is the set of arguments it can take
2 the range of a function is the set of values it can return 
3 the intent of a function is the relationship it computes between inputs anmd ouputs as well as any side effects it might generate 
understanding functional abstractions via their domain,l range and intent is critical to using them correctly in a complex program 


operators, mathemtical operator provided our example of a method of combination, but we have yet to define an evaluation procedure for exprssions that contain these operators 

python expressions with infix operators each have their own evaluation procedures, but you can often think of them as shorthand for call expressions.


infix notation can be nested, just like call expressions , python applies the normal mathematical rules of operator precedence, which dictate how to interpret a compound expression with multiple operators 

the nesting in the call exprsesion is more explcit than the operator version, but also harder to read python allows subexpression grouping with parentheses, to override the normal precedence rules or make the nested structure of an expression more explicit 

when it comes to divisoin, python provides two infix operators: / and // 
the former is normal division, so that reults in a floating point, or decimal value, even if the divisor evenly divides the dividend 
the // operator, on the other hand, rounds the result down to an integer 
these two operators are shorthand for truediv and follordiv functions 
you should feel free to use infix operators and parentheses in your program 
idiomatic python prefers operators over call expressions for simple mathematical operations 


desiging functions: functions are an essential ingredient of all programs, large and small, and serve as primary medium to express computational processes in a programming language 
so far, we have discussed the formal proeprties of functions and how they are applied
fundamentally , the qualties of good functions all reinforce the idea that functions are abstractions:
1 each function should have exactly one job. that job should be identfiable with a short name and characterizable in a single line of text. functions that perform multiple jobs in sequence should be divided into multiple functions 
2 do not repeat yourself is a contral tenet of software engieering. the so call DRY principle states that multiple fragments of code should not describe redundant logic. isntead, the logic should be implemented once, given a name, and applied multiple times. if you find yourself copying and pasting a block of code, you have probably found an opoortunity for functional abstract 
3 functions should be defined generally.
thse guidlines improve the readability of code, reduce the number of errors, and often minimize the total amount of code written
decomposing a complex task into concise functions is a skill tha takes experience to master 
python provides serverl features to support your efforts 


documentaiton 
a function defintion will often include documentation describing the function, called a docstring, which msut be indented along with the function body 
docstring are congentionally tripped quoted 
the first line describe the job of the function in one line 
the following lines can describe arguments and clarity the behavior of the function 
>>> def pressure(v, t, n):
        """Compute the pressure in pascals of an ideal gas.

        Applies the ideal gas law: http://en.wikipedia.org/wiki/Ideal_gas_law

        v -- volume of gas, in cubic meters
        t -- absolute temperature in degrees kelvin
        n -- particles of gas
        """
        k = 1.38e-23  # Boltzmann's constant
        return n * k * t / v

When you call help with the name of a function as an argument, you see its docstring (type q to quit Python help).

>>> help(pressure)

when writting prorgams, include docstring for all but the simplest functions 
code is written only once, but often read many times 
comments can be attached to the end of a line following the # symbol. 

default argument value; a conseuqnce of definining general functions is the introduciton of additional arguments 
functions with many arguments can be awkward to call and difficult to read 
we can provide default values for the arguments of a function 
when calling that function, arguments with default values are optional
if they are not provided, then the default value is bound to the formal paramter name instead 


as a guideline, most data values used in a function's body should be expressed as default values to named arguments, so that they are easy to inspect and can be changed by the function caller 









