# Setting up ssh key

```
 cat ~/.ssh/id_rsa.pub
...

$ ssh-keygen -o -t rsa -C "<my email address" -b 4096
...
Generate file path(just press enter to use defaualt)
...
Enter SSH key pasword twice
...
Copy the  SSH key using the command below
$ cat ~/.ssh/id_rsa.pub | clip
...
Paste the code into the SSH key setup box in the gitlab user profile section
...
Give the key a meaningful name

```
