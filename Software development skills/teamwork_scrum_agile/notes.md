# But first … What is Scrum (in 2 minutes)

“Scrum is a framework for managing software development. Scrum is
designed for teams of approximately 10 individuals, and generally relies
on two-week development cycles, called "sprints", as well as short
daily stand-up meetings.” (Wikipedia, scrum, 2017)

# What is a user stories (in 2 minutes)

Many agile techniques use user stories

◦ Short descriptions of functionality told from user’s perspective that have value for a
user/customer

The most widely used template for writing user stories is from Coen (2004):

“As a <type of user>, I want <some goal> so that <some reason>.”

They can be written at varying levels of detail

◦ Large user stories are known as Epics

◦ These are split into multiple smaller user stories to complete in one iteration

◦ Related stories can also be organised into themes

Define acceptance criteria, each with a clear pass/fail result, to make the
story testable

Stories will need to prioritised

There are techniques for estimating effort for implementing stories

# Managing Dependencies in Software Development

Fit dependencies arise because all the activities performed by team
members are contributing to the development of the same software
product

Flow dependencies arise because artefacts produced in one activity of
the development process are used by team members in a subsequent
activity

Shared dependencies arise due the problem of allocating resources
(e.g. people, machines, money) to activities when these resources are
constrained

# Advantages of Version Control

**Prevent problems with Simultaneous Update**

◦ Two (or more) programmers each take a copy of the same component and make a
change

◦ Last copy submitted overwrites changes made previously

**Control Changes to Code**

◦ Roll back changes if there is a problem

◦ Need to check changes do not conflict with others who might share or use the code

**Keep Variants Consistent**

◦ To support different platforms or operating systems

**Keeping team members aware of relevant changes**

◦ Keep change history through meaningful comments

◦ See differences between versions

# Dealing with Merge Conflicts

Git usually will figure out how to integrate new changes – particularly if
you pull just before you push to the remote directory

There are situations where you may have to step in and tell Git what to do

◦ If two people change the same lines in a shared file

◦ If one person deletes a file while the other decides to modify the same file

◦ If two people add two separate files with the same name

Git will tell you that you have “unmerged paths” in git status

Work with the other developer to make sure you sort out the conflict.
