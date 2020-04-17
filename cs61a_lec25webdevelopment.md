it helps you to understsand parts of software engieering 
editing software 



pip is a package management used to install and manage python package 
pip should already be installed if you installed python fro python.org 
Eddies-MBP-2:Desktop eddiehuang$ pip3 --version 
pip 19.2.3 from /Library/Frameworks/Python.framework/Versions/3.8/lib/python3.8/site-packages/pip (python 3.8)


we have a ton of packages whenever you have to type import 
require new packages download those from internet 
pip is a nice way to do that 


one important distinction 
pip3 and pip are different 
pip3 deals python 3 package management system 


if pip is erroring 


API applicaiton programming interface 
that is a fancy way of saying the code that allows programs to commuunciate 
i want to talk to some compnay's code i should not know how their code is implemented 
we abstract away their code and i just need to access what i want 
metaphor: the waiter is the API running between the customers user applciation and the ktichen the copanies 
most big companies have public APIs
you can customize it and use existing APIs 
freemium 



google apis drive APIs , Maps API, youtube APIs 
that integrates some of the stuff 


for time sake, i am gonna sort of go through the set up 
you can just look that up 

what we have dealt with is SQL is table
SQL is sometimes not best language 
all sorts of issues can arise to act as your database 



twilio API 
send messages programmatically 
with twilio you can send SMS/MMS/voice messages 
enable vidoe conversations in web/mobile apps 
enable two factor authentication with your apps 


# reading and writing files 
no super flashy but very important 
use cases : 
data analysis 
editing existing files 
anytime you need to automate a task of moving, renaming, writign reading files on your comptuer 

it is good for graphing, you find statistical analysis 


open(filename,mode)
filename: name of file 

mode:
'r' - read mode only being read 
'w' - write mode when editing or writing to a file 

import csv
>>> with open('craft.csv','r') as csvfile:
...     reader = csv.DictReader(csvfile)
...     for row in reader:
...             print(row)
>>> csvfile.close()




>>> with open('craft.csv','r') as csvfile:
...     reader = csv.DictReader(csvfile)
...     for row in reader:
...             print(row['item_description'])
>>> csvfile.close()



# Web development 
what is web development ? 
web development is a very broad term that describes any tasks associtaed with developing websites through the internet 
web developers/ engineers are developers/engineers that work on web development 


many companies rely entirely on websites for traffic and profit 
these companies need people to build and maintain their websites

all these things they optimize the track for traffic 


# front end development 
front end development manages everythign that users see in a web aplication 
front end developers are responsible for the look and feel of the site 
common front end languages: html, css, javascript 

draw mockups 


front end developer implementing the website 
web designer 
ui/ux designer focus on user interface and user experience 



# back end development 
back end development refer to the server side of an application and everything that comunciates bewtween the database and the browser 
common back end languages -- java, php , ruby , python 
they are focused on site responsiveness and sepped 
focused on how to store data effectively, and query it effectively 
back end engineer 
data engineer 

there is a whole bunch of people 


# full stack development 

that is what i will be doing at . small companies usually do not have enough poeple to have a whole team dedicate to front end or back end or even granular teams, so they have full stack engineers 
full stack development needs to know a little bit of everything not necessarily well 
the stack refers to both front end and back end 


you spread yourself pretty think 
a couple handful of web developers 
search it up


simple full stack web app with flask
what is flasj 
simple web framework using python 
every easy to set up and use! create web applciaitons in < 50 lines 


misc topics we did not go over but wanted to 
web scraping 
SQL pivot table 
python visualization libraries 
tons of cool apis 
python imaging library 










# Web Development

