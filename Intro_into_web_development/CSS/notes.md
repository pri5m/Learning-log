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
      h1{
        color: green;
      }
      h2{
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
