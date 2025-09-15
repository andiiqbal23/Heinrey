<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Animasi Kasih Sayang Romantis</title>
<style>
  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    font-family: Arial, sans-serif;
    color: #333;
  }

  h1 {
    font-size: 2.5rem;
    margin-bottom: 10px;
    color: #800000;
    text-shadow: 1px 1px 2px #f0c0c0;
  }

  #heart-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    overflow: hidden;
    z-index: 0;
  }

  .heart {
    position: absolute;
    width: 30px;
    height: 30px;
    background: #ff4d6d;
    transform: rotate(-45deg);
    animation: fall linear forwards;
    opacity: 0.8;
  }
  .heart::before,
  .heart::after {
    content: "";
    position: absolute;
    width: 30px;
    height: 30px;
    background: #ff4d6d;
    border-radius: 50%;
  }
  .heart::before {
    top: -15px;
    left: 0;
  }
  .heart::after {
    left: 15px;
    top: 0;
  }

  @keyframes fall {
    0% {
      transform: translateY(-50px) rotate(-45deg) scale(1);
      opacity: 0.8;
    }
    100% {
      transform: translateY(110vh) rotate(45deg) scale(0.5);
      opacity: 0;
    }
  }

  #message {
    margin-top: 30px;
    font-size: 1.5rem;
    max-width: 90%;
    text-align: center;
    color: #800000;
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 1s ease, transform 1s ease;
    user-select: none;
  }

  #message.show {
    opacity: 1;
    transform: translateY(0);
  }

  #btn-love {
    margin-top: 20px;
    padding: 12px 30px;
    font-size: 1.2rem;
    background-color: #ff4d6d;
    border: none;
    border-radius: 30px;
    color: white;
    cursor: pointer;
    box-shadow: 0 5px 15px rgba(255, 77, 109, 0.6);
    transition: background-color 0.3s ease;
    user-select: none;
  }
  #btn-love:hover {
    background-color: #e03e5a;
  }
</style>
</head>
<body>

  <h1>Untuk Kamu, Istriku 💖</h1>

<div id="heart-container"></div>

<button id="btn-love">Klik Aku!</button>

<div id="message">Jangan lupa mam siang yang banyak bby, love u 💕</div>

<script>
  const heartContainer = document.getElementById('heart-container');
  const btnLove = document.getElementById('btn-love');
  const message = document.getElementById('message');

  function createHeart() {
    const heart = document.createElement('div');
    heart.classList.add('heart');
    heart.style.left = Math.random() * 100 + 'vw';
    heart.style.animationDuration = (5 + Math.random() * 5) + 's';

    heartContainer.appendChild(heart);

    heart.addEventListener('animationend', () => {
      heart.remove();
    });
  }

  setInterval(createHeart, 300);

  btnLove.addEventListener('click', () => {
    message.classList.add('show');
    btnLove.disabled = true;
    btnLove.textContent = "Terima Kasih, Sayang!";
  });
</script>

</body>
</html>
