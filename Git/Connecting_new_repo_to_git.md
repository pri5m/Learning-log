# Connecting a new project to git(hub)

```
git status
...
git add .
...
git commit -m "First commit"
...
git remote add <localprojectname> <url generated from setting up git repo in github console>
...
git push -u <localprojectname> master
<Enter github credentials>
...
```

Was getting confused about the use of 'origin' in git commands as I was getting the error message:

```fatal: remote origin already exists```

For some reason the use of 'origin' is used in examples. It was not clear that this should(could) be the artifactID that you created when setting up the project
