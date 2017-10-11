11/10/17
```
c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development
$ git init
Initialized empty Git repository in C:/Users/c1712480/Documents/Semester_1/Intro to web development/.git/

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        CSS/
        HTML/
        Project work/

nothing added to commit but untracked files present (use "git add" to track)

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git add
Nothing specified, nothing added.
Maybe you wanted to say 'git add .'?

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git add CSS/
warning: LF will be replaced by CRLF in CSS/BigCSS_Eg/Home.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/BigCSS_Eg/css/company.css.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_BlankKatas/kata1Semantics.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_BlankKatas/kata2Selection.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_BlankKatas/kata3Dropdown.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_BlankKatas/kata4Pseudo.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_BlankKatas/pageForWireframe.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_KataAnswers/kata1Semantics.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_KataAnswers/kata2Selection.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_KataAnswers/kata3Dropdown.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/_KataAnswers/kata4Pseudo.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/code/1NthOfType.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/code/2Hover.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/code/3position.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/code/4Blocks.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/CSSLayoutLC/code/5hover.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/Stuff/1_inline.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/Stuff/2_InDoc.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/Stuff/3_Selectors.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/Stuff/4_inDocDivs.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in CSS/Stuff/5_inDocDivsExternal.html.
The file will have its original line endings in your working directory.

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git add HTML/
warning: LF will be replaced by CRLF in HTML/Semantic Tagging.html.
The file will have its original line endings in your working directory.

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git add Project work/
fatal: pathspec 'Project' did not match any files

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git add "Project work"
c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git add "Project work"/

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   CSS/BigCSS_Eg/Games.html
        new file:   CSS/BigCSS_Eg/Home.html
        new file:   CSS/BigCSS_Eg/HomeNoCSS.html
        new file:   CSS/BigCSS_Eg/Profile.html
        new file:   CSS/BigCSS_Eg/css/company.css
        new file:   CSS/BigCSS_Eg/css/dept.css
        new file:   CSS/BigCSS_Eg/css/my.css
        new file:   CSS/BigCSS_Eg/css/paddleBanner.JPG
        new file:   CSS/CSSLayoutLC/CSSLayout.pdf
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata1Semantics.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata2Selection.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata3Dropdown.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata4Pseudo.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/pageForWireframe.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/screenShot.JPG
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata1Semantics.html
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata2Selection.html
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata3Dropdown.html
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata4Pseudo.html
        new file:   CSS/CSSLayoutLC/code/10Media.html
        new file:   CSS/CSSLayoutLC/code/1NthOfType.html
        new file:   CSS/CSSLayoutLC/code/2Hover.html
        new file:   CSS/CSSLayoutLC/code/3position.html
        new file:   CSS/CSSLayoutLC/code/4Blocks.html
        new file:   CSS/CSSLayoutLC/code/5hover.html
        new file:   CSS/CSSLayoutLC/code/7BoxModel.html
        new file:   CSS/CSSLayoutLC/code/8BorderBox.html
        new file:   CSS/CSSLayoutLC/code/9Flex.html
        new file:   CSS/Stuff/1_inline.html
        new file:   CSS/Stuff/2_InDoc.html
        new file:   CSS/Stuff/3_Selectors.html
        new file:   CSS/Stuff/4_inDocDivs.html
        new file:   CSS/Stuff/5_inDocDivsExternal.html
        new file:   CSS/Stuff/5_my.css
        new file:   CSS/Stuff/Exercise1.html
        new file:   CSS/Stuff/Profile_inline.html
        new file:   HTML/Favourite animals table.html
        new file:   HTML/Git hub random
        new file:   HTML/Me.jpg
        new file:   HTML/Qualifications list.html
        new file:   HTML/Semantic Tagging.html
        new file:   HTML/SemanticTaggingEx.html
        new file:   HTML/Shiro_NGNL.jpg
        new file:   HTML/User profile
        new file:   HTML/User profile.html
        new file:   HTML/animated_image.gif
        new file:   HTML/code/S1_1_basics.html
        new file:   HTML/code/S1_2_Semantics.html
        new file:   HTML/code/S1_3_listTable.html
        new file:   HTML/code/S1_4_Attributes.html
        new file:   HTML/code/S1_5_links.html
        new file:   HTML/code/S1_6_Forms.html
        new file:   HTML/code/ian.jpg
        new file:   HTML/image1.jpg
        new file:   HTML/profile_inDoc.html
        new file:   HTML/webdev session1.pdf
        new file:   HTML/website links.html
        new file:   Project work/Individual project/Elements.mp4
        new file:   Project work/Individual project/I_like_what_you_got.wav
        new file:   Project work/Individual project/Me.jpg
        new file:   Project work/Individual project/Profile_styling.css
        new file:   Project work/Individual project/Shiro_NGNL.jpg
        new file:   Project work/Individual project/animated_image.gif
        new file:   Project work/Individual project/contact.html
        new file:   Project work/Individual project/game.js
        new file:   Project work/Individual project/home.html
        new file:   Project work/Individual project/profile.html
        new file:   Project work/Individual project/profile_inDoc.html
        new file:   Project work/Individual project/video.html


c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git commit
Vim: Error reading input, exiting...
Vim: preserving files...
Vim: Finished.

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   CSS/BigCSS_Eg/Games.html
        new file:   CSS/BigCSS_Eg/Home.html
        new file:   CSS/BigCSS_Eg/HomeNoCSS.html
        new file:   CSS/BigCSS_Eg/Profile.html
        new file:   CSS/BigCSS_Eg/css/company.css
        new file:   CSS/BigCSS_Eg/css/dept.css
        new file:   CSS/BigCSS_Eg/css/my.css
        new file:   CSS/BigCSS_Eg/css/paddleBanner.JPG
        new file:   CSS/CSSLayoutLC/CSSLayout.pdf
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata1Semantics.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata2Selection.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata3Dropdown.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/kata4Pseudo.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/pageForWireframe.html
        new file:   CSS/CSSLayoutLC/_BlankKatas/screenShot.JPG
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata1Semantics.html
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata2Selection.html
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata3Dropdown.html
        new file:   CSS/CSSLayoutLC/_KataAnswers/kata4Pseudo.html
        new file:   CSS/CSSLayoutLC/code/10Media.html
        new file:   CSS/CSSLayoutLC/code/1NthOfType.html
        new file:   CSS/CSSLayoutLC/code/2Hover.html
        new file:   CSS/CSSLayoutLC/code/3position.html
        new file:   CSS/CSSLayoutLC/code/4Blocks.html
        new file:   CSS/CSSLayoutLC/code/5hover.html
        new file:   CSS/CSSLayoutLC/code/7BoxModel.html
        new file:   CSS/CSSLayoutLC/code/8BorderBox.html
        new file:   CSS/CSSLayoutLC/code/9Flex.html
        new file:   CSS/Stuff/1_inline.html
        new file:   CSS/Stuff/2_InDoc.html
        new file:   CSS/Stuff/3_Selectors.html
        new file:   CSS/Stuff/4_inDocDivs.html
        new file:   CSS/Stuff/5_inDocDivsExternal.html
        new file:   CSS/Stuff/5_my.css
        new file:   CSS/Stuff/Exercise1.html
        new file:   CSS/Stuff/Profile_inline.html
        new file:   HTML/Favourite animals table.html
        new file:   HTML/Git hub random
        new file:   HTML/Me.jpg
        new file:   HTML/Qualifications list.html
        new file:   HTML/Semantic Tagging.html
        new file:   HTML/SemanticTaggingEx.html
        new file:   HTML/Shiro_NGNL.jpg
        new file:   HTML/User profile
        new file:   HTML/User profile.html
        new file:   HTML/animated_image.gif
        new file:   HTML/code/S1_1_basics.html
        new file:   HTML/code/S1_2_Semantics.html
        new file:   HTML/code/S1_3_listTable.html
        new file:   HTML/code/S1_4_Attributes.html
        new file:   HTML/code/S1_5_links.html
        new file:   HTML/code/S1_6_Forms.html
        new file:   HTML/code/ian.jpg
        new file:   HTML/image1.jpg
        new file:   HTML/profile_inDoc.html
        new file:   HTML/webdev session1.pdf
        new file:   HTML/website links.html
        new file:   Project work/Individual project/Elements.mp4
        new file:   Project work/Individual project/I_like_what_you_got.wav
        new file:   Project work/Individual project/Me.jpg
        new file:   Project work/Individual project/Profile_styling.css
        new file:   Project work/Individual project/Shiro_NGNL.jpg
        new file:   Project work/Individual project/animated_image.gif
        new file:   Project work/Individual project/contact.html
        new file:   Project work/Individual project/game.js
        new file:   Project work/Individual project/home.html
        new file:   Project work/Individual project/profile.html
        new file:   Project work/Individual project/profile_inDoc.html
        new file:   Project work/Individual project/video.html


c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git commit -m "Initial commit"
[master (root-commit) 077b31a] Initial commit
 69 files changed, 3150 insertions(+)
 create mode 100644 CSS/BigCSS_Eg/Games.html
 create mode 100644 CSS/BigCSS_Eg/Home.html
 create mode 100644 CSS/BigCSS_Eg/HomeNoCSS.html
 create mode 100644 CSS/BigCSS_Eg/Profile.html
 create mode 100644 CSS/BigCSS_Eg/css/company.css
 create mode 100644 CSS/BigCSS_Eg/css/dept.css
 create mode 100644 CSS/BigCSS_Eg/css/my.css
 create mode 100644 CSS/BigCSS_Eg/css/paddleBanner.JPG
 create mode 100644 CSS/CSSLayoutLC/CSSLayout.pdf
 create mode 100644 CSS/CSSLayoutLC/_BlankKatas/kata1Semantics.html
 create mode 100644 CSS/CSSLayoutLC/_BlankKatas/kata2Selection.html
 create mode 100644 CSS/CSSLayoutLC/_BlankKatas/kata3Dropdown.html
 create mode 100644 CSS/CSSLayoutLC/_BlankKatas/kata4Pseudo.html
 create mode 100644 CSS/CSSLayoutLC/_BlankKatas/pageForWireframe.html
 create mode 100644 CSS/CSSLayoutLC/_BlankKatas/screenShot.JPG
 create mode 100644 CSS/CSSLayoutLC/_KataAnswers/kata1Semantics.html
 create mode 100644 CSS/CSSLayoutLC/_KataAnswers/kata2Selection.html
 create mode 100644 CSS/CSSLayoutLC/_KataAnswers/kata3Dropdown.html
 create mode 100644 CSS/CSSLayoutLC/_KataAnswers/kata4Pseudo.html
 create mode 100644 CSS/CSSLayoutLC/code/10Media.html
 create mode 100644 CSS/CSSLayoutLC/code/1NthOfType.html
 create mode 100644 CSS/CSSLayoutLC/code/2Hover.html
 create mode 100644 CSS/CSSLayoutLC/code/3position.html
 create mode 100644 CSS/CSSLayoutLC/code/4Blocks.html
 create mode 100644 CSS/CSSLayoutLC/code/5hover.html
 create mode 100644 CSS/CSSLayoutLC/code/7BoxModel.html
 create mode 100644 CSS/CSSLayoutLC/code/8BorderBox.html
 create mode 100644 CSS/CSSLayoutLC/code/9Flex.html
 create mode 100644 CSS/Stuff/1_inline.html
 create mode 100644 CSS/Stuff/2_InDoc.html
 create mode 100644 CSS/Stuff/3_Selectors.html
 create mode 100644 CSS/Stuff/4_inDocDivs.html
 create mode 100644 CSS/Stuff/5_inDocDivsExternal.html
 create mode 100644 CSS/Stuff/5_my.css
 create mode 100644 CSS/Stuff/Exercise1.html
 create mode 100644 CSS/Stuff/Profile_inline.html
 create mode 100644 HTML/Favourite animals table.html
 create mode 100644 HTML/Git hub random
 create mode 100644 HTML/Me.jpg
 create mode 100644 HTML/Qualifications list.html
 create mode 100644 HTML/Semantic Tagging.html
 create mode 100644 HTML/SemanticTaggingEx.html
 create mode 100644 HTML/Shiro_NGNL.jpg
 create mode 100644 HTML/User profile
 create mode 100644 HTML/User profile.html
 create mode 100644 HTML/animated_image.gif
 create mode 100644 HTML/code/S1_1_basics.html
 create mode 100644 HTML/code/S1_2_Semantics.html
 create mode 100644 HTML/code/S1_3_listTable.html
 create mode 100644 HTML/code/S1_4_Attributes.html
 create mode 100644 HTML/code/S1_5_links.html
 create mode 100644 HTML/code/S1_6_Forms.html
 create mode 100644 HTML/code/ian.jpg
 create mode 100644 HTML/image1.jpg
 create mode 100644 HTML/profile_inDoc.html
 create mode 100644 HTML/webdev session1.pdf
 create mode 100644 HTML/website links.html
 create mode 100644 Project work/Individual project/Elements.mp4
 create mode 100644 Project work/Individual project/I_like_what_you_got.wav
 create mode 100644 Project work/Individual project/Me.jpg
 create mode 100644 Project work/Individual project/Profile_styling.css
 create mode 100644 Project work/Individual project/Shiro_NGNL.jpg
 create mode 100644 Project work/Individual project/animated_image.gif
 create mode 100644 Project work/Individual project/contact.html
 create mode 100644 Project work/Individual project/game.js
 create mode 100644 Project work/Individual project/home.html
 create mode 100644 Project work/Individual project/profile.html
 create mode 100644 Project work/Individual project/profile_inDoc.html
 create mode 100644 Project work/Individual project/video.html

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git status
On branch master
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git log
commit 077b31a5f81e16962b9f95afe112ec9af0e3387e
Author: Holly Smith <SmithHL2@cardiff.ac.uk>
Date:   Wed Oct 11 20:44:07 2017 +0100

    Initial commit

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ ^V
bash: $'\026': command not found

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git remote add origin git@gitlab.cs.cf.ac.uk:c1712480/my_first_project.git

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git push -u origin --all
Enter passphrase for key '/c/Users/c1712480/.ssh/id_rsa':
Counting objects: 80, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (77/77), done.
Writing objects: 100% (80/80), 127.84 MiB | 2.19 MiB/s, done.
Total 80 (delta 12), reused 0 (delta 0)
To gitlab.cs.cf.ac.uk:c1712480/my_first_project.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$ git log
commit 077b31a5f81e16962b9f95afe112ec9af0e3387e
Author: Holly Smith <SmithHL2@cardiff.ac.uk>
Date:   Wed Oct 11 20:44:07 2017 +0100

    Initial commit

c1712480@NSA107D1A0AE75B MINGW64 ~/Documents/Semester_1/Intro to web development (master)
$
```
