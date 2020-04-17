we are moving on to this topic of languages 

our goals are to extend what we know about programming to another language 

how data types can be represented in another language 


# Scheme , it is a dialect of Lisp, it uses a lot of parentheses  
it is half century old 
a more civilized age, it is even designed 
he claims xxxx  

# teach a variety of programming techniqeus and core concepts 
1 to see some key components across many programmign languages 
expressions to be evaluated 
modularize programs 
2 to see what paradigms certain languages prioritizes 
in its entirety as complex as python 
3 to learn how interpreter are implemented 

its extremely minimal syntax. 
scheme's beauty lies in its simplicity 
it consists entirely of two types of expressions 
can be categorized into two kinds 

atomic expressions: self-evaluating expressions, booleans 
symbols: names bound to values 

the conventions for names and scheme is to hyphenate in between words 

a combination combines multiple expressions into a single expression 
these expressions are separated by spaces and contained with paretheses 
see angled brackets with some expressions 
it is an optional exprssions 
that was a quick overview of scheme exprsesion 


first categoory 
atoms: primitive values that cannot be broken up into smaller parts 
procedurs: function objects, either built in or user defined 
lists : a sequence fo zero or more values separated by spaces 

i have a set of parentheses 
the operator evalautes to a procedure and operands 
then i apply addition to the operands 
follow the special rules 

if the predicate evaluate to true or false 


combinations: 
all non primitive expression in scheme have the following ynstax 
(<operator> <operand1> <operand2>.....)
special forms have special behaviours that allow us to write compelx programs 
how to evalaute special form exprssion 
each special form has its own rules 
some operands may not be evaluated 

a combination of either a call expression or a special form expression 
the operator of a call expresison evalautes to a procedure 
the operator of a special form expression is a special form 

how to evalute call exprsesions: 
step1 evaluate the operator to get a procedure 
step2 evalaute all operands left to right to get the arguments 
step3 apply the procedure to the arguments 

anything underlined or highlighted in xxx 



special forms 
let us take a deeper look at each individual 

the define special form assigns a value to a name 
(define <name> <exp>)
	how to evaluate 
this is very much like an assignment statement 
this is deviates from python 
step1 evaluate the given expression 
step2 bind the resulting value to the given name in the current frame 
step3 return the name as a symbol 



let us see we can create functions in scheme 
the lambda special form returns a lambda procedure 
(lambda (<param1> <param2>) <body>)
step1 : create a lambda procedure with the given parameteres and body 
step2 : return the lambda procedure 

define functiosn with names 
the second version of define is a shorthand for creating a function with a name 
(define (<name> <param1> <param2> ...) <body>)
step1 : create a lambda procedure with the given parameters and body 
step2 : bind it to the given name in the current frame 


it is creating underlying functions 



control flow 
the if special form allows to evaluate an expression based on a condition 
(if <predicate> <if-true> [if-false])
step1 evalaute the <predicate>
step2 : if <predicate> evalautes to anything btu #f , evalute if true and return the value. otherwise, evaluate if false, if provided and return the value 


sanity check,
a bit of arsenal of special forms and expressiosn that we can use to write functions 


more control flows : the cond special form allows us to specify many conditions and consequences 
(cond (<pred1> <exp1>) (<pred2> <exp2>) ... (else <else-expr>))
how to evalaute 
step1 : evaluate <pred1> <pred2> etc, util one evaluates to a truth y value 
some consequent expression 
step2 : evaluates and return the expression corresponding to the firts truth.y predicate if no predicate evalutes to a truth y value, evalaute and return else expr f provided 




Lists: 
a brief overview of a list 
how scheme lists are structured 
constructing lsits: the built in lsit procedure takes in an arbitary number of argumetns and constructs a list containing the values of those arguments 


the quotes special form can be used to create a lsit literal 
(quote <expr>) <expr> 
step1 do nto evaluate <expr> return it as a value 
the built in procedure filter takes in a lsit and predciates procedure and returns a new list ocontaining only elements that fulfill the predicate 


accumlate and similar functions 



# filter, map, and reduce 
write a function filter-map-reduce that filters a list, maps a procedure to every element, and returns the result of reducing the resuling elements 


ideas: 
1 we should filter first so that we do not do extra mapping operations 
2 reducing is the last step 
3 the result of the filter is the input into map 

these first two points were kind of drawn out in lecture 
scheme programs consiss only of exprssions, all of whch can be cateorized into either atomic exprssions or combinations 
combinations are either call exprssion or special form expressions, and they differ in the vlaue of the operator 
scheme call exprsison are eluated just like they are in python, but each special form has its own rules of evaluation 





get quiet down a bit 
giving the video up 
i was having issues with xxx 

attempt to sync out
hopefully everything works out 
before we get to that 
i think the actual texture most would be fairly readable, it is a blusih screen 


# Pairs in Scheme 
the fundamental unit for data abstraction in scheme is the pair 
a pair can be constructed with the cons builtin procedure 
it consists of two fields , for weired historical reasons, theseare called the car and the cdr 
with spacing around it 
scheme pairs always have two elemetns the car and the cdr 

the linked list abstraction 
we call this seuqence of linked pairs a linked list 
you can implement linked lists in any language , but they are a core part of the schme language 


a formal defintion, we get the full defintion
formally, we define a list in scheme to be one of two things 
1 the empty list or 
2 a pair whose cdr is also a list 
note the recursive defintion 



like trees, linked lists are a recursive data structure 
duck through a lot 
it sort of in that way 



special handling of linked lists in scheme 
it doesn ot just like represents that 


displaying lsits 
because linked lists are so fundamental to the scheme language, it includes several features to make them easier to create and use 
pairs are generally displayed as car . cdr , so you would expect a list of the numbers 1 through 5 to look something like 
but scheme has a special rule to make this simpler 
if the cdr of a pair is another pair, or the empty list, remove the dot between the car and the cdr , and the parentheses around the cdr 
so , instead, the list of the numbers 1 through 5 as 


constructing lists, you do not need to make every list manually with cons 
scheme has a few simpler ways to construct lists 


# symbolic programming 
we are quoting maek a literal list, it is always being made 


writing code with scheme lists: linked lists are a recursive data sttructure, so it makes sense to use recursion to solve list porblem 
the built map procedure takes in a procedure and a list and returns a new list that consits of f (x) for every x in the original 
null and nil is different 
try implemeneting map!, which mutates the original list instead of creating a new one 



# Summary 
it has one compound type: the pair 
pair consits of two elements : a car and a cdr 
we can chain pairs togeteher into a linked list, the car of each pair contains an lement, while the cdr contains the result of the list 
scheme lists are linekd lists , a list in scheme is defined to be the 
the empty lsit or 
a pair whose cdr is a scheme list 
scheme code is made out of scheme lists, which means we can write code taht manipulates code 
scheme lists can be mutated with set car ! and set cdr ! 
because linked lists are a recursive data structure, it make sense to use recursion when solving scheme list problems 





























