progress in difficulty 
a gentle application of concept 
take an attempt at extra quesitons to challenge you in different ways 
get through them 
we intend for the worksheet to be longer 
seek help when you need 


offer resources 

do not be disrespectful of your fellow classmates 
as a constructive forum 


set aside however the exam was adminstered for 
simulate the exam 

fill in the blanks 

# 19 Tail resursion 

# recursion version iterations 
in python, a new frame is opened for each recursive call before the current one is closed 
python has special iterative constructs 


in scheme, a frame can be removed for there is no further work to be done 



# tail recursion 
what we just saw was tail recursion: iterative recursion 
a procedure is tail recursive if everything recursive call is a tail call 
main idea: no additional work to be done after making the recursive call 

a tail call is call expression in a tail context 
the following are exaples of tail context 
the last body subexprssion in a lambda/ a function 
the consequent and alternative in a tail context 



# map : goal, apply a function to every item in a list. return a new list. use reerse 
# idea : think iteratively, keep track of progress, easy to add to the begining of the list. the reulst in a reversed order 

# 20 Interpreters 
address all the remarks 
signups for xxx 
it happens at usual time 


study data structures and special forms that introduce new rules for evaluation 
understand how computer programs are interpreted and evaluated 



# interpretation : computers only understsands one language - binary code 0 and 1 
# human cannot naturally write 0 and 1 . programs written in python, c java, need to be translated 
# some languages are compiled and some are interpreted translated on the fly 

# an interpreter allows users / humans to enter exprssion in a particular language 
# translate the exprssion in order to the computer to do thigns 
# presents the result of evaluating the expressions back to the user 

# there are two languages involved:
# implemented languages , the language being interpreted 
# implementing langauges : the langue the interpreter is implemented 

most interprets are implemented as an infinite loop that 
1 reads command line input 
2 evaluates the expression and 
3 print out its value 



# reading input : lexical analysis turning the input strings into a collection of tokens 
# a token is a single unit of the input string e.g. literals, names, keywords, delimiters 
# syntactic analysis: turning tokesn into a representations of the expression in the implementing language 
# the exact representation depends on the type of exprssion 



self evaluating exprssiosn boolean and numbers  
use python booleans and python numbers 
symbols use python strings 


# representing combinations (<operator><operand><operator>)
evaluating expression, after readign expression, we can then evaluate them to obtain values. rules for evaluating an exprssion depends on the expression's type 


self-evaluting expression: these exprssions evaluate to themselves 


# Lecture 21: Macros

# that is not affliated with the course 
a recurring mentoring section 

# a macro is an operation performed on the source code of a program before evalatuion 
# marcos exsit in many languages, but are easist to define correctly in a language like Lisp 

# evaluation procedures for Macros 
recall evalatuion procedure used for regular call exprssions 
1 evalaute the operator subexprssion which evalues to a reular proceduer
2 evalaute the operand exprssions in order 
3 apply the procedure to the evaluated operands 

macros , on the other hand, do the follwoing 
1 evaluate the operator subexprssion, which evalautes to a macro procedure 
2 apply the macro procedure to the operand expresions without evaluting them first 


the but unquoted 
macros effectively allow you to define new special forms for the language 
they do this by taking in peices of unevalauted code, constructing a new pieces of code, and then evalauting i 
it does not natively support 















