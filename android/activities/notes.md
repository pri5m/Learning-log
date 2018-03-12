[Slides 1](https://gitlab.cs.cf.ac.uk/CM6122/lectures/activities_i/blob/master/activities_i_what_and_how.pdf)

# Activities

*Generally speaking*

- Each screen in an app involves and activity

- Therefore, each app has at least one activity

- They serve as an entry point into applications and are central to navigation within and between apps

*How they fit into the overall picture*

- Most apps contain multiple screens, which means they comprise multiple activities.

- Typically, one activity in an app is specified as the main activity, which is the first screen to appear when the user launches the app. Each activity can then start another activity in order to perform different actions.

- Although activities work together to form a cohesive user experience in an app, each activity is only loosely bound to the other activities; there are usually minimal dependencies among the activities in an app. In fact, activities often start up activities belonging to other apps. For example, a browser app might launch the Share activity of a social-media app.

# Managing the activity lifecycle

Over the course of its lifetime, an activity goes through a number of states. You use a series of callbacks to handle transitions between states. The following sections introduce these callbacks.

**onCreate()**
You must implement this callback, which fires when the system creates your activity. Your implementation should initialize the essential components of your activity: For example, your app should create views and bind data to lists here. Most importantly, this is where you must call setContentView() to define the layout for the activity's user interface.

When onCreate() finishes, the next callback is always onStart().

**onStart()**
As onCreate() exits, the activity enters the Started state, and the activity becomes visible to the user. This callback contains what amounts to the activity’s final preparations for coming to the foreground and becoming interactive.

**onResume()**
The system invokes this callback just before the activity starts interacting with the user. At this point, the activity is at the top of the activity stack, and captures all user input. Most of an app’s core functionality is implemented in the onResume() method.

The onPause() callback always follows onResume().

**onPause()**
The system calls onPause() when the activity loses focus and enters a Paused state. This state occurs when, for example, the user taps the Back or Recents button. When the system calls onPause() for your activity, it technically means your activity is still partially visible, but most often is an indication that the user is leaving the activity, and the activity will soon enter the Stopped or Resumed state.

An activity in the Paused state may continue to update the UI if the user is expecting the UI to update. Examples of such an activity include one showing a navigation map screen or a media player playing. Even if such activities lose focus, the user expects their UI to continue updating.

You should not use onPause() to save application or user data, make network calls, or execute database transactions. For information about saving data, see Saving and restoring activity state.

Once onPause() finishes executing, the next callback is either onStop() or onResume(), depending on what happens after the activity enters the Paused state.

**onStop()**
The system calls onStop() when the activity is no longer visible to the user. This may happen because the activity is being destroyed, a new activity is starting, or an existing activity is entering a Resumed state and is covering the stopped activity. In all of these cases, the stopped activity is no longer visible at all.

The next callback that the system calls is either onRestart(), if the activity is coming back to interact with the user, or by onDestroy() if this activity is completely terminating.

**onRestart()**
The system invokes this callback when an activity in the Stopped state is about to restart. onRestart() restores the state of the activity from the time that it was stopped.

This callback is always followed by onStart().

**onDestroy()**
The system invokes this callback before an activity is destroyed.

This callback is the final one that the activity receives. onDestroy() is usually implemented to ensure that all of an activity’s resources are released when the activity, or the process containing it, is destroyed.

This section provides only an introduction to this topic. For a more detailed treatment of the activity lifecycle and its callbacks, see The Activity Lifecycle.

## An activity has essentially four states:

- If an activity is in the foreground of the screen (at the top of the stack), it is active or running.

- If an activity has lost focus but is still visible (that is, a new non-full-sized or transparent activity has focus on top of your activity), it is paused. A paused activity is completely alive (it maintains all state and member information and remains attached to the window manager), but can be killed by the system in extreme low memory situations.

- If an activity is completely obscured by another activity, it is stopped. It still retains all state and member information, however, it is no longer visible to the user so its window is hidden and it will often be killed by the system when memory is needed elsewhere.

- If an activity is paused or stopped, the system can drop the activity from memory by either asking it to finish, or simply killing its process. When it is displayed again to the user, it must be completely restarted and restored to its previous state.

## There are three key loops you may be interested in monitoring within your activity:

- The entire lifetime of an activity happens between the first call to onCreate(Bundle) through to a single final call to onDestroy(). An activity will do all setup of "global" state in onCreate(), and release all remaining resources in onDestroy(). For example, if it has a thread running in the background to download data from the network, it may create that thread in onCreate() and then stop the thread in onDestroy().

- The visible lifetime of an activity happens between a call to onStart() until a corresponding call to onStop(). During this time the user can see the activity on-screen, though it may not be in the foreground and interacting with the user. Between these two methods you can maintain resources that are needed to show the activity to the user. For example, you can register a BroadcastReceiver in onStart() to monitor for changes that impact your UI, and unregister it in onStop() when the user no longer sees what you are displaying. The onStart() and onStop() methods can be called multiple times, as the activity becomes visible and hidden to the user.

- The foreground lifetime of an activity happens between a call to onResume() until a corresponding call to onPause(). During this time the activity is in front of all other activities and interacting with the user. An activity can frequently go between the resumed and paused states -- for example when the device goes to sleep, when an activity result is delivered, when a new intent is delivered -- so the code in these methods should be fairly lightweight.

[Activity reference](https://developer.android.com/reference/android/app/Activity.html)

[AppCompatActivity](https://developer.android.com/reference/android/support/v7/app/AppCompatActivity.html)   Base class for activities that use the support library action bar features.

## Creating activities

Android studio does the basics but all necessary parts need to be done manually

**Automated tasks**

1. Creating the activity class file (*.java)

2. Creating the layout resource associated with the activity (*.xml)

3. Declairing the existance of the activity in the Application manifest

## YourActivity.java

```
...//package name, imports ect.
public class MainActivity extends AppCompatActivity

  @Override
  protected void onCreate(Bundle savedInstanceState)
    super.onCreate(savedInstanceState)
    ...
  }
}
```

- There is no 'main' method, insted we use the onCreate method

- Inside Android's activity class (ie. the superclass) there ia an onCreate method (among many others) which we do not edit directly. We are "overriding" this so that our onCreate method is ran instead. Our activity will use all other methods in the superclass (not shown) that we do not override

## UI
```
...//package name, imports ect.
public class MainActivity extends AppCompatActivity

  @Override
  protected void onCreate(Bundle savedInstanceState)
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main);
    ...
  }
}
```

- UI created as resource layouts files can be attatchedd to an activity through a process called inflation

## Declaring in the app manifest

- Creating a .java file just creates an activity that is part of your source code

- In order to use it, you must define that it exists by adding it to your application manifest

- *Remember*, the application manifest is an XML file with a hierarchal structure

- Example, to decaler an activity called MainActivity (in "MainActivity.java")

```
<application...>
...
  <activity
  android:name=".MainActivity">
  </activity>
...
</application> ...
```

## How can activities be launched?

As stated each app should have a designated "main" activity that is launched when its icon is tapped (ie.on the home screen or launcher)

To do this, enter the following inside the activity's tag in the application manifest

```
<activity android:name=".MainActivity">
  <intent-filter>
    <action android:name-"android.intent.action.MAIN" />
    
    <category android:name="android.intent.category.LAUNCHER" />
  </intent-filter>
</activity>
```
[Sending the user to another app](https://developer.android.com/training/basics/intents/sending.html)
# Slides 2

[Slides 2](https://gitlab.cs.cf.ac.uk/CM6122/lectures/activities_ii/blob/master/activities_ii_intents_and_filters.pdf)

## Intents

- An intent is a message object that instructs Android to perform a specified action

- In this case they are used to start an activity, however the concept is also used for other app components such as Services

- The intent may also carry additional information about what kind of app shsoulld recieve (it does not refer to an explicit app), as well as data that the new Activity can retrieve and then so something with

[Intent and intent fillers](https://developer.android.com/guide/components/intents-filters.html)

[Intent reference](https://developer.android.com/reference/android/content/Intent.html)

**Two broad tupes of intent**

Explicit intent (typically intra-app)

- You can instruct Android to either open a specific activity

```
//Assumes that this is being called within an activity
Intent i = new Intent(this, ReceptiveActivity.class);
startActivity(i);
```

Implicit intent (typically inter-app)

- Or find an appropriate activity (which should be another application) to handle it

```
//Intent.ACTION_DIAL is an Intent API constant
Intent i = new Intent(Iintent.ACTION_DIAL);
i.setData(Uri.parse("tel:123123123"));
startActivity(i);
```

**How does an Activity declare that they can handle an Intent?**

Intent filters

- An intent filter is a rule that is addedd as part of an activity's declaration in the App manifest.  Android will only match the activity to an intent if the parameters of the intent match the filter.

- *important note*, for an activity to show as an option for an implicit intent, the intent filter must include a category tag containing a name attribute with the value android.intent.category.DEFAULT

```
<intent-filter>
  <action android:name="android.intent.action.DIAL"/>
  <category android:name"android.intent.category.DEFAULT"/>
  <data android:scheme="tel"/>
</intent-filter>
```
