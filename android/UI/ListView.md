
[Slides](https://gitlab.cs.cf.ac.uk/CM6122/lectures/app_ui_iii/blob/master/app_ui_iii_lists.pdf)

**What is a list view?**

- ListViews are built in

- They are a type of "container" view that displays a scrollable list of items

- Items can have a custom layout themselves or use a built-in template

- However, in keeping with the concept of separation in Android dev, the ListView does not connect directly to your data. This requires an "Adapter"
which acts as the middle party

**What are the fundamental components?**

**What is a RecyclerView?**

- An efficient and flexible, but more abstract alternative that can be used to achieve the functionality of a ListView

- In most cases, you should use a RecyclerView instead of a ListView

- Need to create a custom adapter (class) that extends Recycler view.Adaper and implement this functionality
