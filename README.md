<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>LOVE U MY HONEYY</title>
<style>
  body {
    background: #ffe6f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    flex-direction: column;
  }
  .heart {
    width: 150px;
    height: 150px;
    background: #ff4d6d;
    position: relative;
    transform: rotate(-45deg);
    animation: beat 1s infinite;
    cursor: pointer;
    box-shadow: 0 0 15px #ff4d6d88;
  }
  .heart::before,
  .heart::after {
    content: "";
    width: 150px;
    height: 150px;
    background: #ff4d6d;
    border-radius: 50%;
    position: absolute;
  }
  .heart::before {
    top: -75px;
    left: 0;
  }
  .heart::after {
    left: 75px;
    top: 0;
  }
  @keyframes beat {
    0%, 100% {
      transform: rotate(-45deg) scale(1);
      box-shadow: 0 0 15px #ff4d6d88;
    }
    50% {
      transform: rotate(-45deg) scale(1.1);
      box-shadow: 0 0 25px #ff4d6dcc;
    }
  }
  .message {
    margin-top: 20px;
    font-size: 1.5rem;
    color: #d6336c;
    opacity: 0;
    transition: opacity 0.5s ease;
  }
  .message.show {
    opacity: 1;
  }
</style>
</head>
<body>

<div class="heart" id="heart"></div>
<div class="message" id="message">SEMANGAT YA BBY 💖</div>

<script>
  const heart = document.getElementById('heart');
  const message = document.getElementById('message');

  heart.addEventListener('click', () => {
    message.classList.toggle('show');
  });
</script>

</body>
</html>
