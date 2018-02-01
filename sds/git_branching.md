[Session slides](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4539349_1&course_id=_381772_1)

[git book online](https://git-scm.com/book/en/v2)

**Kaizen ideas**

Commit, pull, merge, test, push- Small changes are easier to merge- Do this often!

**Tagging**

Used to record a significant sttate/point in time

**Dealing with tasks that overrun time deadline**

- Descope x completelty

Is release good engough? Resources do nothing?

- Split x

Can it be split? Is any one part usable?

- Delay until x complete

Impact on other plans. Marketing, sales, customer service, operations ect.

- Isolate x

Develop x separately

- A combination of the above

**Feature toggling**

if else statements used to control what can be accessed or not. Yes/No

Can combine a switch so use the iso code for a country so a feature only appears in one country, ab testing- Facebook

**Branching**

- $ git branch (name of branch)

- $ git checkout (nameofbranch)     Switch brances

- $ git commit -a -m "change"       Commit on a branch

- $ git checkout master      Go back to "master"

**Branching is cheap in Git**

Because a branch in Git is in actuality a simple file that contains the 40
character SHA-1 checksum of the commit it points to, branches are
cheap to create and destroy. Creating a new branch is as quick and
simple as writing 41 bytes to a file (40 characters and a newline).


This is in sharp contrast to the way most older VCS tools branch, which
involves copying all of the project’s files into a second directory. This can
take several seconds or even minutes, depending on the size of the
project, whereas in Git the process is always instantaneous. Also,
because we’re recording the parents when we commit, finding a proper
merge base for **merging is automatically done for us and is generally
very easy to do. These features help encourage developers to
create and use branches often.**

