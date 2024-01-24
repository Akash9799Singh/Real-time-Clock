# Real-time-Clock
  This project will auto-refresh as you edit the HTML, CSS and JS. See README.md for more info (including how to disable auto-refresh and install packages).
-->

<!doctype html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Replit</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
    <link href="script.js" rel="javascript" type="text/js" />
    <style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background: #091921;
      }

      .clock {
        width: 350px;
        height: 350px;
        display: flex;
        justify-content: center;
        align-items: center;
        background: url(clock.png);
        background-size: cover;
        border: 4px solid #091921;
        border-radius: 50%;
        box-shadow: 0 -15px 15px rgba(255, 255, 255, 0.05),
          inset 0 -15px 15px rgba(255, 255, 255, 0.05),
          0 15px 15px rgba(0, 0, 0, 0.3),
          inset 0 15px 15px rgba(0, 0, 0, 0.03);
      }

      .clock:before {
        content: '';
        position: absolute;
        width: 15px;
        height: 15px;
        background: #fff;
        border-radius: 50%;
        z-index: 10000;
      }

      .clock .Hours {
        position: absolute;
      }

      .clock .Minutes {
        position: absolute;
      }

      .clock .Seconds,
      {
      position: absolute;
      }

      .clock .Hours,
      .hrs {
        width: 160px;
        height: 160px;
      }

      .clock .Minutes,
      .mints {
        width: 190px;
        height: 190px;
      }

      .clock .Seconds,
      .secs {
        width: 230px;
        height: 230px;
      }

      .hrs {
        display: flex;
        justify-content: center;
        /align-items: center;/
        position: absolute;
        border-radius: 50%;
      }

      .mints {
        display: flex;
        justify-content: center;
        /align-items: center;/
        position: absolute;
        border-radius: 50%;
      }

      .secs {
        display: flex;
        justify-content: center;
        /align-items: center;/
        position: absolute;
        border-radius: 50%;
      }

      .hrs:before {
        content: '';
        position: absolute;
        width: 8px;
        height: 80px;
        background: #ff105e;
        z-index: 10;
        border-radius: 6px 6px 0.0;
      }

      .mints:before {
        content: '';
        position: absolute;
        width: 4px;
        height: 90px;
        background: #fff;
        z-index: 10;
        border-radius: 6px 6px 0.0;
      }

      .secs:before {
        content: '';
        position: absolute;
        width: 2px;
        height: 150px;
        background: brown;
        z-index: 12;
        border-radius: 6px 6px 0.0;
      }
    </style>
  </head>

  <body>
    <div class="clock">
      <div class="Hours">
        <div class="hrs" id="hrs"></div>
      </div>
      <div class="Minutes">
        <div class="mints" id="mints"></div>
      </div>
      <div class="Seconds">
        <div class="secs" id="secs"></div>
      </div>
    </div>
    <script>
      let Hours = document.getElementById("hrs");
      let Minutes = document.getElementById("mints");
      let Seconds = document.getElementById("secs");

      function displayTime() {
        let date = new Date();
        let hrs = date.getHours();
        let mints = date.getMinutes();
        let secs = date.getSeconds();

        let hrs_Rotation = 30 * hrs + mints / 2 + secs / 120;
        let mints_Rotation = 6 * mints + secs / 10;
        let secs_Rotation = 6 * secs;
        Hours.style.transform = rotate(${hrs_Rotation}deg)
        Minutes.style.transform = rotate(${mints_Rotation}deg)
        Seconds.style.transform = rotate(${secs_Rotation}deg)
      }

      setInterval(displayTime, 1000);
    </script>
  </body>
</html>
