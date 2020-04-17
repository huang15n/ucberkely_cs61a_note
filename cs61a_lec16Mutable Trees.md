
i am recording this a couple of days in advance 
for your reference w have made a walkthorugh video 


please reach out to us 
have a method and regrade request if you have reviewed you midterme and sawa a discrenpancy 

they have not been released yet 
complete phase one and two 
you get one point of extra credit 




the goals for this week are to study the paradigm for objects 



terminolgy from our abstract data type trees 

a node: which is a single unit that contains a label 
label : value at a node 
root : top node at the tree 
branch L substree whose parent is the root 
leaf : a node with no subbranches 


trees reqires a label and some branches 
>>> class Tree: 
...     def __init__(self, label, branches = []):
...             self.label = label 
...             self.branches = branches
... 


we bind label and branches to the instance attribtues label and branches 
trees are inherently recursive structures 
>>> t = Tree(3, [Tree(2, [Tree(5)]), Tree(4)])
>>> t.label
3

we are gonna denote that here , this is not the standard convention 



>>> def tree(label, branches=[]):
...             return [label] + list(branches)
... 
>>> def label(tree):
...     return tree[0]
... 
>>> def branches(tree):
...     return tree[1:]
... 



Objects versus ADT: 
in class based representation, we are able to easily mutate the tree that we construted 
whereas with the abstract data type representation, we are not 
ADT :

"""
this is the regular immutable tree function call 
which means the values inside the tree construct is immutable 

"""

def tree(label, branches=[]):
	for b in branches:
			assert is_tree(b)
	return [label] + list(branches)


def label(tree):
	return tree[0]

def branches(tree):
	return tree[1:]


def is_tree(tree):
	if type(tree) != list or len(tree) < 1:
			return False
	for b in branches:
		if not is_tree(b):
			return False
	return True


def is_leaf(tree):
		return not branches(tree)


use the ADT we use the function call label 
we cannot assign a value to a function class 




# Tree Processing 
we want to create a function map 
the goal is to apply a function to each node in the tree but also mutate the tree for it to contain thos new values here 



t1.map(lambda x : x + 2)
t1.map(lambda x : x * 4)
t1.map(lambda x : x * x)
we are mutating the original tree that we construct due to the call to map 
how did we build this up? 



ideas : 
1 apply fn to current node mutate tree 
2 call map on branches 

take a moment to pause the video and use these ideas to build out the map 
work on this implementaiton by itself 
that captures the first main idea that we developed here 
then what we can do is we can interate through the branches 


we use the dot notation to access the branches 
we are trusting our recursion to handle or work on our branches 
>>> class Tree:
...     def __init__(self, label, branches =[]):
...             self.label = label
...             self.branches = branches
...     def map(self, fn):
...             self.label = fn(self.label)
...             for b in self.branches:
...                     b.map(fn)



>>> class Tree:
...     def __init__(self, label, branches =[]):
...             self.label = label
...             self.branches = branches
...     def map(self, fn):
...             self.label = fn(self.label)
...             for b in self.branches:
...                     b.map(fn)




we performed a procedure and we trust the recursion will mutate this tree in which every node has been squared perform that interaction 




# contain :  goal, deterime whether an element exists in a tree 

in our visual inspection we should see true 

idea: check label of current node 
otherwise, check branches 



with a very recursive flavor 
i am trusting that i have some method that i could on this branch for that matter is in that branch 
it tells us the value that we are looking for is in the tree 






another data structure which extends our idea of trees 
it is a special structure 

# Binary Search Trees 
# a binary search tree is a tree where each node has at most 2 branches 
# left branch elements are all less than or equal to the label 
#  right branch elements are all greater than label 
# left branch and right branch are also BST's 



class BST:
	def __init__(self, label, branches=[]):
		for b in branches:
			assert isinstance(b, BST)
		self.label = label 
		self.branches = branches


	def is_leaf(self):
		return not self.branches

which of these trees hold the defintion? 
i have highlighted a lot of pieces that we need to use 

class BST:
	empty = () 
	def __init__(self, label, left = empty, right = empty):
		assert left is BST.empty or isinstance(left, BST)
		assert right is BST.empty or isinstance(right, BST)
		self.label = label 
		self.left , self.right = left, right 


	def is_leaf(self):
		return self.left is BST.empty and self.right is BST.empty

we use the word empty to represent an empty tupple, we change our assert statement and the left is empty as well as it is a BST


this node is a leaf 
let us enforce that now 

we no longer check the list of branches, we just check that left is that self dot left does not exit for this particular node that is leaf 

# Construction a BST
let us construct the tree 

def __init__(self, label, left = empty, right = empty):
		assert left is BST.empty or isinstance(left, BST)
		assert right is BST.empty or isinstance(right, BST)
		self.label = label 
		self.left , self.right = left, right
		if left is not BST.empty:
			assert left.max() <= label
		if right is not BST.empty:
			assert label < right.min()


we want to make sure all the items in the right branch are greater than the label 
so another way of saying that is the label is then right dot min 
we will see the impelemtnation 








# BST processing 

Max: goal find the largest element in a BST
we have our skeleton here which we are defining this function inside the class 

we abstract away before 
# we unravel the magic here 



all the items in the right branch must be greater than the value of the label 
we know these value must be larger than this one here 
we can get the maxiumum value , we know that value is the largeest value in the entire BST 


we want to come up with some ideas 
####   ideas: if right branch unavailable, return label 
def max(self):
		if self.right is BST.empty:
			return self.root
		return self.right.max()

	def min(self):
		if self.left is BST.empty():
			return self.root
		return self.left.min()




# contains: goal to deterime whether an element exists in a tree 
idea: checked label of current node. otherwise, check branches 
otherwise, check left 
if the item is greater than the label, we need to check the branch 

# this exploits the important property 

def __contains__(self, element):
		if self.root == e:
			return True 
		elif e > self.root and self.right is not BST.empty:
			return e in self.right 
		elif e < self.root and self.left is not BST.empty:
			return e in self.left 



check for what we are looking for



we saw this difference in implementation for contains 



# Time Complexity 
does this affect the time of complexity? 

is there a difference in time complexity when we check existence in a tTree versus a BST

runtime in terms of n the number of nodes 


roadmap :
build out an example tree as both a Tree and a BST 
perform existence operations 



# elucidate some of the ecxample 

the recurring shows what is going on 
we then iterate through branches 
we have completed investigating whether that is inside the subtree here 
we have to nearly search all of the items and nodes 
we still need to search it 
the time complexity for searching a tree is theta of n 
we cannot break down our problem much easier 
take the momeent to pause and think about the time complexity 



inspect this node here, we can immediately discard the node there 
we can cut our problem again in half 
and we see we found it 
based on the item that we are looking for 
the time complexity for contains is log n 



summary: 
we look at class based tree 
a tree created with a class is mutable , we can use the dot notaito to perform mutation 
a BST allow us to organize data in left branch and right branch based on value 
use recursion to process an ADT tree, a class based tree ,and a BST
A BST allows for more efficient saerch, theta(n) for Tree, theta(log n ) for BST . we can cut our prroblem in half 





we trusted our procedures to behave recursively on the branches 
























