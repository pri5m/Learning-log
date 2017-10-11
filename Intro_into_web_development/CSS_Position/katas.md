# 1- Semantics

```
<!DOCTYPE html>
<html>
  <head>
    <title> Kata 1</title>
  </head>

  <body>
    <title>
      Introduction to Web development
    </title>
    <!-- The corporate links block -->
    <nav class ="corporateLinks">
      <p>
        Introduction to Web Development: <a href="http://www.cs.ac.uk">COMSC</a> <a href="http://www.cs.cf.ac.uk/software-academy">National Software Academy</a>
      </p>
    </nav>

    <!-- The page title block -->
    <section class ="title">
     <h1> Kata 1 </h1>
   </section>

    <!-- The site links block -->
    <nav class = "links">
      <h3>Site Links</h3>
      <a href="kata1Semantics.html">Home</a>
      <a href="kata1Semantics.html">Kata 1</a>
      <a href="kata2Selection.html">Kata 2</a>
      <a href="kata3Dropdown.html">Kata 3</a>
      <a href="kata4Pseudo.html">Kata 4</a>
    </nav>

    <!-- Main content of page -->
    <section class="content">
      <article class="mainItem">
        Look at the HTML file for this page and think about the purpose of each of the code blocks. <br>
        All structuring is currently achieved with &ltdiv&gt tags. <br>
        Go through the code and semantically tag the document.
      </article>

      <article class="comments">
        <h3>Comments</h3>

        <p>Remember the learning resources that you looked at: html5 doctor lets talk about semantics, MDN elements reference etc.</p>
        <p> Comment by Ian <date>20/10/2012</date></p>

        <p> Semantic tags are ment to indicate the purpose of the code block, don't get too obsessed with the semantic element's name </p>
        <p> Comment by Ian <date>20/10/2012</date></p>
      </article>
    </section>

    <!-- Other stuff that needs to be on page -->
    <section class="ads">
      adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts
    </section>

    <!-- Info at the end of page -->
    <footer class="bottom">
      <p> The GamesCompany..... a <a href="parentCompany.htm">parent</a> subsiduary. </p>
      <p>The GamesHouse.website... <br> Corporate address: 20 ARoad, AStreet, ATown. CF0 3TF</p>
    </footer>

  </body>

</html>
```

**Answer**
```
<!DOCTYPE html>
<html>
  <head>
    <title> Kata 1</title>
  </head>

  <body>
    <header>
      <div>
        Introduction to Web development
      </div>
    <!-- The corporate links block -->
      <nav class ="corporateLinks">
        <p>
          <a href="http://www.cs.ac.uk">COMSC</a> <a href="http://www.cs.cf.ac.uk/software-academy">National Software Academy</a>
        </p>
      </nav>
    </header>

    <!-- The page title block -->
    <div class ="title">
     <h1> Kata 1 </h1>
    </div>

    <!-- The site links block -->
    <nav class = "links">
      <h3>Site Links</h3>
      <a href="kata1Semantics.html">Home</a>
      <a href="kata1Semantics.html">Kata 1</a>
      <a href="kata2Selection.html">Kata 2</a>
      <a href="kata3Dropdown.html">Kata 3</a>
      <a href="kata4Pseudo.html">Kata 4</a>
    </nav>

    <!-- Main content of page -->
    <main class="content">
      <div class="mainItem">
        Look at the HTML file for this page and think about the purpose of each of the code blocks. <br>
        All structuring is currently achieved with &ltdiv&gt tags. <br>
        Go through the code and semantically tag the document.
      </div>

      <div class="comments">
        <h3>Comments</h3>
        <article>
          <p>Remember the learning resources that you looked at: html5 doctor lets talk about semantics, MDN elements reference etc.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>
        </article>
        <article>
          <p> Semantic tags are ment to indicate the purpose of the code block, don't get too obsessed with the semantic element's name </p>
          <p> Comment by Ian <date>20/10/2012</date></p>
        </article>
      </div>
    </main>

    <!-- Other stuff that needs to be on page -->
    <aside class="ads">
      adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts
    </aside>

    <!-- Info at the end of page -->
    <footer class="bottom">
      <p> The GamesCompany..... a <a href="parentCompany.htm">parent</a> subsiduary. </p>
      <p>The GamesHouse.website... <br> Corporate address: 20 ARoad, AStreet, ATown. CF0 3TF</p>
    </footer>

  </body>

</html>
```

# 2- Selection

```

```
**Answer**

```

```

# 3- Dropdown


# 4- Pseudo


# Page for Wireframe
