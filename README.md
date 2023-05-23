<!DOCTYPE html>
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
    }
    
    h1 {
      font-family: Times New Roman, serif;
      font-style: italic;
      color: white;
      text-align: center;
    }
    
    #video-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      object-fit: cover;
    }
  </style>
</head>
<body>
  <div id="login-form">
    <form>
      <input type="text" id="username" value="your_username">
      <input type="password" id="password" value="your_password">
      <button type="button" onclick="login()">Login</button>
    </form>
  </div>

  <h1 id="welcome-msg"></h1>

  <video id="video" autoplay loop muted>
    <source src="https://www.dropbox.com/s/snsqjy444rn22e2/Static%20No%20Sound.mp4?dl=1" type="video/mp4">
  </video>

  <script>
    function login() {
      // Hide the login form
      document.getElementById('login-form').style.display = 'none';
      
      // Show the welcome message
      document.getElementById('welcome-msg').textContent = 'Welcome to Wired World.';
      
      // Set the font style for the welcome message
      document.getElementById('welcome-msg').style.fontFamily = 'Times New Roman, serif';
      document.getElementById('welcome-msg').style.fontStyle = 'italic';
      document.getElementById('welcome-msg').style.color = 'white';

      // Start the video playback
      var video = document.getElementById('video');
      video.src = "https://www.dropbox.com/s/snsqjy444rn22e2/Static%20No%20Sound.mp4?dl=1";
      video.requestFullscreen().then(function () {
        video.play();
      });

      // Start the audio playback
      var audio = new Audio("https://www.dropbox.com/s/wjct0w8fp260qvr/Apollo%20pads%20loop.mp3?dl=1");
      audio.loop = true;
      audio.play();
    }
  </script>
</body>
</html>
