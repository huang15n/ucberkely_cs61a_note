
1

I do not have the count, helping your out with questions, trust with a lot of information 
the act of writting programs for particular tasks 
we will explore aspects 
declaring CS major 
you restricted in what you can do , set you up, prior experience 
statistical inference
go over different problems 
get more individualized attention 
composing programs, help each other out 
i am currently attempting to record this 
count on them 
i am gonna get to that 
recurring dropin sessions 

here and there 
the textbooks are all embeded there 
you are focused on learning, doing it out of interest 
take a break 
i will get there in a little bit, i am gonna move on  
frantically, it is more targeted for xxx, regularly with the same group of students 
more individualized 
you want to commit to going there 
reinforce the material 
but unfortunately 
collaborate with each other, it is not curved , the introductory survey, it is submitted to xx 
you work through it 
earn out to xx points 
maxing out your score 

give alternates, irresolvable 
after maxing/recover out your participation score, can be used toward exam recovery point 
we are running a little behind that  

there is no dependency on xxx 
you scale a lot more than it with your fellow 
with this last one exception, do not browse interent , run similarity detection, kick you out of this course 
do not publicly share it 

the content of this course 
1.1 fundamentally, what problems can be solved using computation 
1.1.1 we have the common enemy as complexity , how we manage that compelxity  
1.1.2 we master the art of abstraction 
1.1.3 programming paradigms  
demand a lot of you 
nitty gritty 
any prior exposures 
at the choice of pace, have a lot fun, as a general advice  
1.2 how do we solve those problems using computers  
1.3 what techqniues lead to effective solutions 



computer sciecne is a tremoudously braod academic dsicpline 
the areas of globally distributed system, artificial intelligence, robotics, graphics, security, scientific computing, computer architecture, and dozens of emerging subfields all expand with new techniques and discoveries. 
the rapid progress of computer science has left few aspects of human life unaffected. commerce, communication, science, leisure and plictics have all be reinvented as computational domains 

the high productivity of cs is only possible because the discipline is built upon an elegant and powrful set of fudamental ideas. all computing begins with representing info, specifying logic to process it, and desgining abstractions that manage the complexity of that logic. mastering these fundamentals will require us to understand precisely how computer interprete computer prgrams and carry out computational processes 





Course Overview: 
center around a theme with a specific set of goals 


what is in the program 
programs work as by manipulating values 
an expression in program evaluate to values 
1 primitive expression evaluate directly to values with minimal work 
2 operator combine primitive expressions into more complex expressions 
3 the python interpreter evaluates expressions and disipalys their values 








Typically, computer science is a tremendously broad academic discipline 

the areas of globally distributed systems, artificial intelligence, robotics, graphics, security, scientific computing, computer architecture, and dozens of emerging subfields all expand with new techniques and discoveries 

the rapid progress of CS has left few aspects of human life unaffected -- commerce, lesiure and politics have been reinvented as computation domains 


the high productivity of cs is only possible because the discipline is built upon an elegant and powerful set of fundamental ideas 

all computing begins with representing information, specifying logic to process it and designing abstractions that manage the complexity of that logic 
mastering fundamemtals will require us to understand precisely how computers interpret programs and carry out computational processes 

creative commons attribution noncommercial share alike licsense 

define computational process, preferrably one that many humans and a great variety of comptueres can all understand 

python is a widely used programming language that has recruited enthusiasts from many professions 
developer communities are tremendously important institutions 
collectively

dedicated members often achieve celebrity and widespread esteem for their contributions 

the python excels as an instructional language because, throughout its history, it has emphasized the interpretability of code 
reinforced by xx guiding principles of beauty 
it is broad set of features support a variety of different styles 
in addition, it's combination of great flexibility and accessibility allows students to explore paradigms, and then apply their newly acquired knowledge 

illustrative examples, increasing your facility with xx should come naturally as you progress through the text


trigonometric stuff , logarithm, summation 

stick to one that is I am curious in particular 


# an expression describes a computation and evaluates to a value 



