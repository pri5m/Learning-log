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
<!DOCTYPE html>
<html>
  <head>
    <title> Kata 2</title>
    <style>

      .links ul{
        text-align:center;
      }

      .links ul li{
        display:inline-block;
        padding: 20px;
      }

      #first{
        padding-right: : 60px;
      }
    </style>

  </head>

  <body>

    <!-- The corporate links block -->
    <nav class ="corporateLinks">
      <p>
        Introduction to Web Development: <a href="http://www.cs.cf.ac.uk">COMSC</a> <a href="http://www.cs.cf.ac.uk/software-academy">National Software Academy</a>
      </p>
    </nav>

    <!-- The page title block -->
    <headder class ="title">
     <h1> Kata 2 </h1>
    </headder>

    <!-- The site links block -->
    <nav class = "links" id = "move">
      <h3>Site Links</h3>
      <ul>
        <li><a href="kata1Semantics.html" id = "first">Home</a></li>
        <li><a href="kata1Semantics.html">Kata 1</a></li>
        <li><a href="kata2Selection.html">Kata 2</a></li>
        <li><a href="kata3Dropdown.html">Kata 3</a></li>
        <li><a href="kata4Pseudo.html">Kata 4</a></li>
      </ul>
    </nav>

    <!-- Main content of page -->
    <article class="content">
      <section class="mainItem">
        Look at the HTML file for this page and think about the Site Links block. <br>
        Create a horizontal links bar. center and pad the menu items, 20 pixels all round each item apart from the first which needs 60 pixels on the right.

        <section class="comments">
          <h3>Comments</h3>

          <p>The MDN site has an example of this in the hover description.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>

          <p>You may need to think about the position of the menu items.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>
        </section>
      </section>
    </article>

    <!-- Other stuff that needs to be on page -->
    <aside class="ads">
      adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts
    </aside>

    <!-- Info at the end of page -->
    <footer class="bottom">
      <p> The GamesCompany..... a <a href="parentCompany.htm">parent</a> subsiduary. </p>
      <address>
        <p>The GamesHouse.website... <br> Corporate address: 20 ARoad, AStreet, ATown. CF0 3TF</p>
      </address>
    </footer>

  </body>

</html>
```
**Answer**

```
<!DOCTYPE html>
<html>
  <head>
    <title> Kata 2</title>
    <style>
      *{
        padding:0;
        margin: 0;
      }
      
      .links li{
        padding: 0px 20px 0px 20px;
        display:block;
        float: left;
        list-style: none;
      }
      .links > ul >li:nth-child(1) {
        padding: 0 60px 0 10px;
      }
      
      .content{
        clear: both;
      }
    
    </style>
  </head>

  <body>
    
    <!-- The corporate links block -->
    <nav class ="corporateLinks"> 
      <p> 
        Introduction to Web Development: <a href="http://www.cs.cf.ac.uk">COMSC</a> <a href="http://www.cs.cf.ac.uk/software-academy">National Software Academy</a> 
      </p>
    </nav>
    
    <!-- The page title block -->
    <headder class ="title">
     <h1> Kata 2 </h1>
    </headder> 
  
    <!-- The site links block -->
    <nav class = "links">
      <h3>Site Links</h3>
      <ul>
        <li><a href="kata1Semantics.html">Home</a></li>
        <li><a href="kata1Semantics.html">Kata 1</a></li> 
        <li><a href="kata2Selection.html">Kata 2</a></li>
        <li><a href="kata3Dropdown.html">Kata 3</a></li> 
        <li><a href="kata4Pseudo.html">Kata 4</a></li>
      </ul>
    </nav>

    <!-- Main content of page -->
    <article class="content">
      <section class="mainItem">
        Look at the HTML file for this page and think about the Site Links block. <br>
        center and pad the menu items 20 pixels all round each item apart from the first which needs 50pixels on the right. 
        
        <section class="comments">
          <h3>Comments</h3>
        
          <p>The MDN site has an example of this in the hover description.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>

          <p>You may need to think about the position of the menu items.</p>
          <p> Comment by Ian <date>20/10/2012</date></p> 
        </section>
      </section>
    </article>

    <!-- Other stuff that needs to be on page -->
    <aside class="ads">
      adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts 
    </aside>
    
    <!-- Info at the end of page -->
    <footer class="bottom">
      <p> The GamesCompany..... a <a href="parentCompany.htm">parent</a> subsiduary. </p>
      <address>
        <p>The GamesHouse.website... <br> Corporate address: 20 ARoad, AStreet, ATown. CF0 3TF</p>
      </address>
    </footer>
      
  </body>

