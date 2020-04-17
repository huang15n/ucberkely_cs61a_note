

you won't be required to analyze or write code using the ideas from this 

please follow along at a high level 

preface a few outdated 
please fill out the survey as usual 



paradigms with that means to study different means used in computing 
to learn about how these techqniues can change the way you think about a problme 



memoization 
to motivate this idea, we implemented fibonacci call trees 
repeated the work to xxx

let us do a time and space complexity analysis 
we would need to nearly double it 

this process grows exponentially 

it would be the longest path of this tree 
so space complexity is linear 

fibonacci with memoization
ideas: 
1 keep a cace of all of our work so far 
2 if we have alrady computed a particular number, we can retrive it from the cache 



# Dynamic Programming: identify subproblems and solving subproblesm in the order of incrasing complexity to avoid repeating work 
the goal is similar to memoziation 
1 do the easier stuff first 
2 build up to the larger problem 
step1 : identify the subproblems 
step2 : strategize order of solving the subproblems 


ideas: subproblem : called that with smaller inputs 
 solve subproblems in order of increasing inputs 
 save space: throw away results of small inputs to it when we get to a larger input 

(old) ideas: sliding window: at any time we only care about the numbers in the window
perform an iterative process of moving the window along 


push the idea toward a slightly more complex problem called longest common subsequence 
goal: find the length of the longest common subsequence between two words. a subsequence can contain non consecutive characters 

ideas: if one of the words is empty, any common subsequence is empty 
otherwise compare first characters 
if same, inspect the rest of both words 
if different, inspect each word with the rest of other word 

index into the words instad of slicing them 

lcs ('sequence1', 'sequence2')
1 + lcs('equence1','equence2')
1 + lcs('quence1','quence2')



>>> def lcs(word1, word2):
...     if word1 == '' and word2 == '':
...             return 0
...     elif word1[0] == word2[0]:
...             return 1 + lcs(word1[1:],word2[1:])
...     return max(lcs(word1,word2[1:]),lcs(word1[1:],word2))
... 



longest common subsequnce let's analyze time and space complexity in the worst case assume both words have length n 
for each recurisve call, we need to perform a slice and store the words 

i have abstracted it away 


LCS with indexing 
ideas: use i and j to represent indices 
we do not have to slice the word and we do not have to store them 

>>> def lcs(word1, word2):
...     def helper(i, j):
...             if i == len(word1) or j == len(word2):
...                     return 0
...             elif word1[i] == word2[j]:
...                     return 1 + helper(i + 1, j + 1)
...             return max(helper(i, j + 1), helper(i + 1, j))
... 

still have 2n recurisve calls, but ow we lose cost of slicing ans toring 

LCS with memoization
idea: we should perform this work once, and resue the rsults 

perform work only when we encounter a pair of input we have not seen 

# LCS with dynamic programming 
ideas: 
we saw a table structure, try filling it in 
subproblems : helper called with smaller inptus 
solve subproblesm in order to increase intputs 
save spaces: throw away results of small inputs to helper when we get to larer inputs 



entires in last row or last colum are 0
compar first characters
if same ,add 1 to entry in bottom right 
if differnt , get max of right and down 



start at bottom most right most entry 
fill in table upwards and to the left 
discard old colums 
each entry takes constant time to fill in and there are theta(n^2)
total entries we need to keep between n and 2n total entries at any time 



LCS with dynamica programming 
high level overview of code 
1 make a table from a list of lists 
2 have indices tha decrement from the lengths of the words to 0
fill the table as we go 
discard old column when we fill in a new colum
add a new initailized column to the front of the table 



future directions: 
an engineer can do for a dime what any fool can do for a dollar 
you will also be concerned with resoruces used 
analyze tradeoffs betwen different approaches 
think deeply about why you need to use the resources that you are using 
thinking critically about the structure of the problem will alow us to solve it in more efficient ways 


these ideas show up in job interviews
and on the actual jobs 

these tools also show up in academic research whever you are building an algorithm 

we always want to understand what resoruces we are using 
often times, we go through the process of imprveoments, which then helps us understand the problem better before thinking of how to optmize 




daunting this complicated problem 
we solve it in a very naive way 
we try to come up with a working implementation 


exploit certain pattersn and the structure of the problem 
and think about how we can optimize our work 
minimize a process 
reduce the number of resources 



# Summary 
memoization: instead of repeating this work, we can remember the rsult 
dynamic programming: identify subprobles and solving subprobles in the order of incrasing complexity to avoid repeating work 


do the easier stuff first, get that out the way 
build up to the larger problem 
step 1: identify the subproblems 
step 2: strategize order of solving the subproblems 


















