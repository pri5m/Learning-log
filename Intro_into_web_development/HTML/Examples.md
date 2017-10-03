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