</html>
```

# 3- Dropdown
```
<!DOCTYPE html>
<html>
  <head>
    <title> Kata 3</title>

    <style>
    .links ul{
      text-align:center;
    }

    .links ul li{
      display:inline-block;
      padding: 20px;
    }

    #first{
      padding-right: : 60px;
    }

      .links:hover ul li{
        visibility: visible;
        display: block;
      }

      .content{
        clear: both;
        width:99%;
      }
      </style>

  </head>

  <body>

    <!-- The corporate links block -->
    <nav class ="corporateLinks">
      <p>
        Introduction to Web Development: <a href="http://www.cs.cf.ac.uk">COMSC</a> <a href="http://www.cs.cf.ac.uk/software-academy">National Software Academy</a>
      </p>
    </nav>

    <!-- The page title block -->
    <headder class ="title">
     <h1> Kata 3 </h1>
    </headder>

    <!-- The site links block -->
    <nav class = "links">
      <h3>Site Links</h3>
      <ul>
        <li id = "first"><a href="kata1Semantics.html">Home</a> </li>
        <li><a href="kata1Semantics.html">Kata 1</a> </li>
        <li><a href="kata2Selection.html">Kata 2</a> </li>
        <li class = "sub_links"> Sub Links
          <ul>
            <li><a href="http://www.cs.cf.ac.uk">COMSC</a></li>
            <li><a href="http://www.cs.cf.ac.uk">COMSC</a></li>
            <li><a href="http://www.cs.cf.ac.uk">COMSC</a></li>
          </ul>
        </li>
        <li><a href="kata3Dropdown.html">Kata 3</a> </li>
        <li><a href="kata4Pseudo.html">Kata 4</a> </li>
      </ul>
    </nav>

    <!-- Main content of page -->
    <article class="content">
      <section class="mainItem">
        Look at the HTML file for this page and think about the Site Links block. <br>
        First; copy the style element from your previous answer to this exercise. <br>
        Using the :hover pseudo class add a "drop down" list for the sublinks.


        <section class="comments">
          <h3>Comments</h3>

          <p>The MDN site has an example of this in the hover description.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>

          <p>You may need to think about the position of the menu items.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>
        </section>
      </section>
    </article>

    <!-- Other stuff that needs to be on page -->
    <aside class="ads">
      adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts
    </aside>

    <!-- Info at the end of page -->
    <footer class="bottom">
      <p> The GamesCompany..... a <a href="parentCompany.htm">parent</a> subsiduary. </p>
      <address>
        <p>The GamesHouse.website... <br> Corporate address: 20 ARoad, AStreet, ATown. CF0 3TF</p>
      </address>
    </footer>

  </body>

</html>
```
**Answers**
```
<!DOCTYPE html>
<html>
  <head>
    <title> Kata 3</title>
    <style>
      *{
        padding:0;
        margin: 0;
      }
/*Style the links bar*/
      .links > ul > li:nth-child(1) {
        padding: 0 60px 0 10px;
      }
      .links li{
        display:block;
        float: left;
        list-style: none;
        padding: 0px 20px 0px 20px;
        background-color: grey;
      }
/*place, but hide the sub lists  */
      .links li ul{
        display: none;
        position: absolute; ! this is out of flow and
      }
/*cancel the float left for sub list items - so they are underneath
each other*/
      .links li > ul > li{
        float: none;
      }
/*display when hovered over.
the direct child ul of a li which is hovered over (in the class links) will
 display as a block*/
      /*.links li:hover > ul, .links li:hover > ul li{*/
      .links li:hover > ul{
        display: block;
      }


      .content{
        clear: both;
      }

    </style>
  </head>

  <body>

    <!-- The corporate links block -->
    <nav class ="corporateLinks">
      <p>
        Introduction to Web Development: <a href="http://www.cs.cf.ac.uk">COMSC</a> <a href="http://www.cs.cf.ac.uk/software-academy">National Software Academy</a>
      </p>
    </nav>

    <!-- The page title block -->
    <headder class ="title">
     <h1> Kata 3 </h1>
    </headder>

    <!-- The site links block -->
    <nav class = "links">
      <h3>Site Links</h3>
      <ul>
        <li><a href="kata1Semantics.html">Home</a> </li>
        <li><a href="kata1Semantics.html">Kata 1</a> </li>
        <li><a href="kata2Selection.html">Kata 2</a> </li>
        <li> Sub Links
          <ul>
            <li><a href="http://www.cs.cf.ac.uk">COMSC</a></li>
            <li><a href="http://www.cs.cf.ac.uk">COMSC</a></li>
            <li><a href="http://www.cs.cf.ac.uk">COMSC</a></li>
          </ul>
        </li>
        <li><a href="kata3Dropdown.html">Kata 3</a> </li>
        <li><a href="kata4Pseudo.html">Kata 4</a> </li>
      </ul>
    </nav>

    <!-- Main content of page -->
    <article class="content">
      <section class="mainItem">
        Look at the HTML file for this page and think about the Site Links block. <br>
        Using the :hover pseudo class add a "drop down" list for the sublinks.


        <section class="comments">
          <h3>Comments</h3>

          <p>The MDN site has an example of this in the hover description.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>

          <p>You may need to think about the position of the menu items.</p>
          <p> Comment by Ian <date>20/10/2012</date></p>
        </section>
      </section>
    </article>

    <!-- Other stuff that needs to be on page -->
    <aside class="ads">
      adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts adverts
    </aside>

    <!-- Info at the end of page -->
    <footer class="bottom">
      <p> The GamesCompany..... a <a href="parentCompany.htm">parent</a> subsiduary. </p>
      <address>
        <p>The GamesHouse.website... <br> Corporate address: 20 ARoad, AStreet, ATown. CF0 3TF</p>
      </address>
    </footer>

  </body>

</html>
```

# 4- Pseudo


# Page for Wireframe
