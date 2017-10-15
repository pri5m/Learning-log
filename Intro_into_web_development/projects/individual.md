# home
```
<html>

  <head>
    <title>Project | Home Page</title>
    <link rel = "stylesheet" type = "text/css" href = "Profile_styling.css">
    <link href="https://fonts.googleapis.com/css?family=Ubuntu" rel="stylesheet">
    <style>
      *{
        padding: 5px;
        margin: 5px;
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

      .footer{
        margin: 10px;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }

    </style>
  </head>
  <body class = "main-body">

    <h1> HTML and CSS tutorials </h1>

    <nav class = "links">
     <ul>
       <li><a href = "home.html" href="css_syntax.asp" class = "highlight">Home</a></li>&nbsp; &nbsp; <!--target="_blank" opens lnk into a new tab-->
       <li><a href = "profile.html" href="css_syntax.asp" class = "highlight">Profile</a></li>&nbsp; &nbsp;
       <li><a href = "contact.html" href="css_syntax.asp" class = "highlight">Contacts</a></li>&nbsp; &nbsp;
       <li><a href = "video.html" href="css_syntax.asp" class = "highlight">Videos</a></li>&nbsp;
      </ul>
    </nav> <br> <br>

    <section>
      <h2> XKCD: Password strength </h2>
      <img src = "https://imgs.xkcd.com/comics/password_strength.png" alt = "XKCD 936" class = "comic">
      <br> <br>
      <h2> What people think coding is... </h2>
      <img src = "https://i.redd.it/9nxwv2c0fsaz.jpg" alt = "img_text" class = "img-text">
      <br> <br>
      <iframe src="https://giphy.com/embed/dbtDDSvWErdf2" width="480" height="261" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/richard-ayoade-it-crowd-maurice-moss-dbtDDSvWErdf2">via GIPHY</a>
    </section>

    <section>
      <h2> Bored of tutorials? Give this a try! </h2> <!--http://www.ageofdefenders.com/embed-game -->
      <script type="text/javascript" src="http://cdn.static.geewa.net/g/age-of-defenders/launcher/embed.js"></script>
      <canvas type="application/x-shockwave-flash" id="AOD" name="AOD" data="http://cdn.static.geewa.net/g/age-of-defenders/launcher/StandalonePreloader.swf">
        <param name="quality" value="high">
        <param name="bgcolor" value="#000000">
        <param name="allowscriptaccess" value="sameDomain">
        <param name="allowfullscreen" value="true">
        <param name="allowFullScreenInteractive" value="true">
        <param name="wmode" value="direct">
      </canvas>
    </section>

  </body>
  <footer class = "footer">
    <script type="text/javascript" src="http://100widgets.com/js_data.php?id=255"></script> <br> <br> <br>
    <!-- http://100widgets.com/others/255-shasocial-networking-buttons-after-the-text.html -->
    <p> © 2017    ilex.laurel.smith@gmail.com </p>
    <img src = "http://russellgroup.ac.uk/media/5002/cardiff.png?anchor=center&mode=crop&width=288&rnd=130809473120000000" alt = "Cardiff logo" id = "Cardiff_logo">
  </footer>
</html>
```
# Profile
```
<html>
  <head>
    <title> Project | Profile page </title>
    <link rel = "stylesheet" type = "text/css" href = "Profile_styling.css">
    <script type="text/javascript" src="https://platform.linkedin.com/badges/js/profile.js" async defer></script>
    <link href="https://fonts.googleapis.com/css?family=Ubuntu" rel="stylesheet">
    <style>
      *{
        padding: 5px;
        margin: 5px;
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

      .profilePic{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }

      .credentials{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }

      .about-me{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
        display: inline;
      }

      .github-widget{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        float: left;
      }

      .linked-in{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        float: left;
      }

      .audio-play{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        float: left;
      }

      .footer{
        margin: 10px;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }
    </style>

  </head>

  <body class = "main-body">
    <h1> Profile </h1>

    <nav class = "links">
     <ul>
       <li><a href = "home.html" class = "highlight">Home</a></li>&nbsp; &nbsp; <!--target="_blank" opens lnk into a new tab-->
       <li><a href = "profile.html" class = "highlight">Profile</a></li>&nbsp; &nbsp;
       <li><a href = "contact.html" class = "highlight">Contacts</a></li>&nbsp; &nbsp;
       <li><a href = "video.html" class = "highlight">Videos</a></li>&nbsp;
      </ul>
    </nav>

    <div class = "profilePic">
     <img src = "Me.jpg" alt = "Me" class = "Me"> <!-- Add Id and put the width in the CSS  element -->
    </div>

    <article class = "about-me">
      <h2> About me </h2>

      <p> I am an undergrad studying for a BSc in Applied Software Engineering.
        My expected year of graduation is in 2020. </p>

      <p> Along side my main degree, I am also studying Japanese as part of
        Cardiff University's<a href "https://www.cardiff.ac.uk/modern-languages/courses/languages-for-allLanguages" target="_blank" class = "highlight">Languages For All </a>
        program. I attend a 2 hour class each week as part of this and can then
        do as much studying in my own time as I want to. </p>

      <p> To further enrich the time that I am at university I have joined clubs
        which offer a variety of socials. The<a href = "https://www.cardiffstudents.com/activities/society/anime/" target = "_blank" class = "highlight">Anime Soc</a>
        has weekly screenings where members watch either a film or five episodes
        of a series. As well as this, they also have, on alternate weeks, a workshop
        where participants can try out activities related to Japanese culture or
        anime.</p>

      <p>I also joined a sports society Tae Kwon-do.<a href = "https://www.cardiffstudents.com/activities/sport/cutkd/" target = "_blank" class = "highlight">Tae Kwon-do</a>meets up twice a
        week for practice and once a week as a social. I enjoy Tae Kwon-do as it
        has a lot of variety, making it more interesting. </p>
    </article>

    <article class = "credentials">
      <h2> My credentials </h2>

      <h3> A- level subject list: </h3>
      <ul>
        <li> Biology </li>
        <li> Chemistry </li>
        <li> Geography </li>
      </ul>

      <h3> BSc Applied Software Engineering course content: </h3>
        <ul>
          <li> Year 1 </li>
            <ul>
              <li> Introduction into Web Development </li>
              <li> Computational thinking </li>
              <li> Software development skills 1 </li>
              <li> Fundamentals of computing with Java </li>
              <li> Mobile development with Android </li>
              <li> Software development skills 2 </li>
            </ul>
          <li> Year 2 </li>
            <uL>
              <li> Database systems </li>
              <li> DevOps </li>
              <li> Commercial applications with Java </li>
              <li> Security </li>
              <li> Preformance and scalability </li>
              <li> Agile project management </li>
            </ul>
          <li> Year 3 </li>
            <ul>
              <li> Commercial frameworks, languages and tools </li>
              <li> Adopting technologies </li>
              <li> Emerging technologies </li>
              <li> Large team project </li>
              <li> Managing software enabled change in large organisations </li>
            </ul>

    </article>

    <section class = "linked-in">
     <h2> Visit my Github profile: </h2>
      <div class="github-widget" data-username="pri5m"></div> <!-- https://github.com/surbhioberoi/github-widget -->
      <script src="https://unpkg.com/github-card@1.2.1/dist/widget.js"></script>
    </section>

    <section class = "linked-in">  <!--https://www.linkedin.com/badges/profile/create?vanityname=holly-smith-b5349a151&trk=pprof-settings-badge-->
     <h2> Visit my LinkedIn profile: </h2>
      <div class="LI-profile-badge"  data-version="v1" data-size="medium" data-locale="en_UK" data-type="horizontal" data-theme="dark" data-vanity="holly-smith-b5349a151">
      <a class="LI-simple-link" href='https://uk.linkedin.com/in/holly-smith-b5349a151?trk=profile-badge'>Holly Smith</a></div>
    </section>

    <section class = "audio-play">
     <p>'I like what you got' </p>
     <audio controls autoplay>
       <source src="https://sound.peal.io/ps/audios/000/000/706/original/I_like_what_you_got.wav?1469744420" type="audio/mp3"> #source: https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content
       <p>Your browser doesn't support HTML5 audio. Here is a <a href="https://sound.peal.io/ps/audios/000/000/706/original/I_like_what_you_got.wav?1469744420t">link to the audio</a> instead.</p>
     </audio> <br> <br>
    </section>
  </body>

  <footer class = "footer">
    <script type="text/javascript" src="http://100widgets.com/js_data.php?id=255"></script> <br> <br> <br>
    <!-- http://100widgets.com/others/255-shasocial-networking-buttons-after-the-text.html -->
    <p> © 2017    ilex.laurel.smith@gmail.com </p>
    <img src = "http://russellgroup.ac.uk/media/5002/cardiff.png?anchor=center&mode=crop&width=288&rnd=130809473120000000" alt = "Cardiff logo" id = "Cardiff_logo">
  </footer>

</html>
```
# contacts
```
<html>

  <head>
    <title> Project | Contact Information </title>
    <link rel = "stylesheet" type = "text/css" href = "Profile_styling.css">
    <link href="https://fonts.googleapis.com/css?family=Ubuntu" rel="stylesheet">
    <style>
      *{
        padding: 5px;
        margin: 5px;
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

      .web-links{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }

      .queries{
        margin: 10px;
        border: 1px solid black;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }

      .footer{
        margin: 10px;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }
    </style>

  </head>

  <body class = "main-body">
    <h1> Contact Information </h1>

    <nav class = "links">
     <ul>
       <li><a href = "home.html" class = "highlight">Home</a></li>&nbsp; &nbsp; <!--target="_blank" opens lnk into a new tab-->
       <li><a href = "profile.html" class = "highlight">Profile</a></li>&nbsp; &nbsp;
       <li><a href = "contact.html" class = "highlight">Contacts</a></li>&nbsp; &nbsp;
       <li><a href = "video.html" class = "highlight">Videos</a></li>&nbsp;
      </ul>
    </nav> <br> <br>

    <section class = "queries">
      <h2> Queries </h2>
      <p> To contact me, fill out the form below: </p>

      <form action = "http://127.0.0.1:8080/myAction" method = "get" id="myform">
        <select name="title"> <!--https://www.w3schools.com/html/html_form_elements.asp -->
          <option value="Miss">Miss</option>
          <option value="Mister">Mister</option>
          <option value="Ms">Ms</option>
          <option value="Mrs">Mrs</option>
          <option value="Mr">Mr</option>
          <option value="Sir">Sir</option>
          <option value="Dr">Dr</option>
        </select> <br>
        Name:<br>
        <input type="text" name="name">
        <br>
        Contact email:<br>
        <input type="email" name="email"><br>
        Query:<br>
        <input type="text" name="query"><br>
        Comments:<br>
        <textarea rows="5" cols = "60" name = "comments">Write something here</textarea>
        <br><br>
        <button type="submit">submit</button>
      </form>
    </section>

    <nav class = "web-links">
      <h2> Sponsor websites and information </h2>
      <ul>
        <p>
          Institution information: <br>
          <li> <a href = "http://www.cs.cf.ac.uk" target="_blank"> COMSC </a>. </li> <br>
          <li> <a href = "https://www.cardiff.ac.uk/" target="_blank"> Cardiff university </a> </li> <br>
          <li> <a href = "https://www.cardiff.ac.uk/study/undergraduate/courses/2018/applied-software-engineering-bsc" target="_blank"> Applied software engineering course </a> </li> <br>
        </p>
      </ul>
      <p>
        Please e-mail me if you have any further requirements. <br>
        I will aim to respond within 48 hours.<br>
        <a href = "mailto:SmithHL2@cardiff.ac.uk" target = "blank"> E-mail address </a>
      </p>
    </nav>
  </body>

  <footer class = "footer">
    <script type="text/javascript" src="http://100widgets.com/js_data.php?id=255"></script> <br> <br> <br>
    <!-- http://100widgets.com/others/255-shasocial-networking-buttons-after-the-text.html -->
    <p> © 2017    ilex.laurel.smith@gmail.com </p>
    <img src = "http://russellgroup.ac.uk/media/5002/cardiff.png?anchor=center&mode=crop&width=288&rnd=130809473120000000" alt = "Cardiff logo" id = "Cardiff_logo">
  </footer>

</html>
```