Eddies-MacBook-Pro-2:cs61a eddiehuang$ python3 
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 26 2018, 23:26:24) 
[Clang 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 4 
4
>>> 4 + 3 
7
>>> (2 + 3 ) * 10 / 2
25.0
>>> import add, mul from operator 
  File "<stdin>", line 1
    import add, mul from operator 
                       ^
SyntaxError: invalid syntax
>>> from operator import add, mul 
>>> add(4,5)
9

I can refer to it 
look a little formally 
we are not limited to the expressions 

add (2,3) 
operator operand operand 
operators and operands are also expressions 
so they also evulate to value 


# Call Expressions 
evaluation procedure for call expression 
1 evaluate the operator 
2 evaluate the operands from left to right 
3 apply the operator a function to the evaluated operands/ argument 



# Nested call expressions 
human evalaute inside out 
skip around 

how different pieces fix together 

2 
type python code after the prompt, >>>. the python interpreter reads and executes what you type 
carrying out your various commands. 

interactive controls: each session keeps a history of what you type 
to access this history 
presss Control-P, Control-N, Control-D exists a session, which discards this history 



think of this section as a sneak preview of features to come 
python has builtin support for a wide range of common activties 
manipulating text, displaying graphics, and communicating over the internet 


it is an import statement that loads functionality for accessing data on the internet 
in particular, it makes available a function called urlopen, which can acccess the content at a uniform resource locator, URL, a location of something on the internet 



3 
statements & expressions, code consists of expressions and statements. broadly, computer prorgam consist of instructions to either: 
1 compute some value 
2 carry out some action 

statements typically describe actions 
when the python interpreter executes a statement, it carries out the corresponding action 
on the other hand, expressions typically describe computations 
when python evaluate an expression, it computes the value of that expression



4 
functions, functions encapsulate logic that manipulates data. urlopen is a function. 
a web address is a piece of data, the process by which the former leads to the latter may be complex 
we can apply this process using only simple expression because that complexity is tucked away within a function 


5 
objects, a set is a type of object, one that support set operations like computing 

an object seamlessly bundles together data and the logic that manipulates that data 

6 
interpreters:  evulating compound expression requires a precise procedure that interprets code in a predicatble way
a program that implements sucha a procedure, evaluating compound expression, is called an interpreter 
they are unique in their generality 
however, its great flexibilty allowed us to process a large amount of text with only a few statements and expresisons 
all of these core concepts are closely related 
functions are object, objects are functions, and interpreters are instances of both 


switch over here 

>>> file = open('file.txt')
>>> txt = file.read().split() 
>>> txt[:25]
['This', 'is', 'the', '100th', 'Etext', 'file', 'presented', 'by', 'Project', 'Gutenberg,', 'and', 'is', 'presented', 'in', 'cooperation', 'with', 'World', 'Library,', 'Inc.,', 'from', 'their', 'Library', 'of', 'the', 'Future']
>>> len(txt)
901325
>>> txt.count('the')
23242
>>> words = set(txt)
>>> len(words)
67505
>>> 

>>> txt.count('the') / len(txt) * 100
2.5786481014062628


>>> max(txt)
'}'
>>> max(words)
'}'
>>> max(words, key=len)
'tragical-comical-historical-pastoral;'


reverse the word: 
>>> 'draw'[::-1]
'ward'

>>> {w for w in words if w[::-1] in words and len(w) > 4 }
{'refer', 'stink', 'level', 'knits', 'steel', 'speed', 'sexes', 'keels', 'devil', 'minim', 'drawer', "'mum'", '******', 'redder', 'stops', 'deeps', '*****', 'madam', 'spots', 'leets', 'lived', 'sleek', 'reward'}
>>> 


the equivalent point 
we are getting way beyond what we are talking about 
evidently separated 
>>> max(words, key = lambda x: x.lower().count('e'))
'ever-esteemed'



7
error, while computers are tremendously flexible, they are extremely rigid 
the nature of computers is looking at volumnes of dat quickly 
computers are shockingly fragile and mechanical 
it lacks anything like real insight 

to build somehing useful, constructed out of enny, little operations 

the riidity of computers will become apparent as you experiment with interpreter 

diagnose the cause of unexpected errors is called debugging 
1 test incrementally, it is composed of modular components tha can be tested individually 
2 isolate errors : it can typically be attribtued to a particular modular component 
try to diagnose a porblem , trace. the erro to the fragment of code 
3 check assumptions: interpreters carry out your instruciton to the letter 
4 consult others, it is shared in the process of group problem solving 
it will persist throughout your cs career 


I am gonna wrap it up now 













