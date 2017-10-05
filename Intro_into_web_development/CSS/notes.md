# CSS notes

```
style = "border: 3px dotted"
```

**example 1**
```
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Exercise1 </title>
    <style>
      /* To Do: add the style in here.*/
      h1, h2{
        color: green;
      }
      .main_links {
        color: red;
        background: black;
      }
      #adverts1{
        color: blue;
        background: green;
        border-radius: 5px;
      }
    </style>
  </head>

  <body>

    <h1>Make me Green (hint - American spelling)</h1>

    <nav class = "main_links">
      <p>Links Links Links Links ---- Make me Red with a Black background (I am in an element with a class main_links). </p>
    </nav>

    <h2>Make me Green too</h2>

    <aside id = "adverts1">
      <p>Ads Ads Ads --- Make me Blue with a Green background with rounded corners.</p>
    </aside>

  </body>
</html>
```

**Classes or IDs**
They work in a v similar way. Which should you use, where and why?

IDs should be used for one off items
Class should be used for a bunch of elementes. If it is going to be reused.
It doesn't actually make much difference, it is just best practice. It is assumed that IDs are used for one off items and will be treated by others as such.

**Selectors**

- x,y{...}     AND        Applies to x and y

- xy{...}      WITHIN     Applies to y within x

- x > y{...}         DIRECT DECENDANTS