# videos
```
<html>
  <head>
    <title> Project | Video tutorials </title>
    <link rel = "stylesheet" type = "text/css" href = "Profile_styling.css">
    <link href="https://fonts.googleapis.com/css?family=Ubuntu" rel="stylesheet">
    <style>
      *{
        padding: 5px;
        margin: 5px;
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

      .footer{
        margin: 10px;
        padding: 5px;
        width:40%;
        text-align: left;
        float: left;
      }
    </style>
  </head>

  <body class = "main-body">

    <h1> Video tutorials </h1>

    <nav class = "links">
     <ul>
       <li><a href = "home.html" class = "highlight">Home</a></li>&nbsp; &nbsp; <!--target="_blank" opens lnk into a new tab-->
       <li><a href = "profile.html" class = "highlight">Profile</a></li>&nbsp; &nbsp;
       <li><a href = "contact.html" class = "highlight">Contacts</a></li>&nbsp; &nbsp;
       <li><a href = "video.html" class = "highlight">Videos</a></li>&nbsp;
      </ul>
    </nav> <br> <br>

    <table>
    <thead>
      <tr>
        <th> Video </th>
        <th> Summary </th>
        <th> Source </th>
      </tr>
    </thead>
    <tr>
      <td><a href = "https://www.youtube.com/watch?v=3NjQ9b3pgIg" target="_blank"> How to choose a password</a> <br></td>
      <td> A video effectively explaining whwo to create a password <br>
      that can survive a brute force attack. </td>
      <td> Computerphile </td>
    </tr>
    <tr>
      <td><a href = "https://www.youtube.com/watch?v=XETZoRYdtkw" target="_blank"> How computer memory works</a></td>
      <td> How logic gates work to create a system where information can be stored.</td>
      <td> Computerphile </td>
    </tr>
    <tr>
      <td><a href = "https://www.youtube.com/watch?v=BsSmBPmPeYQ" target="_blank"> Deep Dream</a></td>
      <td> Explaining how Google's Deep Dream works</td>
      <td> Computerphile </td>
    </tr>
    <tr>
      <td><a href = "https://www.youtube.com/watch?v=l42lr8AlrHk" target="_blank"> Deep Learning</a></td>
      <td> Deep learning is used by several large companies such as Google and Facebook <br>
      This video explains what deep learning is.</td>
      <td> Computerphile </td>
    </tr>
    </table>
    <br>

    <div>
      <h2> Youtube tutorial </h2> <br>
      <iframe width="560" height="315" src="https://www.youtube.com/embed/kDyJN7qQETA" frameborder="0" allowfullscreen></iframe>
    </div> <br>

    <div>
      <h2> mp4 tutorial </h2>
      <video class = "video_small" controls>
        <source src="Elements.mp4" type="video/mp4">
      Your browser does not support the video tag.
      </video>
    </div> <br> <br>


  </body>

  <footer class = "footer">
    <script type="text/javascript" src="http://100widgets.com/js_data.php?id=255"></script> <br> <br> <br>
    <!-- http://100widgets.com/others/255-shasocial-networking-buttons-after-the-text.html -->
    <p> © 2017    ilex.laurel.smith@gmail.com </p>
    <img src = "http://russellgroup.ac.uk/media/5002/cardiff.png?anchor=center&mode=crop&width=288&rnd=130809473120000000" alt = "Cardiff logo" id = "Cardiff_logo">
  </footer>

</html>
```

