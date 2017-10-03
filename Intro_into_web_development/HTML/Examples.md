# 1) Basics
```HTML
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Basic html </title>
  </head>

  <body>
    <h1>Ian Cooper</h1>


    <p> this is my first html</p>

    
  </body>
</html>

```
# 2) Semantics
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title> Semantics  </title>
  </head>

  <body>
    <h1> Blog Page </h1>
    <div> <!-- this is the blog  -->
      <div> <!-- this is a blog entry -->
        <h2>The 1st post</h2>
        <p>Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog </p>
        <div>
          <p>Posted on <time datetime="2017-9-9 15:00">May 16</time> by Ian.</p>
        </div>
      </div><!-- end of blog entry -->

      <div> <!-- this is a blog entry -->
        <h2>The 2nd post</h2>
        <p>Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog Blog </p>
        <div>
          <p>  Posted on <time datetime="2017-9-9 15:00">May 16</time> by Ian.  </p>
        </div>
      </div> <!-- end of blog entry -->
    </div> <!-- end of the blog  -->

    <div> <!-- this is the footer info  -->
      <p>  this site is maintained by acme blogging.com  </p>
    </div>

  </body>
</html>
```
[elements video](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4449853-dt-content-rid-7834305_2/xid-7834305_2)

# 3) Lists and tables
```HTML
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Lists Tables </title>
  </head>

  <body>
    <h1>Lists and Tables</h1>
    <!-- new stuff -->
    <h3>Favourite Films</h3>
    <ul>
      <li>Star Wars</li>
      <li>Star Trek</li>
      <ul>
        <li>the new ones</li>
        <li>the old ones</li>
      </ul>
    </ul>

      <table>
      <caption> Shopping </caption>
      <thead>
        <tr>
          <th> Item </th>
          <th> Quantity </th>
        </tr>
      </thead>
      <tr>
        <td>apples</td>
        <td>5</td>
      </tr>
      <tr>
        <td>bananas</td>
        <td>3</td>
      </tr>
    </table>
    <!-- end new stuff -->
  </body>
</html>
```
**Important**
When finding links make sure to use image lins directly from the website, not from google, else it won't work

# 4) Attributes
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Attributes </title>
  </head>

  <body>
    <p title = "bio"> hi I am Ian Cooper</p>
    <h1>Ian Cooper</h1>
    <a href ="http://bbc.co.uk">
      <img src = "ian.jpg" width = "20%">
    </a>
      <table draggable = "true" title = "shopping list">
      <caption> Shopping </caption>
      <thead>
        <tr>
          <th> Item </th>
          <!-- colspan="2"   width ="20%"-->
          <th> Quantity </th>
        </tr>
      </thead>
      <tr>
        <td>apples</td>
        <td>5</td>
      </tr>
      <tr>
        <td>bananas</td>
        <td>3</td>
      </tr>
    </table>
  </body>
</html>
```
[attributes video](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4449855-dt-content-rid-7834309_2/xid-7834309_2)

# 5) links
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title> Links </title>
  </head>

  <body>
    <h1 id = "top">Ian Cooper</h1>
    <p>Hi I am Ian Cooper, I work
      in <a href = "http://www.cs.cf.ac.uk"> COMSC </a>.</p>
    <a href = "mailto:i.m.cooper@cs.cf.ac.uk">mail me</a>
    <br><br><br><br><br><br><br>
Scroll down
    <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
    <a href = "#top">go to top</a>
  </body>
</html>
```
[Links, lists and tables video](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4449862-dt-content-rid-7834311_2/xid-7834311_2)

# 6) Forms
```HTML
<!DOCTYPE html>
<!-- comment -->
<html>
  <head>
    <title> Forms </title>
  </head>

  <body>
    <h1>Ian Cooper</h1>
    <p>Contact me...</p>

    <form action = "http://127.0.0.1:8080/myAction" method = "get" id="myform">
      First name:<br>
      <input type="text" name="firstname">
      <br>
      Last name:<br>
      <input type="text" name="lastname"><br>
      comments:<br>
      <textarea rows="5" cols = "50" name = "text">Write something here</textarea>
      <br><br>
      <button type="submit">submit</button>
    </form>

  </body>
</html>
```
[form video](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4449867-dt-content-rid-7834316_2/xid-7834316_2)
