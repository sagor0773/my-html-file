<!DOCTYPE html>
<html>
<head>
  <title>Birthday Countdown</title>
  <style>
    body {
      text-align: center;
      font-family: Arial, sans-serif;
      background-color: #fff0f5;
      margin-top: 100px;
    }
    h1 {
      color: #ff69b4;
    }
    #countdown {
      font-size: 30px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>My Birthday Countdown!</h1>
  <p id="countdown">Loading...</p>

  <script>
    // Set your birthday here (MM/DD/YYYY)
    const birthday = new Date("05/05/2025 00:00:00").getTime();

    const countdownFunction = setInterval(function () {
      const now = new Date().getTime();
      const distance = birthday - now;

      if (distance < 0) {
        document.getElementById("countdown").innerHTML = "Happy Birthday!";
        clearInterval(countdownFunction);
      } else {
        const days = Math.floor(distance / (1000 * 60 * 60 * 24));
        const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((distance % (1000 * 60)) / 1000);

        document.getElementById("countdown").innerHTML =
          days + "d " + hours + "h " + minutes + "m " + seconds + "s ";
      }
    }, 1000);
  </script>
</body>
</html>