# CSS
```
h1{
  color: black;
  text-align: center;
  background-color: rgb(165, 219, 133);
}
h2{
  color: grey;
}
.main-body{
  background-color: rgb(200, 255, 167);
  color: rgb(91, 99, 87);
  font-family: 'Ubuntu', sans-serif;
}

.github-widget{
  background-color: rgb(231, 231, 231);
  width: 100% !important;
}

nav.links{
  background-color: rgb(163, 196, 143);
  font-size: 20px;
  position: -webkit-sticky;
  position: sticky;
  top: 0;
}

a.highlight:hover{
  color: rgb(255, 255, 255);
}

table {
  table-layout: fixed;
  width: 700px;
  border: 1px solid green;
}

/* pseudo element */
th::first-line{
  font-size: 20pt;
}

td:nth-of-type(even){
  background-color:lightgrey;
}

td {
  border: 1px solid blue;
}

img.comic {
  width: 700px;
}

img.img-text {
  width: 500px;
}

img.me{
  width: 50%;
}


#Cardiff_logo {
  width: 50;
  height: 50px;
}

#AOD{
  align: "middle";
   width: "1px";
   height: "1px";
}

video{
  width: 600px;
  height: 600px;
}

/* Cascading CSS */
video.video_small{
  width: 500px;
  height: 400px;
}
```
