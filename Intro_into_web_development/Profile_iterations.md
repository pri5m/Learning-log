# 1- Some CSS styling
```
<!DOCTYPE html>

<html>
  <head>
    <title>User profile </title>
    <style>

    h1{
      color: white;
      text-align: center;
    }
    h2{
      color: white;
    }
    .main_body{
      background-color: black;
      color: grey;
    }
    .github-widget{
      background-color: grey;
    }
    table {
      table-layout: fixed;
      width: 500px;
      border: 1px solid white;
    }

    td {
      border: 1px solid blue;
    }

    </style>
  </head>

  <body class = "main_body">
    <h1 id= "top"> Holly Smith: A profile </h1>

      <img src = "Me.jpg" alt = "Me" width = "20%">
      <br><br>

      <p>Follow me and star my work on Github </p>
      <div class="github-widget" data-username="pri5m"></div> <!-- https://github.com/surbhioberoi/github-widget -->
      <script src="https://unpkg.com/github-card@1.2.1/dist/widget.js"></script>
      <br> <br>

      <img src = "animated_image.gif" alt = "animated_image">
      <br>

    <h2> My background </h2>
      <article>
        I am from South London and live a short walk away from the station; <br>
        ideal for commuting into the city. <br>
        I attended Nonsuch High School for Girls from 2010-2017 where I completed <br>
        my GSCEs and A-levels.
      </article>

    <h2> My hobbies </h2>
      <article>
        I enjoy reading comics and graphic novels, as well as watching films. <br>
        I also enjoy doing martial arts, such as Karate and Tae Kwon-do. <br>
        When I am not reading the news or Reddit, then you will find me watching
        Youtube videos, Netflix or anime.
      </article>

      <p>I enjoy creating digital art. Here is some fan art that I created for the anime- No Game No life: </p>
      <img src = "Shiro_NGNL.jpg" alt = "Shiro_fanart" width = "30%">
      <br><br><br>

      <table>
      <caption> My favourite anime </caption>
      <thead>
        <tr>
          <th> Anime </th>
          <th> Reasons why </th>
        </tr>
      </thead>
      <tr>
        <td>Natsume yuujinchou</td>
        <td>Has likeable and well developed characters</td>
      </tr>
      <tr>
        <td>Mahou Shoujo Madoka Magica</td>
        <td>Great visuals and animation</td>
      </tr>
      <tr>
        <td>Assassination classroom</td>
        <td>Feel good story</td>
      </tr>
      <tr>
        <td>Death Note</td>
        <td>Fast paced and captivating</td>
      </tr>
      </table>
      <br>

    <h2> Interesting facts about myself </h2>
    <ol>
      <li> I play the trumpet and did my grade 8 exam. </li>
      <li> I have two Guinea Pigs called Pippin and Pepper</li>
      <li> I took part in the Space Design competion held at Imperial and was
        part of the winning team. </li>
      <li> I also do digital art in my own time using a Wacom digital tablet </li>
    </ol>
    <br>

    <p>Warframe is one of the online games that I play. Here is the trailer for it: </p>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ebZ09b-Ahio" frameborder="0" allowfullscreen></iframe>
    <br>
    <!--<video src= "https://www.youtube.com/watch?v=Gx5RDaGVkZE" controls>
      <p>Your browser doesn't support HTML5 video. Here is a <a href="https://www.youtube.com/watch?v=Gx5RDaGVkZE">link to the video</a> instead.</p>
    </video> -->

    <p>'I like what you got' </p>
    <audio controls>
      <source src="https://sound.peal.io/ps/audios/000/000/706/original/I_like_what_you_got.wav?1469744420" type="audio/mp3"> #source: https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content
      <p>Your browser doesn't support HTML5 audio. Here is a <a href="https://sound.peal.io/ps/audios/000/000/706/original/I_like_what_you_got.wav?1469744420t">link to the audio</a> instead.</p>
    </audio>

    <section>
      <p> Contact me. Please fill out this form. </p>

      <form action = "http://127.0.0.1:8080/myAction" method = "get" id="myform">
        Name:<br>
        <input type="text" name="name">
        <br>
        Contact email:<br>
        <input type="text" name="query"><br>
        Query or question:<br>
        <input type="text" name="query"><br>
        Comments:<br>
        <textarea rows="5" cols = "60" name = "text">Write something here</textarea>
        <br><br>
        <button type="submit">submit</button>
      </form>
    </section>

  </body>
  <footer>
    <h3> Sponsor websites and information </h3>
    <p>
      Here are some of the links to the uni that I am studying at <br>
      <a href = "http://www.cs.cf.ac.uk"> COMSC </a>. <br>
      <a href = "https://www.cardiff.ac.uk/"> Cardiff uni </a>
    </p>
    <p>
      Please e-mail me if you have any further requirements. I will aim to respond <br>
      within 48 hours
      <a href = "mailto:blah@cardiff.ac.uk"> My e-mail address </a>
    </p>
  </footer>
</html>
```
