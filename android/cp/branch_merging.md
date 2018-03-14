
c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (featu                                                  re-filter_form)
$ git status
On branch feature-filter_form
Your branch is ahead of 'origin/feature-filter_form' by 1 commit.
  (use "git push" to publish your local commits)
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .idea/vcs.xml

nothing added to commit but untracked files present (use "git add" to track)

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git status
On branch feature-filter_form
Your branch is ahead of 'origin/feature-filter_form' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git commit 'gitignore'
error: pathspec 'gitignore' did not match any file(s) known to git.

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git commit .gitignore -m '/.idea/vcs.xml
> git commit .gitignore -m '/.idea/vcs.xml'
> ^C

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git commit .gitignore -m '/.idea/vcs.xml'
[feature-filter_form a75c6ad] C:/Program Files/Git/.idea/vcs.xml
 1 file changed, 1 insertion(+)

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git push
Enter passphrase for key '/c/Users/c1712480/.ssh/id_rsa':
Counting objects: 24, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (21/21), done.
Writing objects: 100% (24/24), 3.10 KiB | 0 bytes/s, done.
Total 24 (delta 8), reused 0 (delta 0)
remote:
remote: To create a merge request for feature-filter_form, visit:
remote:   https://gitlab.cs.cf.ac.uk/c1714546/Welsh-Pharmacy-Team4/merge_requests/new?merge_request%5Bsource_branch%5D=feature-filter_form
remote:
To gitlab.cs.cf.ac.uk:c1714546/Welsh-Pharmacy-Team4.git
   212a6df..a75c6ad  feature-filter_form -> feature-filter_form

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git status
On branch feature-filter_form
Your branch is up-to-date with 'origin/feature-filter_form'.
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (feature-filter_form)
$ git checkout development
Switched to branch 'development'
Your branch is behind 'origin/development' by 8 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development)
$ git pull
Enter passphrase for key '/c/Users/c1712480/.ssh/id_rsa':
Updating a640b35..58a308b
error: The following untracked working tree files would be overwritten by merge:
        .idea/vcs.xml
Please move or remove them before you merge.
Aborting

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development)
$ git status
On branch development
Your branch is behind 'origin/development' by 8 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development)
$ git pull
Enter passphrase for key '/c/Users/c1712480/.ssh/id_rsa':
Updating a640b35..58a308b
Fast-forward
 .idea/modules.xml                                  |  4 +++-
 .idea/vcs.xml                                      |  6 +++++
 TestingAddingResource.txt                          |  0
 app/src/main/AndroidManifest.xml                   |  9 ++++++-
 .../nsa/welshpharmacy/ListPharmaciesActivity.java  | 28 ++++++++++++++++++++++
 app/src/main/res/layout/activity_main_menu.xml     |  3 ++-
 app/src/main/res/layout/list_pharmacies.xml        | 19 +++++++++++++++
 app/src/main/res/values/strings.xml                |  1 +
 8 files changed, 67 insertions(+), 3 deletions(-)
 create mode 100644 .idea/vcs.xml
 create mode 100644 TestingAddingResource.txt
 create mode 100644 app/src/main/java/com/nsa/welshpharmacy/ListPharmaciesActivity.java
 create mode 100644 app/src/main/res/layout/list_pharmacies.xml

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development)
$ git status
On branch development
Your branch is up-to-date with 'origin/development'.
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development)
$ git merge feature-filter_form
Auto-merging app/src/main/res/values/strings.xml
CONFLICT (content): Merge conflict in app/src/main/res/values/strings.xml
Auto-merging app/src/main/AndroidManifest.xml
CONFLICT (content): Merge conflict in app/src/main/AndroidManifest.xml
Automatic merge failed; fix conflicts and then commit the result.

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development|MERGING)
$ git status
On branch development
Your branch is up-to-date with 'origin/development'.
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:

        modified:   .gitignore
        new file:   app/src/main/java/com/nsa/welshpharmacy/FilterPreferenceActivity.java
        new file:   app/src/main/java/com/nsa/welshpharmacy/KeyValueHelper.java
        modified:   app/src/main/java/com/nsa/welshpharmacy/MainMenu.java
        new file:   app/src/main/res/drawable/ic_check.xml
        new file:   app/src/main/res/layout/activity_filter_preference.xml
        new file:   app/src/main/res/values/dimens.xml
        new file:   app/src/main/res/values/ids.xml

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   app/src/main/AndroidManifest.xml
        both modified:   app/src/main/res/values/strings.xml


c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development|MERGING)
$ git status
On branch development
Your branch is up-to-date with 'origin/development'.
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:

        modified:   .gitignore
        new file:   app/src/main/java/com/nsa/welshpharmacy/FilterPreferenceActivity.java
        new file:   app/src/main/java/com/nsa/welshpharmacy/KeyValueHelper.java
        modified:   app/src/main/java/com/nsa/welshpharmacy/MainMenu.java
        new file:   app/src/main/res/drawable/ic_check.xml
        new file:   app/src/main/res/layout/activity_filter_preference.xml
        new file:   app/src/main/res/values/dimens.xml
        new file:   app/src/main/res/values/ids.xml

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   app/src/main/AndroidManifest.xml


c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development|MERGING)
$ git status
On branch development
Your branch is up-to-date with 'origin/development'.
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:

        modified:   .gitignore
        new file:   app/src/main/java/com/nsa/welshpharmacy/FilterPreferenceActivity.java
        new file:   app/src/main/java/com/nsa/welshpharmacy/KeyValueHelper.java
        modified:   app/src/main/java/com/nsa/welshpharmacy/MainMenu.java
        new file:   app/src/main/res/drawable/ic_check.xml
        new file:   app/src/main/res/layout/activity_filter_preference.xml
        new file:   app/src/main/res/values/dimens.xml
        new file:   app/src/main/res/values/ids.xml

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   app/src/main/AndroidManifest.xml


c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development|MERGING)
$ git add app/src/main/AndroidManifest.xml

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development|MERGING)
$ git status
On branch development
Your branch is up-to-date with 'origin/development'.
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:

        modified:   .gitignore
        modified:   app/src/main/AndroidManifest.xml
        new file:   app/src/main/java/com/nsa/welshpharmacy/FilterPreferenceActivity.java
        new file:   app/src/main/java/com/nsa/welshpharmacy/KeyValueHelper.java
        modified:   app/src/main/java/com/nsa/welshpharmacy/MainMenu.java
        new file:   app/src/main/res/drawable/ic_check.xml
        new file:   app/src/main/res/layout/activity_filter_preference.xml
        new file:   app/src/main/res/values/dimens.xml
        new file:   app/src/main/res/values/ids.xml


c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (development|MERGING)
$
