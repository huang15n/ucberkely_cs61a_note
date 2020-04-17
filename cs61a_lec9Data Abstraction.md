
lecture 9 data abstraction 

that is what i got for today 
you will be placed in xxx 
you want to get checked in 
happening at the usual time 
signups for recurring sections 
continue our journey through the idea of abstraction with data abstraction 
useful data types that you can construct 



visualization of restaurant ratings 
stand at any given time , polygon 
we can see a cluster of restaurants 
you hover over any of these polygons 
some of them are predicated, the existing rating
he is out of luck 
it gives what resturant you should go to 
what are you going to be working ith abstract data types that represent restaurant , reviews 
paritition cluster of restaurants 
predict ratings for users giving their existing ratings 
a predicator line 


Abstraction: 
this is the first time, this is gonna be a little bit of a review 


#### abstraction in real life
using these pedals to stop or move the car 
we are not thinking about things like brakes and blueprints 
we abstracted away the details how this car works 

#### variable assignment abstracts away details of computation 
#### function defintion abstracts away details of procedure execution 
the name x will be bound to the value 
this expression will evaluate to xxx 
the details of compuation for the values were abstracted away 
the value resulting from the computation 
function defintion abstracts away details of procedure eexcution 
given some function if you know the name of the function, what arguments the function takes in, you can call it to execute 
i do not need to know how the function is defined, the details is abstracted awaay 


## functional abstraction, we do not need to know how a function is implemented in order to call it. 
the implementation results in the correct output. it does not matter which is under the hood 
the behaviour the funciton, the detail do not matter to me 
a functional abstraction happens inside the body, because we are able to call 
# taking the leap of faith, it works based on the described behaviour of that without having finished implementing the function 


## data abstraction 
rational numbers 
numerator/denominator using the word fraction 
#### rational number an exact representation of factions as a pair of integers 
arithmetic expression,  as soon as division occurs, the exact representation may be lost~! 


be able to treat rational number as a whole unit, keeping its integer parts 
for the duration of this, compound value 

#### rational number, date , geographic location , latitude and longitude 
we are interested in using and manipulating compound values as singgular units with extractable parts 


#### we can implement rational numbers as abstract data types ADTs 
numbers, strings, lists. 
#### an ADT consists of a constructor and some selectors 


constructor, creates a rational number 
selector: selects from a rational number 
respectively 

i bind it to the name, at this point, we just have to know when you call the constructor is the rational limit 


to reitearte , i use a function to create a rational number, i pass in my rational number and get my denom, numer 
i have an exact representation of the whole integer 
rational number arithmetics. multiply these 
here is a general form of that 

given these general numbers attempt to write functions that implement these arithmetic operations 
specifically, it better return a call to the constructor here 
fill in this function defintion 



i am gonna ahead 
implement rational number arithmetic 



to begin 
# abstraction barrier 
operate the car , drivers do not necessarily need to know a barrier separate the parts prevent users to touch these parts 
how the car is built and engineered 
they was enought to manipulate these numbers 
there is a barrier separating code 
pet your code 

we did not need to know the implementation details of the constructor and selectors to write code that manipulates data. there is a barrier that 



# abstract violations 


using a list, index into the list 
the implementation matches the dscribed behaviour 
all these functiosn are on the same side of the abstrctions 
they can all safely assume rational numbers 

#### violating the abstract barrier 
by passing into element lists, this should not cause any errors 
the issue here is we are using the constructor, we assumed the implementation. 



#### with the reciprocal of it 
we do not use the selector, to make things seven worse 
it assumes the implementaion of rational numbers 
why is this bad?
#### it is the underlying abstract might change 
#### changes in the underlying implementation should not cause errors 
we decide to change our implementation, now our rational is implemented with the numbers 

we are attempting to get the keys , assuming the implementation will be bad, we do not assume that 
we use selectors and constructors, as long as this implementation matches the described behaviour that we assume when writing the function, it should work 

#### change ADTs does not have to be that dramatic 
we would like to refine our abstract data types 
when we pass in a numerator or denominator 
as our programs develop, we want to refine our ADT as much as possible 


to simplify the fractions, rewrite our constructor 
go ahead and return the list
by defintion by being a divisor 


at first glance, it does not cause any problem, 
####  wheras where, we use the constructor and get that improvement will propogate through 

## Abstraction Barriers : an abstraction barrier separates the implementaton and use of an ADT 
draw this out a little further to perform computations 

#### we use the constructors and selectors in order to implement these layers 
you should have to cross this layer 
#### we assume the behaviours are expected 
#### in fact, it does not have to be lists, implement the construct the lists 

#### as programmers writing the constructor and selectors we do not need know how python lists are constructed, you can index into it 
they do not explicitly exist, we should not cross them 


let us try to get motivated 
# why data abstraction? 
#### more readable code, constructors and selectors have human readable names 
you are trying to represent rational numbers 

#### make collaboration easier, other programmres do not have to worry about implementation details 
we are kind of computationally heavy to implement 
this comes up a lot in software engineering startup 

#### prevent error propagation, fix errors in a single funciton rather than all over your prorams 
the error will show up once 


# to summarize the lecture 
#### 1 we can represent data with multiple components as abstract data types 
#### 2 a constructor creates a single value of a particular data type and selectors allow us to access attribtes of a value 
#### 3 an abstraction barrier exists between the implementation and use of data representations 
#### 4 assuming a data type's implementation is known as an abstraction violation 
why namely if the implementation were to change 























