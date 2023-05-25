<html>
<head>
  <title>Login Page</title>
  <style>
    body {
      background-color: black;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    
    #login-form {
      width: 200px;
      padding: 20px;
      background-color: rgba(255, 255, 255, 0.5);
      border-radius: 5px;
      backdrop-filter: blur(10px);
      text-align: center;
    }
    
    h1 {
      font-family: "Times New Roman", serif;
      font-style: italic;
      color: white;
      text-align: center;
      margin-top: 50px;
    }
    
    #login-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      object-fit: cover;
      filter: blur(20px);
    }
    
    #player {
      display: none;
      width: 300px;
      background-color: rgba(255, 255, 255, 0.5);
      border-radius: 5px;
      padding: 20px;
      position: fixed;
      top: 20px;
      right: 20px;
    }
    
    #player img {
      width: 100%;
      height: auto;
      margin-bottom: 20px;
    }
    
    #player audio {
      width: 100%;
    }
    
    #player button {
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <h1>Wired Sound for Wired People</h1>

  <div id="login-form">
    <form>
      <input type="text" id="username" value="User 0001">
      <input type="password" id="password" value="your_password">
      <button type="button" onclick="login()">Login</button>
    </form>
  </div>

  <div id="player">
    <img src="https://www.dropbox.com/s/snreyzwgowu31h9/Flame%206.png?dl=1" alt="Background Image">
    <audio id="audio" src="https://www.dropbox.com/s/bkm5nybdnk688ay/My%20Nostalgia%20Mixtape%2001.mp3?dl=1" loop></audio>
    <button onclick="previous()">Previous</button>
    <button onclick="playPause()">Play/Pause</button>
    <input type="range" id="volume" min="0" max="100" step="1" oninput="setVolume(this.value)">
    <button onclick="next()">Next</button>
  </div>

  <script>
    function login() {
      // Hide the login form
      document.getElementById('login-form').style.display = 'none';

      // Show the player
      document.getElementById('player').style.display = 'block';

      // Change the body background image
      document.body.style.backgroundImage = 'url("https://www.dropbox.com/s/mhimmxmq1kgvroj/Flame%202.png?dl=1")';
    }

    function playPause() {
      var audio = document.getElementById('audio');
      var playPauseButton = document.getElementById('play-pause-button');

      if (audio.paused) {
        audio.play();
        playPauseButton.textContent = 'Pause';
      } else {
        audio.pause();
        playPauseButton.textContent = 'Play';
      }
    }

    function setVolume(volumeValue) {
      var audio = document.getElementById('audio');
      audio.volume = volumeValue / 100;
    }

    function previous() {
      var audio = document.getElementById('audio');
      audio.src = "https://www.dropbox.com/s/bkm5nybdnk688ay/My%20Nostalgia%20Mixtape%2001.mp3?dl=1";
      audio.play();
      document.body.style.backgroundImage = 'url("https://www.dropbox.com/s/mhimmxmq1kgvroj/Flame%202.png?dl=1")';
    }

    function next() {
      var audio = document.getElementById('audio');
      audio.src = "https://www.dropbox.com/s/3po6idbwdie8624/Live%20%40Starry%20Shelter%20ft.%20Mr.%20Ye.mp3?dl=1";
      audio.play();
      document.body.style.backgroundImage = 'url("https://www.dropbox.com/s/snreyzwgowu31h9/Flame%206.png?dl=1")';
    }
  </script>
</body>
</html>
