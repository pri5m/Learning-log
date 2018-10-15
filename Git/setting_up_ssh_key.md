# Setting up ssh key

[Doc  links](https://docs.gitlab.com/ee/ssh/)

```
Check that there isn't already a key using this command
 cat ~/.ssh/id_rsa.pub
...
Set up key by linking to gitlab profile

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
