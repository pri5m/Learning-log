
c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (maste                             r)
$ git init
Initialized empty Git repository in C:/Users/c1712480/AndroidStudioProjects/CP/WelshPharmacy/.git/

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git add .
warning: LF will be replaced by CRLF in .idea/gradle.xml.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in .idea/misc.xml.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in .idea/modules.xml.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in .idea/runConfigurations.xml.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in gradlew.
The file will have its original line endings in your working directory.

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   .gitignore
        new file:   .idea/gradle.xml
        new file:   .idea/misc.xml
        new file:   .idea/modules.xml
        new file:   .idea/runConfigurations.xml
        new file:   app/.gitignore
        new file:   app/build.gradle
        new file:   app/proguard-rules.pro
        new file:   app/src/androidTest/java/com/nsa/welshpharmacy/ExampleInstrumentedTest.java
        new file:   app/src/main/AndroidManifest.xml
        new file:   app/src/main/java/com/nsa/welshpharmacy/MainMenu.java
        new file:   app/src/main/res/drawable-v24/ic_launcher_foreground.xml
        new file:   app/src/main/res/drawable/ic_launcher_background.xml
        new file:   app/src/main/res/layout/activity_main_menu.xml
        new file:   app/src/main/res/mipmap-anydpi-v26/ic_launcher.xml
        new file:   app/src/main/res/mipmap-anydpi-v26/ic_launcher_round.xml
        new file:   app/src/main/res/mipmap-hdpi/ic_launcher.png
        new file:   app/src/main/res/mipmap-hdpi/ic_launcher_round.png
        new file:   app/src/main/res/mipmap-mdpi/ic_launcher.png
        new file:   app/src/main/res/mipmap-mdpi/ic_launcher_round.png
        new file:   app/src/main/res/mipmap-xhdpi/ic_launcher.png
        new file:   app/src/main/res/mipmap-xhdpi/ic_launcher_round.png
        new file:   app/src/main/res/mipmap-xxhdpi/ic_launcher.png
        new file:   app/src/main/res/mipmap-xxhdpi/ic_launcher_round.png
        new file:   app/src/main/res/mipmap-xxxhdpi/ic_launcher.png
        new file:   app/src/main/res/mipmap-xxxhdpi/ic_launcher_round.png
        new file:   app/src/main/res/values/colors.xml
        new file:   app/src/main/res/values/strings.xml
        new file:   app/src/main/res/values/styles.xml
        new file:   app/src/test/java/com/nsa/welshpharmacy/ExampleUnitTest.java
        new file:   build.gradle
        new file:   gradle.properties
        new file:   gradle/wrapper/gradle-wrapper.jar
        new file:   gradle/wrapper/gradle-wrapper.properties
        new file:   gradlew
        new file:   gradlew.bat
        new file:   settings.gradle


c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git commit -m 'Initial commit'
[master (root-commit) a640b35] Initial commit
 37 files changed, 761 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 .idea/gradle.xml
 create mode 100644 .idea/misc.xml
 create mode 100644 .idea/modules.xml
 create mode 100644 .idea/runConfigurations.xml
 create mode 100644 app/.gitignore
 create mode 100644 app/build.gradle
 create mode 100644 app/proguard-rules.pro
 create mode 100644 app/src/androidTest/java/com/nsa/welshpharmacy/ExampleInstrumentedTest.java
 create mode 100644 app/src/main/AndroidManifest.xml
 create mode 100644 app/src/main/java/com/nsa/welshpharmacy/MainMenu.java
 create mode 100644 app/src/main/res/drawable-v24/ic_launcher_foreground.xml
 create mode 100644 app/src/main/res/drawable/ic_launcher_background.xml
 create mode 100644 app/src/main/res/layout/activity_main_menu.xml
 create mode 100644 app/src/main/res/mipmap-anydpi-v26/ic_launcher.xml
 create mode 100644 app/src/main/res/mipmap-anydpi-v26/ic_launcher_round.xml
 create mode 100644 app/src/main/res/mipmap-hdpi/ic_launcher.png
 create mode 100644 app/src/main/res/mipmap-hdpi/ic_launcher_round.png
 create mode 100644 app/src/main/res/mipmap-mdpi/ic_launcher.png
 create mode 100644 app/src/main/res/mipmap-mdpi/ic_launcher_round.png
 create mode 100644 app/src/main/res/mipmap-xhdpi/ic_launcher.png
 create mode 100644 app/src/main/res/mipmap-xhdpi/ic_launcher_round.png
 create mode 100644 app/src/main/res/mipmap-xxhdpi/ic_launcher.png
 create mode 100644 app/src/main/res/mipmap-xxhdpi/ic_launcher_round.png
 create mode 100644 app/src/main/res/mipmap-xxxhdpi/ic_launcher.png
 create mode 100644 app/src/main/res/mipmap-xxxhdpi/ic_launcher_round.png
 create mode 100644 app/src/main/res/values/colors.xml
 create mode 100644 app/src/main/res/values/strings.xml
 create mode 100644 app/src/main/res/values/styles.xml
 create mode 100644 app/src/test/java/com/nsa/welshpharmacy/ExampleUnitTest.java
 create mode 100644 build.gradle
 create mode 100644 gradle.properties
 create mode 100644 gradle/wrapper/gradle-wrapper.jar
 create mode 100644 gradle/wrapper/gradle-wrapper.properties
 create mode 100644 gradlew
 create mode 100644 gradlew.bat
 create mode 100644 settings.gradle

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git status
On branch master
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git remote add origin git@gitlab.cs.cf.ac.uk:c1714546/Welsh-Pharmacy-Team4.git

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git push -u origin master
NSEnter passphrase for key '/c/Users/c1712480/.ssh/id_rsa':
Counting objects: 69, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (53/53), done.
Writing objects: 100% (69/69), 123.44 KiB | 0 bytes/s, done.
Total 69 (delta 0), reused 0 (delta 0)
To gitlab.cs.cf.ac.uk:c1714546/Welsh-Pharmacy-Team4.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

c1712480@NSA107D1A0AE75B MINGW64 ~/AndroidStudioProjects/CP/WelshPharmacy (master)
$
