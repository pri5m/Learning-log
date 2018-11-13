```
$ git config --global user.name "..."

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject
$ git config --global user.email "@..."

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject
$ git init
Initialized empty Git repository in C:/Users/c1712480/IdeaProjects/ClientProject/.git/

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ git remote add origin git@gitlab.cs.cf.ac.uk:c1712480/team4_client_project.git

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ git add .
warning: LF will be replaced by CRLF in .gitignore.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in build.gradle.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in gradle/wrapper/gradle-wrapper.properties.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in gradlew.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in settings.gradle.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in src/main/java/com/nsa/team4/clientproject/ClientprojectApplication.java.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in src/test/java/com/nsa/team4/clientproject/ClientprojectApplicationTests.java.
The file will have its original line endings in your working directory.

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ touch README.md

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ git add README.md

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ git add .

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ git commit -m "Initial commit"
[master (root-commit) 934b7bb] Initial commit
 11 files changed, 351 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 README.md
 create mode 100644 build.gradle
 create mode 100644 gradle/wrapper/gradle-wrapper.jar
 create mode 100644 gradle/wrapper/gradle-wrapper.properties
 create mode 100644 gradlew
 create mode 100644 gradlew.bat
 create mode 100644 settings.gradle
 create mode 100644 src/main/java/com/nsa/team4/clientproject/ClientprojectApplication.java
 create mode 100644 src/main/resources/application.properties
 create mode 100644 src/test/java/com/nsa/team4/clientproject/ClientprojectApplicationTests.java

c1712480@NSA107D1A0AE75B MINGW64 ~/IdeaProjects/ClientProject (master)
$ git push -u origin master
Warning: Permanently added the RSA host key for IP address '131.251.168.40' to the list of known hosts.
Enter passphrase for key '/c/Users/c1712480/.ssh/id_rsa':
Enumerating objects: 28, done.
Counting objects: 100% (28/28), done.
Delta compression using up to 4 threads.
Compressing objects: 100% (16/16), done.
Writing objects: 100% (28/28), 53.20 KiB | 2.96 MiB/s, done.
Total 28 (delta 0), reused 0 (delta 0)
To gitlab.cs.cf.ac.uk:c1712480/team4_client_project.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

```
